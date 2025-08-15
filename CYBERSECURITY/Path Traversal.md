Bu açığın meşhur diğer ismi ==LOCAL FILE INCLUSION (LFI).


>[!FAQ] MDİ Notu
>Biz varlığını şu şekilde anlarız:
>Bize 30.png isimli dosya döndürüldüğünde ../images/30.png giriyoruz.
>Bize geri dönüyorsa bu zafiyetin varlığı meydana çıkıyor.
>(../image/30.png olabilir, ....//images/30.png olabilir.)

#### LFI'ın 4 türü vardır:
- ../../../etc/passwd  temel payload
- ....//....//....//etc/passwd ileri düzey payload
- ..%252f..%252f..%252fetc/passwd bypass'lı payload
- ../../../etc/passwd%00.png  dosya uzantısı içerisine enejkte payload


Burada bize gerekli olan şeylerden birisi 
![[Pasted image 20250316140429.png]]

>[!WARNING] Uyarı
>= işareti olması gereklidir. 
>= işaretinden sonra ../../ şeklinde dizinler arası geçiş yapılır.

![[Pasted image 20250316140558.png |300x300]]

Daha sonra bu şekilde sonuç bize döner.

### BAŞKA BİR YOL ? 

![[Pasted image 20250316141150.png]]

Bu noktada ../../ yapmamıza illaki gerek yoktur. Bazen basit mantık düşünmekte iyidir.

# ==BYPASS YÖNTEMLERİ

....//....//....//etc/passwd

# E TABİ Bİ DE URL ENCODE-DECODE OLAYLARI VAR 😁

### Payload = ../../../etc/passwd
Bunu bir kere encode (URL Encode) edersek : 
..%2F..%2F..%2F..%2Fetc/passwd

Bu payload'ı da encode edersek: 
..%252f..%252f..%252fetc/passwd
Şeklinde bypass yöntemleri ortaya çıkıyor. 

### BAŞKA BİR SEÇENEK
![[Pasted image 20250316143258.png]]
Böyle bir durumda:

![[Pasted image 20250316143314.png]]
Şeklinde bir payload işimizi görür.
![[Pasted image 20250316143339.png|300x300]]

#### SON YOLUMUZ:

![[Pasted image 20250316143617.png]]
Şeklinde bir isteğimiz var. En zor ve en akılalmaz olarak bir yolumuz var. 
![[Pasted image 20250316143642.png]]

Dosya yolu içerisine enjekte ediyoruz.



