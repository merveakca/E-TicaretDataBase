# E-TicaretDataBase Tabloları ve Açıklamaları
---

# Categories Tablosu

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

# CategoryEquivalents Tablosu

```
Id
CategoryId
EquivalentId
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# CategoryFields Tablosu

```
Id
Name
CategoryId
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# CommentImageUrls Tablosu

```
Id
CommentId
ImageUrl
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# CommentLikes Tablosu

```
Id
UserId
CommentId
CreatedDate
UpdatedDate
```

**AÇIKLAMA:** 

---

# Comments Tablosu

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

# Invoices Tablosu

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

# Orders Tablosu

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

# OrderStatuses Tablosu

```
Id
Name
CreatedDate
UpdatedDate
IsActive
```

**AÇIKLAMA:** 

---

# PaymentDetails Tablosu

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

# ProductFieldCategoryFields Tablosu

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

# ProductFieldImageUrls Tablosu

```
Id
ImageUrl
CreatedDate
UpdatedDate
ProductFieldId
```

**AÇIKLAMA:** 

---

# ProductFields Tablosu

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

# Products Tablosu

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

# ProductSelections Tablosu

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

# Sellers Tablosu

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

# SellerTitles Tablosu

```
Id
Title
CreatedDate
UpdatedDate
SellerId
```

**AÇIKLAMA:** 

---

# ShoppingCarts Tablosu

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

# TaxDepartments Tablosu

```
Id
City
Town
Code
Name
```

**AÇIKLAMA:** 

---

# TicketDetails Tablosu

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

# Tickets Tablosu

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

# UserAddresses Tablosu

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

# Users Tablosu

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

---

#  Tablosu

```

```

**AÇIKLAMA:** 

---

#  Tablosu

```

```

**AÇIKLAMA:** 

---

#  Tablosu

```

```

**AÇIKLAMA:** 
