Bu konuda statik olan dosyaları (css,js,image) nasıl ekleriz ve kullanırız onu işleyeceğiz.👌
- Bu konuda öncelikle images yani fotoğraf ekleme işini göstereceğim.
- Daha sonra da css dosyasını eklemeyi.

Fotoğraflarımızı indirip wwroot dosyası oluşturup içine de img dosyası oluşturup içine atalım.
![[Pasted image 20250222223554.png]]

Sonra movie.cs dosyasına ` public string images { get; set; }` komutunu ekliyoruz.
Şimdi de HomeController.cs dosyasını da düzenleyelim.

```cs
    new movie 
    {
        Title = "BMW",
        Description =  "M3 GTR",
        Director = "Mehmet Huseyin Ozyilmaz",
        Players = new string[] {"Mehmet", "Huseyin", "Ozyilmaz"},
        images = "memoli.jpeg"
    },
    new movie
    {
        Title =  "Dodge",
        Description =  "Challenger",
        Director = "Murat Ozyilmaz",
        Players = new string[] {"Murat", "Ozyilmaz"},
        images = "muro.jpeg"
    },
    new movie {
        Title = "Mini",
        Description = "Cooper",
        Director = "Serpil Ozyilmaz",
        Players = new string[] {"Serpil", "Ozyilmaz"},
        images = "abla.jpeg"
    }
}; 
```
Şeklinde düzenleyerek imagesleri ekliyoruz.
 Ve son olarak da about.cshtml dosyamızın içini güncelliyoruz.
```html
@model List<movie>

<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
        <style>
            .film{
                border: 1px solid #000000;
                margin-bottom: 10px;
                padding: 10px;
            }
        </style>
    </head>
    <body>
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
    </body>
</html>
```

>[!NOTE] Düzenlenen Komutlar
>Burada style komutlarını yani css kodlarını ekledik. (style içerisindekiler)
>Ve image komutlarını ekledik. (`<img src="/img/@movie.images" alt="@movie.Title" />`)

VE EN ÖNEMLİSİ!!!
Statik dosyaları çalıştırmak izin ister.
>[!FAQ] Önemli
>Startup.cs dosyasına ` app.UseStaticFiles();`
>Bu komut ile dosyaya erişime izin veriyoruz.
>Böylelikle wwroot klasörünün içindeki img klasörünün içindeki dosyalara erişmiş oluyoruz.

wwwroot dosyası özel bir dosyadır.
Eğer başka bir şekilde kendimiz falan dosya oluşturuyorsak da şu sitede bulabiliriz:
[Site Linki](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/static-files?view=aspnetcore-5.0)

SON OLARAK ÇIKTIMIZ ŞU ŞEKİLDE:
![[Pasted image 20250222224613.png]]

Şimdi sırada css dosyamız var 🫡

Öncelikle css dosyamızı oluşturalım. Add-New Item- Show all tables- Style Sheet diyerek style.css dosyası oluşturuyoruz.
Şimdi css kodlarımızı style.css dosyamıza ekliyoruz. Şu şekilde oluyor içerisi:
```css

    .film {
    border: 1px solid #000000;
    margin-bottom: 10px;
    padding: 10px;
}


```

Daha sonra about.cshtml dosyamızın en başındaki style içerisindeki kodları silerek:
```html
        <link href="/css/style.css" rel="stylesheet" />

```
kodunu giriyoruz. Böylelikle css dosyamızı bağlamış olduk. Şimdi tekrardan çalıştırınca yine aynı çıktıyı aldık. Eğer sorun olsaydı çıktıda hata alırdık.

>[!NOTE] NOT
>Burada alınan bazı hatalar şu şekilde belki ileride karşılaşırsın :(
>`/css/style.css` yerine `css/style.css` kullanmak hataya yol açar.
>`.film üstünde body kısmına kod yazmak` 

.film üstüne body den kastım şu:
```css
body {
    .film {
    border: 1px solid #000000;
    margin-bottom: 10px;
    padding: 10px;
}
}

```
bu kod hatalıdır mesela 🤜

#statik
#css
#img
#asp #asp-core 
#dosya-ekleme

