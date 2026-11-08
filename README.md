# İngilizce Kartlar

Speakout Pre-intermediate (2nd edition) ünite sırasına göre hazırlanmış, telefonda uygulama gibi çalışan bir İngilizce çalışma uygulaması.

## Özellikler

- Günlük kartlar ve aralıklı tekrar (1, 3, 7, 14, 30, 60 gün)
- 12 ünite: kelimeler, ek örnek cümleler, dilbilgisi, alıştırmalar, diyaloglar, konuşma ve yazma görevleri
- 7 pratik modu: anlamını seç, İngilizcesini seç, yazarak cevap, dinle ve yaz, cümlede boşluk, cümle kur, eşleştir
- Ara sınav (Unit 1–6) ve final sınavı (Unit 1–12)
- Profil: kullanıcı adı, avatar, seviye, seri, haftalık grafik, ünite ilerlemesi ve rozetler
- Sesli okuma (tarayıcının metin okuma özelliği ile)
- İnternetsiz çalışma (service worker) ve ana ekrana eklenebilme (PWA)
- Yedek kodu ile ilerlemeyi başka cihaza taşıma

Ünite sırası ve konular kitapla uyumludur; örnekler, alıştırmalar, diyaloglar ve sınav soruları bu uygulama için yazılmış özgün içeriklerdir.

## Dosyalar

| Dosya | Açıklama |
| --- | --- |
| `index.html` | Uygulamanın tamamı (HTML, CSS ve JavaScript tek dosyada) |
| `manifest.json` | Ana ekrana ekleme bilgileri (ad, simge, renkler) |
| `sw.js` | İnternetsiz çalışma için service worker |
| `icon-180.png`, `icon-192.png`, `icon-512.png` | Uygulama simgeleri |
| `netlify.toml` | Netlify ayarları (service worker'ın güncel kalması için) |

## Veriler nerede saklanır?

Tüm ilerleme ve profil bilgisi sadece kullanıcının cihazında, tarayıcının yerel deposunda (localStorage) saklanır. Hiçbir sunucuya gönderilmez.

## Yayınlama

**Netlify:** Bu depoyu Netlify'a bağla (Add new site → Import an existing project → GitHub). Build komutu boş, yayın klasörü `/` olarak kalsın. Her `git push` sonrası site kendiliğinden güncellenir.

**GitHub Pages:** Depo ayarlarında Settings → Pages → Branch: `main`, klasör: `/ (root)` seç. Site birkaç dakika içinde `https://KULLANICI-ADI.github.io/DEPO-ADI/` adresinde yayına girer.

## Güncelleme yaparken

`index.html` değiştiğinde `sw.js` içindeki `CACHE` adını bir artır (ör. `ingilizce-v3` → `ingilizce-v4`). Böylece telefonlardaki eski kopya temizlenir ve yeni sürüm yüklenir.

## Yerelde çalıştırma

```bash
python3 -m http.server 8000
```

Sonra tarayıcıda `http://localhost:8000` adresini aç.
