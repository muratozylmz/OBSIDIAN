## Bu lab bize dönen hata mesajlarında bulunan açıkları kapsıyor.

Örneğin burp ile sayfa yakaladım. Elimde bir productId var. Burası sayı alıyor (1,2,3,4,...) Ben buraya string bir değer giriyorum. Sonra dönen sonuç:
![[Pasted image 20250317132256.png]]

TEMEL OLARAK BÖYLE...
### Peki bu işin biraz daha ilerlemiş hâli nasıl olur?
![[Pasted image 20250317133721.png]]

Burada link içerisinde bize dizini veriyor. Bu linki URL'e girerek dizine giriyoruz. Bu lab da böyle çözülüyor mesela. Bu işlemi Burp Suite'de sayfanın üzerine gelerek
`Engagement tools- Find comments`  ile bulduk, çözdük.


### Biraz daha kurcalarsak. 
Başka bir sitede yani labda bu sefer site üzerine gelerek:
`Engagement tools- Discover content` ile tarama yapıyoruz. ==Dizin taraması bu...

![[Pasted image 20250317134306.png]]

Burada /backup dizinini buluyoruz ve lab çözüldü.

