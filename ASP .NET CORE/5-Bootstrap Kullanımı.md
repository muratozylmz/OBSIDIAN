### Bu konuda bootstrap kullanmayı göstereceğim.

- Bootstrap için site kullanıyoruz. [Site](https://getbootstrap.com/docs/5.3/getting-started/introduction/)
- Bu site ile bootstrap kullanımını anlatacağım.

Öncelikle sitemize giriyoruz. 
```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
```

Bu kodu style.css dosyasını tanımladığımız yerin hemen üstüne yapıştırıyoruz.
body etiketinin hemen üstüne de:
```html
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
```

Bu kodu yapıştırıyoruz bu da javascript için...

Son olarak da:
```html
<nav class="navbar bg-dark border-bottom border-body" data-bs-theme="dark">
    <div class="container-md">
        <a class="navbar-brand" href="#">FİLMLER LİSTESİ</a>
    </div>
</nav>
```
kodunu body etiketinin giriş kısmının hemen altına yapıştırıyoruz.
Bu kod sayesinde kodların son durumu yer olarak şöyle:

![[Pasted image 20250222234828.png]]

Şimdi de çalıştıralım. Son duruma birlikte bakalım...
![[Pasted image 20250222234911.png| 300]]
En üstte arkası koyu "FİLMLER LİSTESİ" yazan navbar oluşturduk.

>[!NOTE] Not
>Burada kodları siteden kopyala yapıştır yaptık. Sorunsuz şekilde çalıştı :D 

---
#bootstrap
#asp #asp-core 