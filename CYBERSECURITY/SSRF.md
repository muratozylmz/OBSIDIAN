
### Bu zafiyet temel mantığı şu şekildedir:  **Bir saldırganın bir web uygulamasını veya API'yi dahili kaynaklara isteklerde bulunmaya yönlendirmesiyle oluşan bir güvenlik açığı türüdür** ve bu da yetkisiz erişime, veri ifşasına, sistem ihlaline ve uzaktan kod yürütülmesine yol açabilir.

Yani URL'de değişiklik yapabiliyoruz. Örneğin;
![[Pasted image 20250325134001.png]]

Girmemiz gereken bilgileri POST'da tek bir açık bulunan yere giriyoruz.

##### Gidilen URL'de açık port olabilir:
http://192.168.0.238:8080/admin
Bu mesela direkt olarak gösteriyor admin panelini. 238 kısmını da brute-force ile buldum.
