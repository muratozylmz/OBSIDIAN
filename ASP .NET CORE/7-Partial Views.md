#### Bu konumuz layout içindeki kısımları farklı dosyalar üzerinden çekmek
Bunun için await'i kullanacağız. Uygulama üzerinde gösterelim. 
Öncelikle `_Layout.cshtml` dosyamızın içindeki nav kısmını full şekilde kopyalıyoruz.
Dosyamızı oluşturalım.

Shared klasörüne sağ tıklayarak
view seçelim. 
razor empty diyelim.
ismini `_navbar.cshtml` olarak değiştirelim.
İçerisine kodu yapıştıralım.
```html
<nav class="navbar bg-dark border-bottom border-body" data-bs-theme="dark">
    <div class="container-md">
        <a class="navbar-brand" href="#">FİLMLER LİSTESİ</a>
    </div>
</nav>
```
Kaydedelim. Şimdi `_Layout.cshtml` dosyamıza gidelim.
Kodun içini kopyalayayım tamamını almayayım. 
```cs
<body>
    @await Html.PartialAsync("_navbar");
    <div>
        @RenderBody()
    </div>
```

```cs
@await Html.PartialAsync("_navbar");
```
kodunu eklemiş olduk. Bu kodu ekledikten sonra çalıştırırsak kodumuz başarılı bir şekilde çalışır.

>[!NOTE] NOT
>Burada `await` komutunu alt alta iki kere kullanırsak 2 tane navbar oluşur.

Burada notlar daha da genişletilebilir. Tamamen senin hayaline kalmış. İstersen:
- Header kısmını ekle 
  `@await HtmlPartialAsync("_header")` ile çağırıp `_Layout.cshtml` dosyasına eklersin.
- Ekleyeceğin yeri yazarsın.
- Css ekleyebilirsin.
- Daha nicelerine senin hayaline ve aklına kalmış

Sayfamızı biraz daha süslememiz gerekiyor bir sonraki ders notları için :(
Şu şekilde süsledim:
```cs
    @await Html.PartialAsync("_navbar");
    <div class=" container mt-3">
        <div class="row">
            <div class="col-md-3">
                @await Html.PartialAsync("_menu")
            </div>
            <div class="col-md-9">
                @RenderBody()
            </div>
        </div>
    </div>
```
Böylelikle sayfanın sağ tarafında bi kategorimiz var. Bunu `_menu.cshtml` den alıyor. 
#partial-views #asp #asp-core #kullanışlı