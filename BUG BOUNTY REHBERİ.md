## **1. Keşif (Reconnaissance) Araçları**

Bu aşama, hedef sistem hakkında bilgi toplamak için kullanılır.

### **1.1 Alan Adı ve Alt Alan Adı Keşfi**

- **Amass** → Pasif ve aktif bilgi toplamak için kullanılır.
    
- **Subfinder** → Hızlı alt alan adı keşfi için idealdir.
    
- **Assetfinder** → Alt alan adlarını bulmak için basit bir araçtır.
    
- **Findomain** → Alt alan adı keşfi ve IP eşleşmesi yapar.
    
- **crt.sh** → Sertifikalardan alt alan adı bilgisi çeker.
    
- **Knockpy** → Python tabanlı alt alan tarama aracıdır.
    
- **Sudomy** → Subdomain keşfi için toplu çalışan bir araçtır.
    
- **Chaos** → ProjectDiscovery tarafından sağlanan geniş bir alt alan adı veritabanına erişim sağlar.
    

### **1.2 IP ve DNS Keşfi**

- **Masscan** → Çok hızlı port taraması yapabilir.
    
- **Nmap** → Ağ keşfi ve güvenlik taraması için en popüler araçlardan biridir.
    
- **Dnsx** → DNS çözümleme için kullanılır.
    
- **Golang DNS Resolver** → DNS kayıtlarını almak için optimize edilmiştir.
    
- **Reverse IP Lookup** → Bir IP adresine bağlı tüm alan adlarını görmek için kullanılır.
    

### **1.3 WHOIS ve Pasif Bilgi Toplama**

- **whois** → Alan adı kayıt bilgilerini getirir.
    
- **theHarvester** → E-posta, alt alan adları, şirket bilgileri toplar.
    
- **Recon-ng** → Modüler bilgi toplama aracıdır.
    
- **Shodan** → İnternete bağlı cihazları aramak için kullanılır.
    
- **Censys** → SSL, IPv4 ve alan adı taraması yapar.
    
- **FOFA.so** → Çin merkezli büyük bir bilgi toplama platformudur.
    
- **Hunter.io** → Şirketlerin e-posta adreslerini bulmak için kullanılır.
    

---

## **2. Tarama (Scanning) ve Açık Port Analizi**

Bu aşamada, hedef sistemdeki açık portlar ve servisler tespit edilir.

### **2.1 Web Uygulama Tarama Araçları**

- **Burp Suite** → Web uygulamaları test etmek için en iyi araçlardan biridir.
    
- **OWASP ZAP** → Açık kaynaklı bir güvenlik tarayıcısıdır.
    
- **Nikto** → Web sunucularındaki güvenlik açıklarını tespit eder.
    
- **Arachni** → Otomatik güvenlik taraması yapabilir.
    

### **2.2 Port ve Servis Tarayıcıları**

- **Nmap** → Ağ keşfi ve güvenlik taraması yapar.
    
- **Masscan** → Büyük ölçekli ağ taramaları için en hızlı araçlardan biridir.
    
- **RustScan** → Çok hızlı port taraması yapar.
    
- **Naabu** → Hızlı TCP port tarayıcısıdır.
    

---

## **3. Açık ve Güvenlik Zafiyeti Tespiti**

### **3.1 Web Güvenlik Açıkları İçin**

- **Nuclei** → Web uygulamalarını güvenlik açıklarına karşı tarar.
    
- **XSStrike** → XSS açıklarını otomatik tespit eder.
    
- **SQLmap** → SQL Injection testleri için kullanılır.
    
- **Dirsearch** → Web sunucularında dizin keşfi yapar.
    
- **Gobuster** → Dizini brute-force yaparak tarar.
    
- **FFUF** → Hızlı fuzzing aracı.
    

### **3.2 Exploit ve Sömürü Araçları**

- **Metasploit Framework** → Exploit geliştirme ve saldırılar için kullanılır.
    
- **ExploitDB** → Güvenlik açıklarına dair exploit kodları içerir.
    
- **SearchSploit** → ExploitDB’deki exploitleri kolayca bulmak için kullanılır.
    
- **Commix** → OS Command Injection açıklarını test eder.
    
- **XAttacker** → Otomatik exploit aracı.
    

---

## **4. OSINT (Açık Kaynak İstihbarat) Araçları**

- **SpiderFoot** → Pasif ve aktif bilgi toplama için kullanılır.
    
- **Maltego** → OSINT analizi için en güçlü araçlardan biridir.
    
- **Sherlock** → Kullanıcı adlarını farklı platformlarda arar.
    
- **GHunt** → Google hesapları hakkında bilgi toplar.
    
- **Recon-ng** → Modüler OSINT aracıdır.
    

---

## **5. Mobil Güvenlik Araçları**

- **MobSF** → Mobil uygulama güvenlik testleri için en iyilerden biridir.
    
- **Frida** → Android ve iOS tersine mühendislik için kullanılır.
    
- **Objection** → Root olmadan Android ve iOS testleri yapmak için kullanılır.
    
- **APKTool** → Android APK dosyalarını decompile etmek için kullanılır.
    
- **JD-GUI** → Java kodlarını analiz etmek için kullanılır.
    
- **AndroBugs** → Android güvenlik açıklarını tespit eder.
    

---

## **6. WiFi ve Ağ Güvenlik Araçları**

- **Aircrack-ng** → Kablosuz ağ güvenliği testleri için kullanılır.
    
- **Wireshark** → Ağ trafiğini analiz etmek için kullanılır.
    
- **Bettercap** → MITM saldırıları ve ağ izleme için kullanılır.
    
- **Responder** → SMB, NetBIOS gibi protokolleri kullanarak kimlik bilgilerini yakalar.
    
- **Evil Twin Attack Tools** → Sahte WiFi ağları oluşturmak için kullanılır.
    

---

## **7. Raporlama ve Otomasyon Araçları**

- **Bugcrowd Template** → Rapor yazımı için kullanılır.
    
- **HackerOne Markdown** → Raporlar için Markdown formatı sağlar.
    
- **Dradis** → Güvenlik test raporları oluşturmak için kullanılır.
    
- **Pentest Report Generator** → Otomatik raporlar oluşturur.
    
- **JIRA** → Güvenlik hatalarını takip etmek için kullanılır.