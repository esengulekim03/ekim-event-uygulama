# Ekim Event Etkinlik Yönetim Sistemi

Ekim Event için Türkçe, mobil/tablet/masaüstü uyumlu, Appwrite Cloud tabanlı yönetim uygulaması.

## İçerik
- Dashboard
- Etkinlikler + renkli aylık takvim + detay ekranı
- Okullar + okul detayları + görüşme geçmişi
- Stok + giriş/çıkış + hareket geçmişi + kritik stok
- Ekipmanlar
- Personeller
- Finans: gelir/gider
- Hatırlatmalar
- Raporlar
- Arama
- Çöp kutusu, geri alma ve kalıcı silme
- Appwrite Realtime ile değişiklikleri cihazlar arasında yenileme

## Appwrite kurulumu
Bu uygulama tek `records` koleksiyonu kullanır. Böylece her modül için onlarca ayrı koleksiyon oluşturmak gerekmez.

Appwrite > Databases > Ekim Event veritabanı > Create collection:
- Collection ID: `records`
- İsim: `Kayıtlar`

Attributes:
- `type` → String → 50
- `data` → String → 60000
- `deleted` → Boolean
- `updatedAt` → String → 40

İzinler (giriş sistemi olmadığı için):
- Read: Any
- Create: Any
- Update: Any
- Delete: Any

UYARI: Bu kurallar internetteki herkesin veritabanına yazabilmesi anlamına gelir. Uygulama gerçek kullanımda güvenli hale getirilirken Appwrite Functions/korumalı API veya Appwrite Auth tabanlı bir erişim katmanı eklenmelidir. API/Secret key'i frontend'e koymayın.

## Çalıştırma
```bash
npm install
npm run dev
```

## Bağlantı
`src/main.jsx` içindeki CONFIG, kullanıcının verdiği Appwrite bilgileriyle hazırdır:
- Endpoint: https://fra.cloud.appwrite.io/v1
- Project ID: 6ac57b3f00273bc7e031
- Database ID: 6ac57bf7000d6193bbb9
- Collection ID: records
