Github'a dosya veya klasör eklemek istediğimizde:
- Öncelikle `git init` komutu giriyoruz. Bu komut ile bilgisayarımızda repo oluşturma işlemini yapıyoruz.
- İstediğimiz dosya için `git add </dosya>` komutu giriyoruz.
- `git remote add origin (Buraya .git adlı URL'i girerek yüklemek istediğimiz repo ile bağlantı kuruyoruz. )` 
- `git commit -m "Yorumu giriyoruz."`
- "git push origin main" komutu ile yükleme işlemini yapıyoruz.


## Diğer bir yol ise:

- İlk başta `git clone <buraya_klasör_kodunu_yapıştırıyoruz>.` Bu komut ile dosyayı pc'ye indiriyoruz.
- Daha sonra `cd` komutu dahilinde klasör içerisine giriyoruz. !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
- Şimdi istersek bireysel olarak düzenliyoruz veya `cp` komutu ile klasöre atmak istediğimiz dosyayı kopyalıyoruz.
- `git add .` ile tüm dosyaları tekrar yüklemek için seçiyoruz. (bireysel olarak dosyayı da çekebiliriz tamamını çekmek zorunda değiliz.)
- `git commit -m "Yorumu yazıyoruz."`
- `git push origin main` komutu ile de bitirmiş oluyoruz.