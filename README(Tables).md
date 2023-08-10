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

Bu tablo, ürün kategorilerini hiyerarşik bir şekilde organize edebilme yeteneği sağlar (ana kategoriler ve alt kategoriler). "MainCategoryId" alanı sayesinde bu ilişki kurulabilir. "Path" alanı, bir kategorinin tam olarak nerede olduğunu izlemek için kullanılabilir (örneğin, bir "Mobilya" kategorisinin "Ofis Mobilyaları" alt kategorisi gibi). "VatRate" alanı, bu kategoriye ilişkilendirilmiş bir vergi oranını saklar.

Bu tablo, ürün kategorileri ve bunlarla ilişkili bilgileri düzenlemek ve sorgulamak için kullanışlı olabilir.

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

Bu tablo, farklı kategorilerin benzer olduğu senaryoları yönetmek için kullanışlıdır. Örneğin, bir "Bilgisayar" kategorisi ile bir "Elektronik Cihazlar" kategorisi arasında eşdeğerlik olabilir, bu da "Bilgisayar" kategorisine ait ürünleri "Elektronik Cihazlar" kategorisi altında da görüntülemeyi mümkün kılar.

Bu tür bir tablo, ürün kategorileri arasında ilişkileri yönetmek ve benzer kategorileri gruplamak için kullanılabilir. "CategoryId" ve "EquivalentId" alanları aracılığıyla eşdeğer kategorileri belirleyebilir ve bu eşdeğerlikleri kullanarak sorgular yapabilirsiniz.

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

Bu tablo, özelleştirilmiş ürün kategori alanları eklemek için kullanışlıdır. Örneğin, bir "Giysi" kategorisi için "Beden", "Renk", "Kumaş Türü" gibi ekstra alanlar eklemek isteyebilirsiniz. Bu ekstra alanlar, ürünlerin daha ayrıntılı olarak kategorize edilmesine yardımcı olur.

"CategoryId" alanı sayesinde her ekstra alanın hangi kategoriye ait olduğu belirtilir, böylece her kategori için farklı ekstra alanlar tanımlayabilirsiniz. Bu tabloyu kullanarak ürün kategorilerinizi daha esnek ve özelleştirilebilir hale getirebilirsiniz.

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

Bu tablo, kullanıcıların yorumlarına resim ekleyebilme ihtiyacını karşılamak için kullanışlıdır. Örneğin, bir e-ticaret platformunda ürünler hakkında yapılan yorumlara resim eklemek isteyebilirsiniz. Bu tablo, yorumlara ilişkilendirilmiş resimlerin URL'lerini depolayarak, kullanıcıların yorumlarına görsel içerik eklemesine olanak tanır.

"CommentId" alanı sayesinde her resim URL'sinin hangi yorumla ilişkilendirildiğini belirtir, böylece hangi resmin hangi yorumla ilişkilendirildiğini takip edebilirsiniz. Bu tablo, yorumlara resim desteği eklemek için kullanışlı bir yapı sağlar.

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

Bu tablo, kullanıcıların yorumlara beğeni ekleyebilme ihtiyacını karşılamak için kullanışlıdır. Örneğin, bir sosyal medya platformunda veya bir forumda kullanıcıların yorumlara beğeni veya destek ifadesi eklemelerini isteyebilirsiniz.

"UserId" alanı sayesinde her beğeni işleminin hangi kullanıcı tarafından yapıldığını belirtir, böylece hangi kullanıcının hangi yorumu beğendiğini takip edebilirsiniz. "CommentId" alanı, beğeninin hangi yorumla ilişkilendirildiğini gösterir, bu sayede hangi yorumun kaç beğeni aldığını veya hangi yorumların popüler olduğunu gözlemleyebilirsiniz. Bu tablo, yorumlara beğeni desteği eklemek için kullanışlı bir yapı sağlar.

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

