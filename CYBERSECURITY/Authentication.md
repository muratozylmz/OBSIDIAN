
# 3 TÜRDE BULUNUR:
### 1. Sadece kullanıcı adı hatası varsa (ilk başta yalnızca username kontrol ediyolarsa, password'u umursamıyorsa)
### 2. 2FA doğrulama varsa 
### 3. 2FA link olarak maile gönderiliyorsa



>[!FAQ] GENEL
>Bize bu açık için gerekli olan şey gideceğimiz URL dizinini bizim belirleyebilmemiz



==İLK LABIMIZ İLE GİRİŞ YAPALIM!

## 1. 
### Bu tip açıklar Brute Force yapabildiğimiz login sayfalarında aranır.
Bu durumlarda herhangi bir engelleyici rate limiting tarzı durumlar olmadığı için wordlist üzerinden brute force attacklar yapılır.
Lakin hem username hem de password'e saldırı yapmak biraz yorucu olabilir ve çok da işe yaramayabilir.

![[Pasted image 20250313133926.png]]

#### Bunun gibi yanlış kullanıcı adı dediği durumlarda kullanırız.
Daha sonra sadece username kısmına brute force yaparız.
Kullanıcı adını bulduktan sonra da password'e saldırı yaparız ve sonucu buluruz.
![[Pasted image 20250313134039.png]]

---
# PEKİ 2FA VAR İSE?

Bize ilk başta bir bilgi veriliyor. Biz de kendimize gelen kodu girip giriş yapıyoruz. 

>[!warning] UYARI
>Bu noktada önemli olan şey giriş yaparken gideceğimiz URL'i değiştiriyor olabilmemiz 

![[Pasted image 20250313140902.png]]
Burada login yerine my-account'e gidiyoruz.


==Login den sonra Burp içerisinde gideceğimiz URL'i değiştirebiliyoruz.

---

# PEKİ LİNK GÖNDERİYORSA MAİL'E?

### Bu durumda linkin bizi yönlendirdiği noktada yine gideceğimiz URL dizinini bypass etmiş oluyoruz.

![[Pasted image 20250313140425.png]]
Wiener'i Carlos yaptık labı çözdük.


