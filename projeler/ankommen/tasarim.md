# Ankommen – Tasarım Dokümanı

Sürüm: prototip 3 · 12 Kasım 2026

## 1. Ürün

**Ne:** Türkiye’den Almanya’ya öğrenim ya da iş için taşınan kişilere, yapmaları gereken resmî işleri kendi durumlarına ve tarihlerine göre sıralayan bir rehber ve takip aracı.

**Kim için:** Dil okulu, lisans, yüksek lisans ya da çalışma amacıyla ulusal vizeye başvuracak kişiler. Çoğu süreci ilk kez yaşıyor, Almancası sınırlı ve sayfayı telefondan açıyor.

**Temel iş:** “Şimdi ne yapmalıyım ve bunun için neye ihtiyacım var?” sorusuna tek ekranda cevap vermek.

**Ne değil:** Hukuki danışmanlık, resmî başvuru sistemi ya da kabul garantisi veren bir araç değil.

## 2. Tasarım ilkeleri

1. **Sıra bilgidir.** Adımlar gerçek bir sıra izlediği için dikey bir tren hattı ve duraklar olarak çizilir. Hat süs değil; neyin neden önce geldiğini gösterir.
2. **Önce sıradaki adım.** Sarı pano her zaman yapılabilir en yakın işi gösterir. Kullanıcı listeyi taramak zorunda kalmaz.
3. **Tarih girmeden de çalışır.** Tarih yoksa adımlar “varıştan 14 gün sonra” gibi göreli gösterilir.
4. **Tek cesur öğe.** Sinyal sarısı yalnızca dikkat gereken yerde kullanılır: sıradaki adım, yaklaşan tarih, odak çerçevesi.
5. **Resmî ama soğuk değil.** Alman tabela dilinden esinlenen dar başlıklar, sade ve açık Türkçe metin.
6. **Uydurma yok.** Kesin tutar bilinmiyorsa “kasaya göre” ya da “üniversiteye göre” yazılır; rakam tahmin edilmez.

## 3. Renkler

Renkler `:root` üzerinde değişken olarak tanımlıdır ve koyu tema için yeniden atanır.

| Değişken | Açık tema | Koyu tema | Kullanım |
|---|---|---|---|
| `--paper` | `#EDF1F4` | `#0E1C28` | Sayfa zemini, giriş alanları |
| `--surface` | `#FFFFFF` | `#16293A` | Kartlar, listeler |
| `--ink` | `#12324A` | `#E6EEF4` | Metin, seçili düğme zemini |
| `--muted` | `#56697A` | `#9DB0C0` | İkincil metin |
| `--line` | `#12324A` | `#7FA3BF` | Hat ve durak çerçevesi |
| `--rule` | `#CFD8DF` | `#2A4257` | Giriş alanı ve düğme çerçeveleri |
| `--soft` | `#DFE6EB` | `#1D3447` | İpucu ve Almanca kutuları, nötr rozet |
| `--signal` | `#F2C200` | `#F2C200` | Sıradaki adım panosu, “az kaldı” rozeti, odak |
| `--signal-ink` | `#2B2300` | `#2B2300` | Sarı üstündeki metin |
| `--done` | `#1E7A4E` | `#4CC38A` | Tamamlanan durak |
| `--late` | `#C0352B` | `#FF7A6E` | Geciken adım rozeti |

Kural: sarı zemin üstünde her zaman `--signal-ink` kullanılır. Kırmızı yalnızca tarihi geçmiş adımda görünür.

## 4. Tipografi

| Rol | Yazı tipi | Ağırlık | Boyut |
|---|---|---|---|
| Sayfa başlığı | Barlow Condensed | 700 | 3,25rem (geniş ekranda 4rem) |
| Bölüm başlığı | Barlow Condensed | 700 | 1,5rem |
| Sıradaki adım | Barlow Condensed | 700 | 1,75rem |
| Adım başlığı | Barlow | 600 | 1,0625rem |
| Gövde | Barlow | 400 | 1,0625rem, satır aralığı 1,5 |
| İkincil metin | Barlow | 400–500 | 0,875–0,9375rem |
| Rozet | Barlow | 600 | 0,8125rem |

Yedek aileler: `"Arial Narrow", system-ui, sans-serif`. Tarih ve tutarlarda `font-variant-numeric: tabular-nums`. Tamamı büyük harfli etiket kullanılmaz; başlıklar cümle düzenindedir.

## 5. Yerleşim

- Tek sütun, en fazla 38rem genişlik, ortalanmış. Yan boşluk 1,125rem.
- Önce telefon: bütün dokunma hedefleri en az 2,9rem yüksekliğinde.
- Köşe yarıçapı: büyük yüzeyler 0,75rem, kartlar 0,625rem, giriş alanları 0,5rem, rozet ve sekmeler tam yuvarlak.
- Gölge yok; katmanlar zemin rengi farkıyla ayrılır.
- Sayfa sırası: başlık → durum kartı → sıradaki adım panosu → sekmeler → seçili bölüm → alt bilgi.

## 6. Bileşenler

**Durum kartı.** Dört soru: ne için gidiyorsun (2×2 seçenek), hangi şehre, varış tarihi, vize bitiş tarihi. Her değişiklik anında bütün sayfayı günceller.

**Sıradaki adım panosu.** Sarı zemin. Küçük etiket, adım başlığı, tarih ve kalan gün, ilerleme çubuğu, “4 / 15 adım tamamlandı”. Ön koşulu eksik olmayan en yakın tarihli adımı seçer.