Bu tablo, müşterilerin siparişlerle ilgili yorumlar yapabilmelerini ve bu yorumlara puan vererek ürün veya hizmetin kalitesini değerlendirebilmelerini sağlar. Örneğin, bir e-ticaret platformunda müşteriler, sipariş verdikleri ürünler veya hizmetler hakkında yorumlar ve puanlar (rating) bırakabilirler.

"OrderId" alanı sayesinde her yorumun hangi siparişle ilişkilendirildiğini belirtir, böylece hangi yorumun hangi siparişe ait olduğunu takip edebilirsiniz. Bu tablo, müşteri geri bildirimlerini kaydetmek ve gelecekteki geliştirmeler için değerlendirme yapmak için kullanışlı bir yapı sağlar.

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

Bu tablo, siparişlerin faturalarını saklamak için kullanışlıdır. Her bir fatura, bir siparişe ait olup siparişin detaylarını ve ödeme bilgilerini içerebilir. "OrderId" alanı, her faturanın hangi siparişe ait olduğunu belirtir, böylece hangi siparişin hangi faturaya sahip olduğunu takip edebilirsiniz. Bu tablo, finansal işlemleri ve fatura bilgilerini yönetmek için kullanışlı bir yapı sağlar.

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

Bu tablo, siparişleri yönetmek ve takip etmek için kullanılır. Her siparişin kimlik bilgisini, ürünün satış fiyatını, stok miktarını, teslimat adresini ve diğer detayları içerir. "UserId" alanı sayesinde hangi kullanıcının hangi siparişi verdiğini takip edebilirsiniz. "OrderStatusId" alanı, siparişin durumunu gösterir, böylece siparişin nerede olduğunu izleyebilirsiniz. Bu tablo, e-ticaret veya sipariş tabanlı bir platformun sipariş yönetimi için kullanışlı bir yapı sağlar.

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

Bu tablo, siparişlerin farklı durumlarını takip etmek ve yönetmek için kullanılır. Siparişin hangi aşamada olduğunu belirtir ve bu aşamaları adlandırır. "IsActive" alanı, bir sipariş durumunun geçerli olup olmadığını belirtir. Örneğin, bir sipariş durumu artık kullanılmıyorsa, bu alanı pasif hale getirerek bu durumun yeni siparişlerde seçilememesini sağlayabilirsiniz.

Bu tablo, siparişlerin yönetimi ve izlenmesi için kullanışlı bir yapı sağlar ve sipariş durumlarını tanımlar.

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

Bu tablo, siparişlerin ödeme detaylarını takip etmek için kullanılır. "OrderId" alanı sayesinde hangi siparişin hangi ödeme detaylarına sahip olduğunu belirleyebilirsiniz. "PaymentType" alanı, ödeme yöntemini belirtir, böylece hangi ödeme yöntemleri kullanıldığını gözlemleyebilirsiniz. Bu tablo, ödeme işlemlerini yönetmek ve izlemek için kullanışlı bir yapı sağlar.

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

Bu tablo, ürünlerin özellikleri ile kategori alanları arasındaki ilişkiyi yönetmek için kullanışlıdır. Örneğin, bir e-ticaret platformunda "Renk", "Beden", "Malzeme" gibi ürün özellikleri ile "Kumaş Türü", "Boyut Seçenekleri" gibi kategori alanlarını ilişkilendirmek isteyebilirsiniz.

"ProductFieldId" alanı, ürün özelliğini belirler ve hangi ürün özelliği ile ilişkilendiğini gösterir. "CategoryFieldId" alanı, kategori alanını belirler ve hangi kategori alanı ile ilişkilendiğini gösterir. "Value" alanı, bu iki alan arasındaki ilişkinin değerini saklar.

Bu tablo, ürün ve kategori bilgilerini daha ayrıntılı ve esnek bir şekilde yönetmek için kullanışlı bir yapı sağlar.

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

