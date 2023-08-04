# Store Prosedürler ve Açıklamaları
---

# 1. CategoryListByNameAndCategoryPath

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

# 2. 

```
CREATE Procedure [dbo].[CategoryListWithSubCategories]
AS
Begin
WITH CategoryHierarchy AS (
	SELECT 
		Id,
		Name,
		IsActive,
		MainCategoryId,
		CAST(Name as VARCHAR(MAX)) AS Hierarchy
	FROM
		Categories
	Where 
		MainCategoryId is Null

	UNION ALL

	SELECT
		c.Id,
		c.Name,
		c.IsActive,
		c.MainCategoryId,
		CAST((ch.Hierarchy + ' > ' + c.Name) AS VARCHAR(MAX)) as Hierarchy
	From 
	Categories c
	INNER JOIN CategoryHierarchy ch
	on ch.Id = c.MainCategoryId
)

SELECT Hierarchy From CategoryHierarchy where IsActive = 1
End
```

**AÇIKLAMA:** 

---

# 3. 

```
CREATE PROCEDURE [dbo].[MainCategoryListByCategoryId] @categoryId INT
AS
BEGIN
WITH CategoryHierarchy AS (
	SELECT
		Id,
		Name,
		IsActive,
		MainCategoryId,
		CAST(Name as VARCHAR(MAX)) AS Hierarchy
	FROM
		Categories
	Where 
		Id = @categoryId

	UNION ALL

	SELECT
		c.Id,
		c.Name,
		c.IsActive,
		c.MainCategoryId,
		CAST((c.name  + ' > ' + ch.Hierarchy) as VARCHAR(MAX)) AS Hierarchy 
	FROM
		Categories c
	INNER JOIN CategoryHierarchy ch
	ON ch.MainCategoryId = c.Id
)

SELECT TOP 1 Hierarchy 
From CategoryHierarchy
Where IsActive = 1
Order By LEN(Hierarchy) DESC
END
```

**AÇIKLAMA:** 