**Sekmeler.** Adımlar · Belge çantası · Bütçe · Mektup yaz. Hap biçiminde düğmeler; seçili olan `--ink` zeminli. “Mektup yaz” yalnızca Claude erişimi varsa görünür.

**Hat ve durak.** Solda 4 piksel kalınlığında dikey çizgi. Her adım, çizginin üstünde 2,125rem çapında yuvarlak bir düğmedir; düğme aynı zamanda “tamamladım” onay kutusudur. Sağında adım kartı durur.

**Adım kartı.** Kapalıyken: başlık, tarih, durum rozeti, varsa “Önce: …” satırı. Açılınca: açıklama, Nerede, Yanında olsun (belge listesi), ipucu kutusu, Almanca kutusu, Takvime ekle ve resmî kaynak linkleri.

**Rozetler.** Nötr (10 günden fazla), sarı (10 gün ve altı, bugün), kırmızı (geçti), yeşil metin (tamamlandı).

**Almanca kutusu.** İki sütunlu terim listesi (Almanca kalın, Türkçe soluk) ve dairede söylenecek tek bir hazır cümle, altında çevirisi.

**Belge çantası.** Seçili yoldaki tüm belgeler tekrarsız, iki grupta: “Türkiye’den hazırla” ve “Almanya’da alacaksın”. Her satır onay kutulu.

**Bütçe listesi.** Solda kalem, sağda tutar, altında tek satır not.

**Mektup formu.** Tür seçimi, beş alan, dil seçimi, “Taslağı yaz”. Çıktı sol kenarı sarı çizgili kutuda akarak yazılır. Altında “Neyi değiştirelim?” alanı ve “Düzelt”.

## 7. Durumlar

| Durum | Görünüm |
|---|---|
| Tamamlandı | Durak yeşil dolu ve onay işaretli, başlık üstü çizili ve soluk |
| Ön koşul eksik | Durak çerçevesi kesikli, kart altında “Önce: …” satırı. İşaretlemek yine de mümkün |
| Yaklaşıyor | Sarı rozet |
| Gecikti | Kırmızı rozet |
| Tarih yok | Rozet yok, göreli tarih metni |
| Hepsi bitti | Pano “Bütün adımları bitirdin” mesajına döner |
| Mektup yazılıyor | Çıktı kutusunda “Düşünüyor…”, Durdur düğmesi görünür |
| Mektup hatası | Kutunun altında kısa, çözüm söyleyen Türkçe not |

## 8. Metin kuralları

- Kullanıcıya “sen” diye hitap edilir. Cümleler kısa ve etken çatıdadır.
- Almanca resmî terim ilk geçtiği yerde Türkçe karşılığıyla birlikte verilir: “Adres kaydını yap (Anmeldung)”.
- Düğmeler ne yaptığını söyler: “Taslağı yaz”, “Takvime ekle”, “İlerlemeyi sıfırla”.
- Tutarlar yılıyla birlikte yazılır: “2026’da ayda 992 €”.
- Garanti ya da abartı yok. Belirsiz olan şey belirsiz olarak söylenir ve resmî kaynağa yönlendirilir.
- Türkçe metinde tipografik kesme ve tırnak işareti kullanılır: ’ ve “ ”.

## 9. Erişilebilirlik

- Bütün etkileşimli öğelerde 3 piksellik sarı odak çerçevesi.
- Durak düğmelerinde `aria-pressed` ve adım adını içeren `aria-label`.
- Pano `aria-live="polite"`; değişiklik ekran okuyucuya bildirilir.
- Açık ve koyu tema; `prefers-reduced-motion` açıkken ilerleme çubuğu animasyonu kapalı.
- Durum yalnızca renkle değil, metinle de verilir (“3 gün geçti”, “Tamamlandı”).

## 10. Veri yapısı

Her adım bir nesnedir; yeni yol ya da şehir eklemek için arayüz koduna dokunmak gerekmez.

```js
{
  id: "anmeldung",
  phase: "w2",                 // prep | pre | w2 | m1 | m3
  offset: 14,                  // varış tarihine göre gün
  paths: ["dil","lisans","master","is"],
  requires: ["konut"],         // ön koşul adımlar
  title: "Adres kaydını yap (Anmeldung)",
  what: "…",                   // ya da yola göre { dil: "…", is: "…" }
  where: "city:anmeld",        // şehir verisinden ya da düz metin
  docs: [["Pasaport","tr"], ["Meldebescheinigung","de"]],
  tip: "…",
  de: { terms: [["Termin","randevu"]], say: ["Almanca cümle","Türkçesi"] },
  links: [{ label: "…", url: "…" }]
}
```

Şehir nesnesi: `{ name, anmeld, abh, links: [{ label, url, for }] }`. Şu an 16 şehir ve bir genel seçenek var.

Kullanıcı durumu cihazda saklanır: `{ arrival, visa, path, city, done, bag, view }`.

## 11. Bilinen eksikler

- İçeriğin bir kısmı resmî kaynaktan tek tek doğrulanmadı; her adıma “son kontrol tarihi” alanı eklenmeli.
- Şehir linklerinin çoğu şehrin ana sayfasına gidiyor; doğrudan randevu sayfalarına çevrilmeli.
- Gerçek bildirim yok; yalnızca takvim linki var.
- Aile birleşimi, Chancenkarte ve Ausbildung yolları yok.
- Mektup yazıcı şu an sayfayı açan kişinin Claude hesabıyla çalışıyor; gerçek üründe sunucu ve AI API’si gerekir.
- İngilizce ve Almanca arayüz yok.