Bu tablo, ürün özelliklerine ait resimleri yönetmek ve saklamak için kullanışlıdır. Örneğin, bir e-ticaret platformunda "Siyah renk" veya "XL beden" gibi ürün özellikleri için ilişkilendirilmiş resimleri bu tabloda saklayabilirsiniz. Her resim, bir ürün özelliğine aittir ve bu tablo sayesinde bu ilişkiyi sağlayabilirsiniz.

"ProductFieldId" alanı sayesinde hangi ürün özelliği ile ilişkilendirilmiş bir resmin olduğunu belirtir, böylece her ürün özelliğine ait resimleri kolayca bulabilirsiniz. Bu tablo, ürünlerin daha çekici ve ayrıntılı bir şekilde gösterilmesi için kullanışlı bir yapı sağlar.

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

Bu tablo, ürün özelliklerini yönetmek ve bu özelliklerin detaylarını saklamak için kullanışlıdır. Ürünlerin farklı özelliklerini, stok durumlarını, fiyatlarını, ana resimlerini ve diğer detaylarını bu tablo üzerinden tutabilirsiniz.

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

Bu tablo, bir e-ticaret platformunda veya ürün yönetimi gerektiren başka bir sistemde ürünleri saklamak için kullanılır. "Name" alanı, ürünün adını belirtir, böylece ürünleri adlarına göre kolayca bulabilirsiniz. "SellerId" alanı, ürünü satan satıcının kimliğini gösterir, böylece hangi ürünün hangi satıcıya ait olduğunu takip edebilirsiniz.

Bu tablo, ürünleri yönetmek, satıcıları belirtmek ve ürünlerin temel bilgilerini tutmak için kullanışlı bir yapı sağlar.

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

Bu tablo, ürün seçeneklerini yönetmek ve bu seçeneklerin hiyerarşisini tanımlamak için kullanılır. Örneğin, bir e-ticaret platformunda "Renk Seçenekleri" veya "Beden Seçenekleri" gibi ürün seçenekleri bu tabloda saklanabilir. Her bir ürün seçeneği, belirli bir ürünle ilişkilendirilmiştir.

"ProductId" alanı sayesinde hangi ürünün hangi ürün seçeneklerine sahip olduğunu belirtir, böylece ürünlerin farklı seçeneklerini kolayca bulabilirsiniz. "MainProductSelectionId" alanı, bir ürün seçeneğinin bir ana ürün seçeneği ile ilişkilendirilip ilişkilendirilmediğini belirtir, böylece ürün seçenekleri arasında hiyerarşi oluşturabilirsiniz.

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

Bu tablo, satıcıların kimlik bilgilerini, hesap durumlarını, şifre doğrulamalarını, ortalama değerlendirmelerini ve genel hesap bilgilerini saklamak için kullanılır. "TaxDepartmentId" alanı ile satıcıların vergi dairesine bağlı olduğu bilgisi tutulabilir ve "IsActive" alanı ile satıcı hesaplarının etkinliği kontrol edilebilir. Bu tür bir tablo, bir e-ticaret platformunda veya bir pazaryerinde satıcıların hesap yönetimi için kullanılabilir.

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

Bu tablo, satıcı unvanlarını yönetmek ve bu unvanların hangi satıcıya ait olduğunu takip etmek için kullanılır. Örneğin, bir e-ticaret platformunda farklı satıcıların farklı unvanları olabilir ve bu unvanları bu tablo üzerinden saklayabilirsiniz. "SellerId" alanı, her bir unvanın hangi satıcıya ait olduğunu belirtir, böylece satıcıların farklı unvanlarını takip edebilirsiniz. Bu tür bir tablo, satıcıların organizasyon içindeki rol ve pozisyonlarını tanımlamak ve yönetmek için kullanışlıdır.

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

Bu tablo, kullanıcıların alışveriş sepetlerini yönetmek için kullanılır. "UserId" alanı sayesinde her kullanıcının kendi sepeti olabilir, ve bu sepetlerde farklı ürün alanlarını (ProductFieldId) ekleyebilirler. "Stock" alanı, sepete eklenen ürünün miktarını belirtir. Bu tür bir tablo, e-ticaret platformlarında kullanıcıların alışveriş sepetlerini yönetmek ve bu sepetlerdeki ürünleri takip etmek için kullanılır.

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

