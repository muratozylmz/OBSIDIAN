Çok ilginç bir not ile karşı karşıya kaldım.
#### SQL var mı yok mu test etmek için mesela id=1 olsun. Sen burada id=2-1 yazdığında sonuç yine id=1 şeklinde dönüyorsa burada SQL Injection vardır deriz. 👌 AMA BU YÖNTEM AŞIRI AŞIRI BASİC 😁 

>[!NOTE] Not
>Burada SQL açığı bulduktan sonra gerisini aslında sqlmap gibi araçlara göndermemiz gerekiyor. Amele gibi uğraşmak yerine 
>ASIL AMAÇ SQL'İN VAR OLDUĞUNU BULMAKI!!!
#sql #cybersecurity 
##### LAKİN LAB ÇÖZÜMÜ İÇİN :
Burada SQL bulduktan sonra sol tarafta dönen kategori yani tablo sayısını bulmak için `UNION SELECT` komutunu kullanırız. 
Burada örneğin;
- '==UNION SELECT== NULL,NULL-- komu 200 döndürürse biliriz ki 2 tane sütun var.

>[!FAQ] Uyarı
>Burada UNION SELECT 1,2# komutundan sonra eğer sitemizde değer dönerse, Mesela diyelim ki bir tablo var 5 sütundan oluşuyor. Burada ilk satırda 1 yazarsa:
>Komutu şu şekilde değiştiririz: UNION SELECT version(),2# Bu kodun çıktısı olarak da 1 yazan yerde versionu görmüş oluruz.

BURADA MDISEC'in database ismi öğrenmek için kullandığı bir fonksiyon not etcem: 
>[!tip] KOD
>extractvalue(rand(), concat(1,(SELECT database())));

>[!NOTE] SUBSTRING
>Bu komut 3 tane parametre alır: 
>1- 'STRING DEGER'
>2- Hangi karakterden
>3- Hangi karaktere kadar keseceği

### SQL INJECTION 
### TIME BASED PAYLOADLAR İLE TESPİT EDİLİR!!!!!!

Mehmet Dursun Ince demiş :)

Sebebi de SQL tipi ne olursa olsun time based tüm databaselerde ortak bir şekilde çalışır.

>[!NOTE] UNUTMA
>Eğer ORACLE database deniliyorsa `FROM dual` kullanılır.



