# Ekim Event – Appwrite kurulumu

## 1. Appwrite
1. Appwrite projesini aç.
2. **Databases → Ekim Event** veritabanına gir.
3. **Create collection** seç.
4. Collection ID: `records`
5. Koleksiyon adı: `Kayıtlar`

## 2. Attributes
Sadece 4 alan gerekiyor:

- `type` → String → 50
- `data` → String → 60000
- `deleted` → Boolean
- `updatedAt` → String → 40

Uygulamadaki okul, etkinlik, stok, ekipman, personel vb. bütün ayrıntılar `data` alanındaki JSON içinde tutulur. Böylece her alanı tek tek Appwrite'ta açmak gerekmez.

## 3. Permissions
Uygulamada giriş olmadığı için istemci doğrudan Appwrite'a bağlanıyor. Çalışması için koleksiyon izinleri:

- Read: Any
- Create: Any
- Update: Any
- Delete: Any

**Güvenlik notu:** Bu ayarlar veritabanını internete açık yazılabilir hale getirir. Gerçek işletme kullanımından önce korumalı bir backend/Appwrite Function veya Auth tabanlı erişim katmanı eklenmesi gerekir. API/Secret key frontend'e kesinlikle konulmamalıdır.

## 4. Proje bağlantısı
`src/main.jsx` içindeki CONFIG zaten kullanıcının Appwrite bilgileriyle ayarlı:

- Endpoint: `https://fra.cloud.appwrite.io/v1`
- Project ID: `6ac57b3f00273bc7e031`
- Database ID: `6ac57bf7000d6193bbb9`
- Collection ID: `records`

## 5. Bilgisayarda çalıştırma
Node.js kurulu terminalde:

```bash
npm install
npm run dev
```

Tarayıcıda Vite'ın verdiği yerel adresi aç.

## 6. Uygulama özellikleri
- Ana sayfa ve özet kartları
- Etkinlik ekleme/düzenleme/silme
- Renkli aylık takvim
- Etkinlik detay sayfası
- Ücretsiz/Ücretli/Biletli etkinlik türleri
- Ücret, kapora, kalan ödeme, bilet ve fatura alanları
- Okul kartları ve okul detay sayfası
- Okul görüşme geçmişi
- Stok miktarı, minimum stok, giriş/çıkış ve hareket geçmişi
- Ekipman ekleme ve etkinliklere ekipman atama
- Personel ekleme ve etkinliklere personel atama
- Gelir/gider
- Hatırlatmalar
- Raporlar
- Global arama
- Çöp kutusu, geri alma ve kalıcı silme
- Appwrite Realtime değişiklik bildirimi
- Mobil/tablet/masaüstü responsive arayüz
