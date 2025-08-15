Süper! Hiç durmadan 29 günün tamamını detaylı şekilde, her gün ne yapacağını, kaynaklarını ve örneklerini vereceğim.  
Bu, **Amazon Scraper Sistemi** için eksiksiz bir yolculuk olacak. En sonda “BİTTİ” diyeceğim.  
Hazırsan, başlıyoruz! 👇

---

# ✅ 1. HAFTA: Python Temelleri + Projeye Hazırlık

---

## 🗓️ GÜN 1: Python’a Giriş

- Python kurulumu
    
- print(), input(), değişkenler
    
- int, float, str, bool
    
- Veri tipi dönüşümü
    
- Mini proje: Kar hesaplayıcı  
    📘 W3Schools Python Basics
    

---

## 🗓️ GÜN 2: Koşullar + Döngüler

- if, elif, else yapıları
    
- Karşılaştırma operatörleri
    
- for, while döngüleri
    
- break, continue
    
- Mini proje: Fiyat etiketleyici  
    📘 W3Schools Conditions
    

---

## 🗓️ GÜN 3: Veri Yapıları

- list, tuple, set, dict
    
- list içinde dict kullanımı
    
- JSON veri yapısı
    
- Mini proje: Ürün listesinden filtreleme  
    📘 W3Schools Data Structures
    

---

## 🗓️ GÜN 4: Dosya İşlemleri

- `open()`, `read()`, `write()`
    
- JSON dosyasına yazma/okuma
    
- CSV yazma
    
- Mini proje: ASIN listesi JSON/CSV olarak saklama  
    📘 Python File Handling
    

---

## 🗓️ GÜN 5: Proje Tanımı ve Amazon Yapısı

- Amazon'da ürün sayfaları nasıl yapılıyor?
    
- ASIN nedir, nasıl alınır?
    
- URL yapıları, parametreleri
    
- Proje klasör yapısı planlama
    

---

## 🗓️ GÜN 6: HTML ve DOM Yapısı

- `<div>`, `<span>`, `<a>`, `<ul>`, `<li>` gibi tag'ler
    
- class ve id ile öğe seçimi
    
- Devtools (Chrome) ile HTML yapıyı analiz etme  
    📘 HTML DOM Tutorial
    

---

## 🗓️ GÜN 7: Mini Python Projesi

- Sahte ASIN listesiyle veri işleme
    
- list/dict/JSON birleştirme
    
- Fiyatlara göre filtreleme
    
- Kod düzenleme, modüler yapıya geçiş
    

---

# ✅ 2. HAFTA: Web Scraping + ASIN Tarama

---

## 🗓️ GÜN 8: Playwright Kurulumu + Temel Kullanım

- Python için Playwright kurulumu
    
- Sayfa açma, bekleme, URL gezme
    
- Basit bir sayfa başlığı çekme örneği  
    📘 Playwright Python Docs
    

---

## 🗓️ GÜN 9: Amazon Sayfalarından ASIN Çekme

- `.product` elementlerini bulma
    
- `data-asin` değerini çekme
    
