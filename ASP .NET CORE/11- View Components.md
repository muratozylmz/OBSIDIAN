### Biz sürekli model çağırma işleri ile uğraşıyoruz
Bu durumu ortadan kaldırmak için View Components kullanırız.
Sürekli olarak model çağırma işlemleri böylelikle her sayfada otomatik olarak çağralacaktır.

#### Adımlar:

- Öncelikle ViewComponents adında bir klasör ekliyoruz. Genel dosya konumuna
- Daha sonra bunun içerisine de `GenresViewComponents.cs` dosyası ekliyoruz. (Class)
-  Bu klasör içerisine sürekli olarak kullanacağımız Model kodlarını yazıyoruz:
	- ![[Pasted image 20250311123603.png]]
-  Daha sonra SHARED klasörü içerisine COMPONENTS klasörü açığı onun da içine `Default.cshtml` dosyası açıyoruz.
	- ![[Pasted image 20250311123724.png]]
- Burada oluşturduğumuz model içerisindeki kodları çağırmış oluyoruz.

VE İŞLEMLERİ BİTİRMİŞ OLUYORUZ....

##### Bu noktadan sonra daha önce oluşturduğumuz turListesi kodlarını diğer dosyalardan siliyoruz sadece burada kalıyor.

