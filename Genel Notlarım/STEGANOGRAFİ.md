`steghide --extract -sf <dosya>`

`stegcracker <dosya>`

`outguess`

### STEGSNOW
 **-C**      Verileri gizliyorsa sıkıştır, çıkarıyorsa sıkıştırılmamış hale getir.
       **-f ** mesaj dosyası
              Bu dosyanın içeriği giriş metin dosyasında gizlenecektir.
       **-l ** line-len 
              Boşluk eklerken, **stegsnow** her zaman bu değerden daha kısa satırlar üretecektir. Varsayılan olarak
              80 olarak ayarlanmıştır.
       **-m ** mesaj-dizisi
              Bu dizenin içerikleri giriş metin dosyasında gizlenecektir. Yeni bir satır olmadığı sürece,
              bir şekilde dizeye dahil edilmişse, mesaj çıkarıldığında yeni bir satır yazdırılmayacaktır.
       **-p ** şifre
              Bu ayarlanırsa, veriler gizlenirken bu parola ile şifrelenecek veya şifresi çözülecektir.
              çıkarma sırasında.
       **-Q**      Sessiz mod. Ayarlanmazsa, program sıkıştırma yüzdeleri ve miktarı gibi istatistikleri bildirir
              kullanılan kullanılabilir depolama alanının miktarı.
       **-S**      Metin dosyasında gizli mesaj için kullanılabilir yaklaşık alan miktarını bildirir. Satır
              uzunluk dikkate alınır, ancak diğer seçenekler göz ardı edilir.
       **-V, ** **--sürüm**
              Kullanım bilgilerini görüntüle ve çık.
       **-h, ** **--yardım**
              Kullanım bilgilerini görüntüle ve çık.

## Stegsnow için olanların hepsi GİFSHUFFLE için de geçerlidir.

---
# HACKVİSER ÇÖZÜMLERİ
### 1- Meta Data
exiftool ile dosya bilgilerini görüntülüyoruz:
![[Pasted image 20250406001233.png]]

Burada cevap bulduk.


### 2- Audio Spectrum
![[Pasted image 20250406002623.png]]

dosyayı açıyoruz.
![[Pasted image 20250406002723.png]]

diyerek sesi büyültüyoruz. Daha sonraaaaaa;
![[Pasted image 20250406002817.png]]

Burada 3 noktaya basıp Waveform kısmını >> **Spectogram** yapıyoruz.
![[Pasted image 20250406002857.png]]

Ve flag burada

### 3- Color Conversion
`https://georgeom.net/StegOnline/upload`
Sitesine gidiyoruz. Dosyayı yüklüyoruz.
![[Pasted image 20250406023044.png]]

LSB Half a tıklıyoruz.
![[Pasted image 20250406023104.png]]

şeklinde foto sol alt yakınlaştıralım.
![[Pasted image 20250406023130.png]]

cevap çıkıyor.

### 4- Embedded Text
Dosyamızı indiriyoruz:
![[Pasted image 20250406014516.png]]

`steghide extract -sf image.jpg -p ""`
şeklinde parola olmadan dosyayı yolluyoruz. txt dosyasına kayedediyor.
![[Pasted image 20250406014550.png]]

Ve çözüldü 👌

>[!FAQ] UYARI
>Burada önemli noktalardan birisi uzantıdır.
>jpg dosya uzantısı için bu geçerlidir.

### 5- Whitespace

Bu dosyamızı `https://www.dcode.fr/whitespace-language` linkine giderek yüklüyoruz.
Sonra da decrpyt tuşuna basıyoruz.
![[Pasted image 20250406015435.png]]

Cevap **Hercules**
Bu kadardı...

---

# BİR YARIŞMADAKİ STEGO ÇÖZÜMÜ:

Elimizde bozuk bir png dosyası vardı.
![[Pasted image 20250406230742.png]]

şeklinde sonuç alıyorduk. Bunu steghide, stegcracker, zsteg gibi araçlara attığımda PNG veya İmage dosyası olmadığı için sürekli olarak hatalar alıyordum. Daha sonra:
![[Pasted image 20250406230846.png]]

![[Pasted image 20250406230858.png]]

`That was clever, but not enough :) Just try to make some visual changes`
şeklinde bir mesaj aldım. Bunun da üstüne gidip araştırma yaptım.
![[Pasted image 20250406231007.png]]

Şeklinde ilerledim.
Bu sonuç dosyayı tanıyamadığı yani bozuk veya eksik olduğu anlamına geliyor.
![[Pasted image 20250406231050.png]]

Yazınca da 
![[Pasted image 20250406231113.png]]

Şeklinde bilgiye ulaştım. 

```css
(echo -ne '\x89\x50\x4E\x47\x0D\x0A\x1A\x0A'; tail -c +9 magician.png) > fixed.png

```
şeklinde kodu girerek dosya içerisine başına PNG'ye ait değeri girip bunu da fixed.png şeklinde adlandırma yaptım. Şimdi elimde yeni bir dosya var. Fixed.png
Bu dosyayı açınca:
![[Pasted image 20250406231238.png]]

şeklinde ve `file fixed.png` yazınca da PNG dosyası olduğunu gördüm. Şimdi aperisolve veya stegonline sitesine gidip dosyayı atıyorum.
![[Pasted image 20250406231358.png]]

VE CEVAP 👌👌👌👌

---
>[!ERROR] NOTE
>stegosolve aracı çalıştırma:
>öncelikle `cd opt` 
>daha sonra `java -jar Stegsolve.jar ` şeklinde çalışır.


>[!FAQ] NOT2
>gif dosyasının her bir adımını fotoğrafa dökme
>`convert copadam.gif frame%d.png` komutu ile yapıyorsun.
>Adimlar foto olarak geliyor.



---
audacity alternatif
## SONİC VİSUALİSER
![[Pasted image 20250407010857.png]]

komutu ile çalıştır.
Daha sonra:
![[Pasted image 20250407010951.png]]

şeklinde görseli meydana çıkar. 👌👌👌👌

---
>[!warning] Not
>jpg dosyalarını outguess aracı ile inceleme yapabiliriz:
>`outguess -r 1.jpeg dosya.txt  ` komutu yeterlidir.