Bu tablo, vergi dairesi bilgilerini yönetmek ve bu bilgileri şehir ve ilçe düzeyinde sınıflandırmak için kullanılır. Vergi daireleri farklı şehirlerde ve ilçelerde yer alabilir, bu nedenle "City" ve "Town" alanları bu ilişkiyi belirtir. Vergi dairesi kodu ("Code") benzersiz bir kimlik sağlar ve bu kodla bir vergi dairesi kolayca tanımlanabilir. "Name" alanı, vergi dairesinin adını içerir ve daha anlaşılır bir şekilde temsil eder.

Bu tür bir tablo, bir organizasyonun vergi dairesi bilgilerini yönetmek için veya bir uygulamada vergi dairesi seçimi veya ilişkilendirmesi gerektiğinde kullanılır.

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

Bu tablo, kullanıcıların veya satıcıların destek taleplerinin ayrıntılarını yönetmek ve bu talepleri ilgili kullanıcılara veya satıcılara bağlamak için kullanılır. "TicketId" alanı, her bir destek talebinin kimliğini belirtir ve bu sayede her talebin ayrıntıları aynı talebe bağlı olarak saklanır. "SellerId" ve "UserId" alanları, talebin ilgili olduğu kullanıcı veya satıcıyı belirtir ve herhangi biri veya her ikisi de boş geçilebilir. "Content" alanı, talebin ayrıntılarına ait metin içeriğini içerir. Bu tür bir tablo, bir müşteri destek sistemi veya yardım masası uygulamasında destek taleplerini yönetmek için kullanılır.

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

Bu tablo, kullanıcıların ve satıcıların destek taleplerini yönetmek ve bu talepleri ilgili kullanıcılara veya satıcılara bağlamak için kullanılır. "SellerId" ve "UserId" alanları, talebin ilgili olduğu kullanıcı ve satıcıyı belirtir. "Subject" alanı, talebin başlığını içerir ve kullanıcıların veya satıcıların hangi konuyla ilgili bir destek talebi gönderdiklerini ifade eder. "CreatedDate" alanı, talebin ne zaman oluşturulduğunu gösterir.

Bu tür bir tablo, bir müşteri destek sistemi veya yardım masası uygulamasında destek taleplerini yönetmek için kullanılır. Talepleri kaydetmek, ilgili kullanıcı veya satıcıya yönlendirmek, ve taleplerin durumunu izlemek için bu tür bir tablo kullanışlıdır.

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

Bu tablo, kullanıcıların farklı adreslerini yönetmek için kullanılır. Her kullanıcıya birden fazla adres ekleyebilir ve bu adresler farklı amaçlar için (ev, iş, kargo adresi, vb.) tanımlanabilir. Adresler, kullanıcının hangi şehir ve ilçede bulunduğunu, tam adresi, posta kodunu ve diğer detayları içerir. Bu tür bir tablo, e-ticaret platformları, kargo hizmetleri ve benzeri uygulamalarda kullanıcıların farklı teslimat adresleri ve iletişim bilgilerini saklamak için kullanışlıdır.

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

Bu tablo, kullanıcıların temel bilgilerini (ad, e-posta, telefon numarası), şifrelerinin güvenli şekilde saklanması (şifre karması ve tuz), hesap durumu (aktif veya pasif), ve hesap oluşturma/güncelleme tarihlerini saklamak için kullanılır. Bu tür bir tablo, kullanıcı hesapları yönetimi ve yetkilendirme işlemleri için kullanılır. Özellikle web siteleri, uygulamalar, üyelik sistemleri ve güvenli kimlik doğrulama işlemleri gerektiren sistemlerde bu tür bir tablo kullanışlıdır.

---

