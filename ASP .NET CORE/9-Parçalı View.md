#### Bu konuda Viewleri parçalı olarak nasıl gösteririz. Onu anlatacağım.

Öncelikle Viewleri parçalı olarak tanımlamak için View dosyası oluşturalım.
Shared klasörünün üstüne sağ tık ile sırasıyla:
Add-View-Razor view empty
İsmini de `_movie.cshtml` yaptım. 
Şimdi burada filmlerin yani içeriklerin olduğu kısmı bootstrap ile de güncelleme yaparak kodlarını aldım.
```html
@model movie


<div class="card mb-3" style="max-width: 540px;">
    <div class="row g-0">
        <div class="col-md-4">
            <img src="/img/@Model.images" class="img-fluid rounded-start" alt="@Model.Title">
        </div>
        <div class="col-md-8">
            <div class="card-body">
                <h5 class="card-title">@Model.Title</h5>
                <p class="card-text">@Model.Description</p>
                <p class="card-text"><small class="text-body-secondary">@Model.Director</small></p>
            </div>
        </div>
    </div>
</div>

```
Şimdi bu kodları kullacanağız.
`index.cshtml` :
```html
@model WebApplication1.Web.Models.movie


@section menu
{
    @await Html.PartialAsync("_menu")
}

    <h1>Filmlerin Listesi</h1>
    <div id="filmler">
        @await Html.PartialAsync("_movie",Model)
    </div>

```
Burada içeriği `@await Html.PartialAsync("_movie",Model)` komutu ile çağırıyoruz.
`about.cshtml` ise: 
```html
@model List<movie>

    <h1>Filmlerin Listesi</h1>
    <div id="filmler">

        @foreach (var movie in Model)
        {
           @await Html.PartialAsync("_movie",movie)
        }
    </div>
```
Şeklinde oldu. 

>[!FAQ] Uyarı
>Burada birinde ,Model diğerinde ise ,movie kullandık. Bunun sebebi:
>İlk başta zaten Model'den çektik. Ama ikinci kısımda `foreach` içerisinde Model'in itemi movie olduğu için movie olarak çağırdık!!!


#parçalı-view
#asp #asp-core 
