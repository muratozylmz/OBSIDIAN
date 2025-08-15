### Burada her bir bootstrap i dosyalar için sürekli yazmak yerine tek bir dosyada hepsinde kullanmayı göstereceğim. 
#### Hatta html temel komutlarını bile sileceğiz 🫡 Ve tüm adımları detaylı anlatacağım.


Öncelikle "Shared" isimli klasör oluşturuyoruz.
İçerisine de sağ tıkla new-item- Razor Layout oluşturuyoruz.

Ve ayrıca Views klasörü içerisine Razor View Start dosyası oluşturuyoruz. 
İsmi `_ViewStart.cshtml` oluyor.

```html
<!DOCTYPE html>

<html>
<head>
    <meta name="viewport" content="width=device-width" />
    <title>@ViewBag.Title</title>
</head>
<body>
    <div>
        @RenderBody()
    </div>
</body>
</html>
```
Komutları bizi karşılıyor. Şimdi içini şu şekilde düzenliyoruz.
```html
<!DOCTYPE html>

<html>
<head>
    <meta name="viewport" content="width=device-width" />
    <title>@ViewBag.Title</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    <link href="/css/style.css" rel="stylesheet" />
</head>
<body>
    <nav class="navbar bg-dark border-bottom border-body" data-bs-theme="dark">
        <div class="container-md">
            <a class="navbar-brand" href="#">FİLMLER LİSTESİ</a>
        </div>
    </nav>
    <div>
        @RenderBody()
    </div>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
</body>
</html>

```

>[!NOTE] NOT
>Buradaki `@RenderBody()` kodu sayfadaki kalan kısımların komutlarıdır.


Burada yapılanlar: 
- style kısımlarını eklemek 
- bootstrap kısmındaki kodları ekledik.
- js bootstrap kodlarını ekledik.
- Son olarak da `_ViewStart.cshtml` kodunun içine :
  ```cs
- @{
  Layout = "_Layout";
}

```
kodunu ekledik. Burada belirtilen dosyayı tanımladık.

Son durumda kodlarımızın güncel hali ;
###### about.cshtml:
```html
@model List<movie>
    <h1>Filmlerin Listesi</h1>
    <div id="filmler">
        @foreach (var movie in Model)
        {
        <div class="film">
            <img src="/img/@movie.images" alt="@movie.Title" />
            <p>@movie.Title</p>
            <p>@movie.Description</p>
            <p>@movie.Director</p>
            <p>
                <ul>
                    @foreach (var player in movie.Players)
                    {
                        <li>@player</li>
                    }
                </ul>
            </p>
        </div>
        }
    </div>
```

Baş kısımlar çıkmış oldu aradan... 

###### index.cshtml:
```html
@model WebApplication1.Web.Models.movie
    <h1>Filmlerin Listesi</h1>
    <div id="filmler">
        <div class="film">
            <p>@Model.Title</p>
            <p>@Model.Description</p>
            <p>@Model.Director</p>
            <p>
                <ul>
                    @foreach (var player in Model.Players)
                    {
                        <li>@player</li>
                    }
                </ul>
            </p>
        </div>
    </div>
```
Bu sayfa da aynı şekilde...

>[!FAQ] PEKİİİİİİ
>EĞER HER SAYFADA AYNI TASARIM KULLANMAK İSTEMİYORSAK

Bunun için bir tane daha `_Layout2.cshtml` dosyası oluşturuyoruz.
İçini de şu kod yerine 
```html
    <nav class="navbar bg-dark border-bottom border-body" data-bs-theme="dark">
```

Bu kodu ekliyoruz:

```html
    <nav class="navbar" style="background-color: aqua;">
```
Şimdi de sadece index.cshtml sayfasında kullanmak istiyoruz diyelim;
index.cshtml sayfasına şu kodu ekliyoruz:
```cs
@{
    Layout = "_Layout2";
}
```
Son görünüm şu şekilde yani :
![[Pasted image 20250223003646.png]]

Şimdi index sayfamızın üst kısmı aqua renginde diğer sayfalar dark tema da denendi ve onaylandı.

#mükemmel #kullanışlı 
#güzel #iyi 
#perfect #asp #asp-core #muhteşem #beğendim #sevdim