- 1 sayfadan tüm ASIN'leri alma  
    📘 [Amazon ürün sayfa DOM yapısı örnekle inceleme](https://www.amazon.com/s?k=product)
    

---

## 🗓️ GÜN 10: Kategori Sayfalarında Sayfa Sayfa Gezinme

- URL üzerinden sayfa parametresi değiştirme
    
- for döngüsü ile 400 sayfa tarama
    
- Her sayfadaki ASIN'leri birleştirme
    

---

## 🗓️ GÜN 11: ASIN Kaydetme

- Liste halinde toplanan ASIN’leri `.json` ve `.csv` dosyalarına yazma
    
- Tekrar edenleri temizleme (`set`)
    
- Günlük klasörleme sistemi
    

---

## 🗓️ GÜN 12: Temizleme ve Kontrol

- ASIN’lerin boş olup olmadığını kontrol et
    
- regex ile geçerli ASIN formatı kontrolü (10 haneli alfanumerik)
    
- `asin_cleaner.py` modülü yaz
    

---

## 🗓️ GÜN 13: Proxy Kullanımı

- Proxy nedir, neden gerekir?
    
- Ücretsiz ve ücretli proxy kaynakları
    
- Playwright ile proxy kullanımı  
    📘 [ScraperAPI veya BrightData gibi servisler araştır](https://www.scraperapi.com/)
    

---

## 🗓️ GÜN 14: Proxy Rotasyonu

- Proxy listesinden rastgele seçim
    
- User-Agent değiştirme
    
- IP bloklanmasına karşı botu sağlamlaştırma
    

---

# ✅ 3. HAFTA: Ürün Detayı + Veritabanı + Kâr Hesaplama

---

## 🗓️ GÜN 15: Ürün Sayfası İncelemesi

- Ürün detaylarının bulunduğu HTML alanlar
    
    - Satıcı sayısı
        
    - Fiyat
        
    - Stok bilgisi
        
- Playwright ile tek ürün sayfası test
    

---

## 🗓️ GÜN 16: Ürün Bilgisi Çekme (Scraper)

- Her ASIN için URL oluştur
    
- Gerekli alanları DOM’dan çek
    
- Boş alanları kontrol et
    

---

## 🗓️ GÜN 17: MongoDB Giriş

- MongoDB Atlas hesabı oluştur
    
- Python’dan bağlanma (pymongo)
    
- Veri yazma/okuma  
    📘 [MongoDB for Beginners](https://www.mongodb.com/basics)
    

---

## 🗓️ GÜN 18: ASIN Bilgilerini MongoDB’ye Yazma

- Her ürün için dict yapısı
    
- insert_one, insert_many kullanımı
    
- Koleksiyon yapısı: `products`
    

---

## 🗓️ GÜN 19: Upsert Kullanımı

- Aynı ASIN varsa güncelle, yoksa ekle
    
- `update_one(filter, { $set: ... }, upsert=True)`
    

---

## 🗓️ GÜN 20: Gümrük ve Kâr Hesaplama Mantığı

- Ürün fiyatı + tahmini kargo + % vergi
    
- Kâr = Satış fiyatı - Toplam maliyet
    
- Fonksiyonlaştırma
    

---

## 🗓️ GÜN 21: Scraper ile Entegre Kâr Hesabı

- Her ürün için `profit` değeri ekle
    
- Sıfır kâr olan ürünleri ayrı listele
    
- MongoDB’ye `profit` alanı ekle
    

---

# ✅ 4. HAFTA: API + Dashboard + Otomasyon

---

## 🗓️ GÜN 22: FastAPI Tanıtım

- Kurulum
    
- Endpoint yapısı
    
- İlk örnek: “Merhaba dünya!”  
    📘 FastAPI Docs
    

---

## 🗓️ GÜN 23: Ürün Listeleme API’si

- `/products` endpoint’i
    
- MongoDB'den tüm veriyi çek
    
- JSON olarak döndür
    

---

## 🗓️ GÜN 24: Filtreleme Endpoint'leri

- `/products?min_profit=10`
    
- `/products?in_stock=true`
    
- Query parametre ile dinamik filtreleme
    

---

## 🗓️ GÜN 25: Dashboard Planı

- Hangi alanlar gösterilecek?
    
- Fiyat grafiği, stok durumu
    
- Hangi framework kullanılacak?
    

---

## 🗓️ GÜN 26: React veya Basit HTML Arayüz

- HTML ile veri çekme (fetch API)
    
- Tablo şeklinde listeleme
    
- “Filtrele” butonları
    

---

## 🗓️ GÜN 27: Otomatik Veri Güncelleme

- Günlük cronjob sistemi
    
- ASIN taraması + detay güncellemesi
    
- Sunucu saatine göre çalışma
    

---

## 🗓️ GÜN 28: Deploy Etme

- API + veritabanı sunucuya kurulum
    
- Uptime robot ile kontrol
    
- .env ile gizli bilgiler
    

---

## 🗓️ GÜN 29: Test ve Demo Hazırlığı

- Sistemin son kontrolü
    
- Log dosyaları
    
- Demo videosu / sunum sayfası
    

---

# 🎉 BİTTİ!

Tebrikler! Bu 29 günlük yolculuğun sonunda:

- Python öğrendin,
    
- Web scraper yazdın,
    
- Amazon’dan binlerce ürün taradın,
    
- MongoDB ile veri sakladın,
    
- API geliştirdin,
    
- Web arayüzü ve otomasyon yaptın.
    

İstersen şimdi her günü uygulamaya başlayabilirsin. Yardımcı olmamı istediğin herhangi bir gün olursa hemen o güne özel destek verebilirim 💪

Hazırsan, şimdi sıradaki günü çalışmaya başlayalım!