# RadeGram — Render ücretsiz test kurulumu

Bu paket, RadeGram'ı Render üzerinde hızlıca test etmek için hazırlanmıştır.

## Render'a yükleme

1. ZIP'i bilgisayarına indirip ayrı bir klasöre çıkar.
2. GitHub'da yeni bir repository oluştur. `app.py`, `index.html`, `render.yaml`, `.gitignore` ve bu README dosyasını repo köküne yükle. Veritabanı veya `uploads` klasörü ekleme.
3. https://dashboard.render.com/ adresini aç ve GitHub hesabını bağla.
4. Render Dashboard → **New +** → **Blueprint** seçeneğine tıkla.
5. RadeGram repository'sini seçip `render.yaml` dosyasını tanıt. Ücretsiz planı seçerek oluştur.
6. Deploy tamamlanınca Render'ın verdiği `https://radegram-....onrender.com` adresini aç.
7. `https://SENIN-ADRESIN.onrender.com/api/health` adresi `{"ok": true, ...}` döndürmeli.

## Çok önemli sınırlamalar

- Ücretsiz web hizmetleri 15 dakika gelen trafik olmazsa uyur; ilk istekten sonra uyanması yaklaşık bir dakika sürebilir.
- Ücretsiz hizmetin dosya sistemi geçicidir. Bu test ayarında kullanıcı hesapları, SQLite veritabanı, yüklenen görseller ve videolar yeniden başlatma, uyku veya yeniden dağıtım sırasında kaybolabilir. Gerçek kullanıcı verilerini burada tutma.
- Render'ın ücretsiz PostgreSQL veritabanı 30 gün sonra sona erdiğinden tek başına kalıcı ve ücretsiz çözüm değildir. RadeGram'ın herkese açık gerçek kullanımına geçmeden önce kalıcı veritabanı ve dosya depolaması tasarlanmalıdır.
- Bu paket sadece backend ve arayüz testidir; Windows `.exe` derlemesi değildir.
- GitHub'a kişisel `vyro.sqlite3`, `-wal`, `-shm`, `.env` veya `uploads/` dosyalarını asla yükleme.

## Güvenlik

RadeGram şu anda bir prototiptir. Geniş kitlelere açmadan önce oran sınırlama, kötüye kullanım bildirimi/moderasyon, yedekleme, dosya türü/ boyutu kontrolleri ve güvenlik testi gerekir.
