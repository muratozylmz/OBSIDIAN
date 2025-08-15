Model ile de verileri getirme işlemleri yapılabilir.
- Öncelikle model dosyası için `class` oluşturuyoruz.
- Daha sonra içerikleri tek tek tanımlıyoruz.

```cs
namespace WebApplication1.Web.Models
{
    public class movie
    {
        public string Title { get; set; }
        public string Description { get; set; }
        public string Director { get; set; }
        public string[] Players { get; set; }
    }
}

```
Şimdi HomeController.cs dizininde değişiklikler yapıyoruz.
- Öncelikle en üstte model için kullanılan namespace'i home controller sayfamızın en başına ekliyoruz.
- Daha sonra kodlarımızı şu şekilde güncelliyoruz:
```cs
public IActionResult Index()
{
    string filmBasligi = "Marvel";
    string filmAciklama = "Süper Kahramanlar";
    string filmYonetmen = "Murat Ozyilmaz";
    string[] oyuncular = { "Aamir Khan", "Kuzey Guney" };

    var m = new movie();
    m.Title = filmBasligi;
    m.Director = filmYonetmen;
    m.Description = filmAciklama;
    m.Players = oyuncular;



    return View(m);
}
```
Burada Modelimizi kullanarak OOP yardımıyla nesne oluşturup atadık. 
>[!NOTE] Not
>🤜view içerisine m (modelin m'si) eklemeyi unutmuyoruz.

Ve son olarak HTML dosyamızın içini güncelliyoruz.
```html
@model WebApplication1.Web.Models.movie

<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
</head>
<body>
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
</body>
</html>
```


>[!NOTE]
>Burada önemli olan şeylerin bir tanesi ilk satırda bulunan `@model WebApplication1.Web.Models.movie` satırını eklemek.
>"WebApplication1.Web.Models.movie" tamamen dosya oluşturduktan sonra alınan namespace bilgileridir.


---
### Liste Şeklinde Models Kullanımı 

Burada birden çok listeyi barındıran modelleri çağırmak için kullanılacak kodları göstereceğim:
- Kullanacağımız sayfaya gitmeden önce HomeController.cs:

```cs
public IActionResult About()
{
    var filmListesi = new List<movie>()
    {
        new movie 
        {
            Title = "Dağ 2",
            Description =  "Savaş Filmi",
            Director = "Murat Ozyilmaz",
            Players = new string[] {"Kuzey Güney", "Berat Albayram"}
        },
        new movie
        {
            Title =  "Savaşçı",
            Description =  "Savaş Filmi",
            Director = "Murat Ozyilmaz",
            Players = new string[] {"Kuzey Abbas", "Berat Albayram"}
        },
        new movie {
            Title = "DAYI",
            Description = "Kabadayı Filmi",
            Director = "Murat Ozyilmaz",
            Players = new string[] {"UFUK", "Berat Albayram"}
        }
    };  

    return View("About", filmListesi);
}
```

Burada kullanılacak kodlar verilmiştir.
`new List<movie>` ile nesne oluşturup aşağıda tanımlıyoruz. 

```html
@model List<movie>

<html xmlns="http://www.w3.org/1999/xhtml">
    <head><title></title></head>
    <body>
    <h1>Filmlerin Listesi</h1>
    <div id="filmler">

        @foreach (var movie in Model)
        {
        <div class="film">
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

>[!NOTE] NOT
>Burada ilk satır kullanım şekli normalde:
>`@model List<WebApplication1.Web.Models.movie>` şeklindedir. Fakat biz ayrıca bir "IMPORT VIEW" dosyası oluşturduk.
>İçeriği şu şekilde: 
>`@using WebApplication1.Web.Models` burada modelin namespace'sini kullandık. Sürekli çağırmak yerine burada tanımlayarak kodumuz şuna döndü:
>`@model List<movie>` şeklinde oldu.

>[!INFO] Ayrıca
>Burada `model` olarak değil de `movie`  olarak çağırdık!!!

#models
#asp 
#asp-core 

---

