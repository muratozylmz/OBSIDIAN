#### Bu not farklı sayfada partial views kullanmak istediğimiz için

Her sayfada aynı viewler olsun istemiyorsak,
Bunun için SECTİON kullanırız.
Şimdi kodlarla anlatmaya çalışalım.

İlk önce `_menu.cshtml` kısmını diyelim ki sadece index sayfamda kullanmak istiyorum diyelim. 
Bunun için index sayfamızın en başına şu komutu ekliyoruz:

```cs
@section menu
{
    @await Html.PartialAsync("_menu")
}
```
Daha sonra `_Layout.cshtml` kodumuza da şunu ekliyoruz:
```cs
 @RenderSection("menu", false)
```

>[!NOTE] NOT
>Burdaki false değeri = Diğer sayfalarda zorunlu olmasın demek

Şu anda çalıştırırsak sadece index sayfamızda navbar altında kocaman menü görürüz.
![[Pasted image 20250223011621.png|300]]
Diğer sayfalarda üstteki kategori kısmı bulunmuyor.

---
##### Peki sadece menu olan section'larda layout çalışsın istersek?

Yani tüm sayfalarda çalışmasın dedik. Sayfa üzerinden düşündük. Layout açısından bakalım duruma. Kodlarla anlatalım.
Şimdi ben istiyorum ki eğer section'da menu varsa kategori göstersin. Yoksa göstermesin. Bunun kodu: 
```cs
     @if (IsSectionDefined("menu"))
     {
         <div class="row">
             <div class="col-md-3">
                 @RenderSection("menu",false)
             </div>
             <div class="col-md-9">
                 @RenderBody()
             </div>
         </div>
     }
     else
     {
         <div class="row">
             <div class="col-md-12">
                 @RenderBody()
             </div>
         </div> 
     }
```

Eğer menu varsa üstteki kod yani menu gösterilecek. Yoksa gösterilmeyecek.
index'de 
```cs
@section menu
{
    @await Html.PartialAsync("_menu")
}
```
Bu kod bulunuyor. Çalıştırdığımızda sadece index sayfamızda kategori var. 
Diğer sayfalarda bulunmadı. 

#section #kullanışlı 
#asp #asp-core 