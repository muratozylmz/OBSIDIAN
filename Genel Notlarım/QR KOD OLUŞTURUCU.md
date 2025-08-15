```cs
import qrcode

import uuid

  

# Benzersiz ID oluştur

unique_id = str(uuid.uuid4())

# Bu ID'yi bağlantıya ekle

url = f"https://www.instagram.com/alperatbiniciii13/"

  

# QR kod oluştur

qr = qrcode.make(url)

  

# QR kodu kaydet

qr.save(f"qrcode_{unique_id}.png")

  

print(f"QR kod oluşturuldu: {url}")
```

Daha sonra klasöre QR Kod oluşturuluyor.

### PDF DOSYASI
Pdf dosyası için yöntemlerden birisi `Google Drive` içerisine yükleyip direkt olarak indirme bağlantısını ekleme.


#### RENDER
Bu site ile birlikte ücretsiz hosting alarak qr oluşturucuyu bir sayfaya çevirdim.
[QR OLUŞTURMA SİTESİ](https://qr-site-ytgg.onrender.com)

Burada github'dan proje çekildi.
![[Pasted image 20250526133605.png]]

![[Pasted image 20250526133612.png]]

![[Pasted image 20250526133619.png]]

![[Pasted image 20250526133636.png]]

Bu kodlar ile birlikte siteyi ayağa kaldırdık.


