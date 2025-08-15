#asp 
#asp-core 

View ile oluşturulan dosya(HTML formatında) çağrılır.

Controller sayfamızda:
```cs
public IActionResult Index()
{
	return View();
}
```
kodlarını ekledikten sonra 
👌View/Home klasörü içerisinde view dosyamızı oluşturmamız gerekiyor. Burada dosya ismimiz Index çünkü IActionResult ismimiz İndex.

---
Oluşturduğumuz .cshtml uzantılı dosyamızın içerisinde HTML kodları olacak ve sayfamızı çalıştırdığımızda da localhost:8000/home 
dendiğinde home içerisinde Index çalışacak.

---
localhost:8000/home/about olduğunda home klasörü içerisinde oluşturduğumuz about.cshtml dosyamızı çalıştıracaktır.
#view

---
## **Daha Önemli Olan Kısım**

#### Dinamik Olarak View Kullanımı

Öncelikle HTML içerisinde kodlarımız yazıyoruz.

```html
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
</head>
<body>
    <h1>Filmlerin Listesi</h1>
    <div id="filmler">
        <div class="film">
            <p>Film Başlığı</p>
            <p>Film Açıklaması</p>
            <p>Filmin Yönetmeni </p>
            <p>
                <ul>
                    
                    {
                        <li>Aamir Khan</li>
                        <li>Kuzey Güney</li>
                    }

                </ul>
            </p>
        </div>
    </div>
</body>
</html>
```
şeklinde temel bir HTML kodları oluşturduk.

---
Şimdi controller sayfamızda Index kısmımızı yazıyoruz:

```cs
public IActionResult Index()
{
    string filmBasligi = "Marvel";
    string filmAciklama = "Süper Kahramanlar";
    string filmYonetmen = "Murat Ozyilmaz";
    string[] oyuncular = { "Aamir Khan", "Kuzey Guney" };

    ViewBag.FilmBasligi = filmBasligi;
    ViewBag.FilmAciklama = filmAciklama;
    ViewBag.FilmYonetmen = filmYonetmen;
    ViewBag.Oyuncular = oyuncular;

    return View();
}
```
Burada view içerisinde stringler ile her bir değeri oluşturduk. Geniş bir şekilde düşünürsek açıklama kısımlarını formlardan çekebiliriz. 👌

Daha sonra oluşturduğumuz kodlara göre HTML sayfamızı düzenliyoruz.

```html
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
</head>
<body>
    <h1>Filmlerin Listesi</h1>
    <div id="filmler">
        <div class="film">
            <p>@ViewBag.FilmBasligi</p>
            <p>@ViewBag.FilmAciklama</p>
            <p>@ViewBag.FilmYonetmen</p>
            <p>
                <ul>
                    @foreach (var item in ViewBag.Oyuncular)
                    {
                        <li>@item</li>
                    }

                </ul>
            </p>
        </div>
    </div>
</body>
</html>
```

Böylelikle controller sayfamızdaki bilgileri HTML sayfamıza çekmiş olduk. 

#viewbag

View.Bag = ile dinamik olarak view kullanımını gördük.
#dinamik-view

---
Tüm bu kodları çalıştırınca çıktımız:
![[Pasted image 20250222154845.png|300x300]]

