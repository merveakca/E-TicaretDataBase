# E-TicaretDataBase Tabloları ve Açıklamaları
---

# 1. Categories Tablosu

```
Id
Name
IsActive
MainCategoryId
CreatedDate
UpdatedDate
Path
VatRate
```

**AÇIKLAMA:**  

---

# 2. CategoryEquivalents Tablosu

```
Id
CategoryId
EquivalentId
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 3. CategoryFields Tablosu

```
Id
Name
CategoryId
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 4. CommentImageUrls Tablosu

```
Id
CommentId
ImageUrl
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 5. CommentLikes Tablosu

```
Id
UserId
CommentId
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 6. Comments Tablosu

```
Id
OrderId
Rating
Comment
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 7. Invoices Tablosu

```
Id
OrderId
InvoiceNumber
Date
DeliveryDate
CreatedDate
UpdatedDate
Discount
```

**AÇIKLAMA:** 

---

# 8. Orders Tablosu

```
Id
UserId
ProductFieldId
SellingPrice
Stock
UserAddressId
CreatedDate
UpdatedDate
OrderStatusId
CargoTracingNumber
```

**AÇIKLAMA:** 

---

# 9. OrderStatuses Tablosu

```
Id
Name
CreatedDate
UpdatedDate
IsActive
```

**AÇIKLAMA:** 

---

# 10. PaymentDetails Tablosu

```
Id
OrderId
PaymentPrice
PaymentType
CreatedDate
UpdatedDate
KKPaymentConfirmId
BankName
IsCompleted
CompletedDate
Description
```

**AÇIKLAMA:** 

---

# 11. ProductFieldCategoryFields Tablosu

```
Id
ProductFieldId
CategoryFieldId
Value
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 12. ProductFieldImageUrls Tablosu

```
Id
ImageUrl
CreatedDate
UpdatedDate
ProductFieldId
```

**AÇIKLAMA:** 

---

# 13. ProductFields Tablosu

```
Id
Name
CreatedDate
UpdatedDate
ProductSelectionId
MainImageUrl
MainProductFieldId
IsActive
Price
SellingPrice
Stock
IsVatInclude
```

**AÇIKLAMA:** 

---

# 14. Products Tablosu

```
Id
Name
OverrangeRating
CreatedDate
UpdatedDate
SellerId
```

**AÇIKLAMA:** 

---

# 15. ProductSelections Tablosu

```
Id
Name
CreatedDate
UpdatedDate
ProductId
MainProductSelectionId
```

**AÇIKLAMA:** 

---

# 16. Sellers Tablosu

```
Id
Name
Address
TaxIdentityNumber
IdentityNumber
TaxDepartmentId
WebSite
PhoneNumber
Email
UserName
PasswordHash
PasswordSalt
IsConfirm
ConfirmCode
ConfirmCodeSendDate
ChangePasswordCode
ChangePasswordCodeSendDate
ChangePasswordIsCompleted
CreatedDate
UpdatedDate
AverageRating
IsActive
```

**AÇIKLAMA:** 

---

# 17. SellerTitles Tablosu

```
Id
Title
CreatedDate
UpdatedDate
SellerId
```

**AÇIKLAMA:** 

---

# 18. ShoppingCarts Tablosu

```
Id
UserId
ProductFieldId
Stock
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 19. TaxDepartments Tablosu

```
Id
City
Town
Code
Name
```

**AÇIKLAMA:** 

---

# 20. TicketDetails Tablosu

```
Id
TicketId
SellerId
UserId
Content
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 21. Tickets Tablosu

```
Id
SellerId
UserId
Subject
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 22. UserAddresses Tablosu

```
Id
UserId
City
Town
Street
ZipCode
Address
PhoneNumber
Name
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# 23. Users Tablosu

```
Id
Name
Email
PhoneNumber
PasswordHash
PasswordSalt
IsActive
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

