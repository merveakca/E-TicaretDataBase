# Store Prosedürler ve Açıklamaları
---

# 1. CategoryListByNameAndCategoryPath Prosedürü

```
CREATE PROCEDURE CategoryListByNameAndCategoryPath 
AS
BEGIN
    WITH CategoryHierarchy AS
    (
        -- Ana kategorileri bul
        SELECT 
            Id,
            Name,
            CAST(Name AS NVARCHAR(MAX)) AS CategoryPath
        FROM 
            Categories
        WHERE 
            MainCategoryId IS NULL
        UNION ALL
        -- Alt kategorileri bul
        SELECT 
            c.Id,
            c.Name,
            CAST(ch.CategoryPath + ' > ' + c.Name AS NVARCHAR(MAX)) AS CategoryPath
        FROM 
            Categories c
        JOIN 
            CategoryHierarchy ch ON ch.Id = c.MainCategoryId
    )
    SELECT * FROM CategoryHierarchy
    ORDER BY CategoryPath;
END
```

**AÇIKLAMA:**  

---

# 2. CategoryListWithSubCategories Prosedürü

```
CREATE PROCEDURE CategoryListWithSubCategories
AS
BEGIN
    WITH CategoryHierarchy AS (
        SELECT 
            Id,
            Name,
            IsActive,
            MainCategoryId,
            CAST(Name AS VARCHAR(MAX)) AS Hierarchy
        FROM
            Categories
        WHERE 
            MainCategoryId IS NULL

        UNION ALL

        SELECT
            c.Id,
            c.Name,
            c.IsActive,
            c.MainCategoryId,
            CAST((ch.Hierarchy + ' > ' + c.Name) AS VARCHAR(MAX)) AS Hierarchy
        FROM 
            Categories c
        INNER JOIN CategoryHierarchy ch
        ON ch.Id = c.MainCategoryId
    )
    SELECT Hierarchy FROM CategoryHierarchy WHERE IsActive = 1;
END
```

**AÇIKLAMA:** 

---

# 3. MainCategoryListByCategoryId Prosedürü

```
CREATE PROCEDURE MainCategoryListByCategoryId
@categoryId INT
AS
BEGIN
    WITH CategoryHierarchy AS (
        SELECT
            Id,
            Name,
            IsActive,
            MainCategoryId,
            CAST(Name AS VARCHAR(MAX)) AS Hierarchy
        FROM
            Categories
        WHERE 
            Id = @categoryId

        UNION ALL

        SELECT
            c.Id,
            c.Name,
            c.IsActive,
            c.MainCategoryId,
            CAST((c.name  + ' > ' + ch.Hierarchy) AS VARCHAR(MAX)) AS Hierarchy 
        FROM
            Categories c
        INNER JOIN CategoryHierarchy ch
        ON ch.MainCategoryId = c.Id
    )
    SELECT Hierarchy 
    FROM CategoryHierarchy
    WHERE IsActive = 1 AND MainCategoryId IS NULL;
END
```

**AÇIKLAMA:** 
