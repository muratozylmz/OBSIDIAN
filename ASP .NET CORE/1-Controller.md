Controller oluştururken: 
```cs
endpoints.MapControllerRoute(
	name: "isim veriyoruz."
	pattern: "dosya yolu (URL'de)"
	defaults: new {controller = "controller ismi", action = "Fonksiyon ismi"}
);
``````

Bu manuel yazımdı. 
Şimdi otomatik olarak kod:
#default-routing
```cs
endpoints.MapControllerRoute(
	name: "home"
	pattern: "{controller}/{action}"
);
```

otomatik olarak gidecektir.
VEYA;

```cs
endpoints.MapControllerRoute(
	name: "home"
	pattern: "{controller=Home}/{action=Index}"
);
```

kodu ile ilk açıldığındaki sayfayı belirtmiş olabiliriz. 

#default-routing 


> [!NOTE] Not
> Burada dikkat edilmesi gereken bir şey var:
> `pattern:"{controller=Home}"` kısmı bitişik yazılmalıdır.
> `pattern: "{controller = Home}"` şeklinde yazımı yanlıştır.



#controller
#asp
#asp-core