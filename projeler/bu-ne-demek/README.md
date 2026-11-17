# Bu ne demek?

Resmî yazının fotoğrafını çek; ne dediğini, ne yapman gerektiğini ve son tarihi sade dille öğren.

Vergi yazısı, tebligat, sigorta mektubu, kira sözleşmesi… Hangi ülkeden, hangi dilde gelirse gelsin, uygulama yazıyı okur ve şunları söyler:

- **Kısaca:** Kim göndermiş, neden, senin için ne anlama geliyor
- **Son tarihler:** Ne zamana kadar ne yapmalısın, takvime tek tıkla ekle
- **Yapman gerekenler:** Adım adım, işaretlenebilir liste
- **Tutarlar** ve **hiçbir şey yapmazsan ne olur**
- **Yazıdaki terimler:** Resmî kelimelerin sade anlamı
- **Cevap yaz:** Süre uzatma, taksit ya da itiraz için yazının dilinde mektup taslağı ve çevirisi

Bütün belgeler son tarihleriyle birlikte “Belgelerim” listesinde durur. En yakın son tarih ana ekranın en üstünde görünür.

## Nasıl denenir?

1. `index.html` dosyasını tarayıcıda aç.
2. Anahtarsız görmek için **Örnek belgeyle dene**’ye bas.
3. Kendi belgen için [Google AI Studio](https://aistudio.google.com/apikey)’dan ücretsiz bir Gemini API anahtarı al ve ⚙ Ayarlar’a yapıştır.

## Teknik

- Tek HTML dosyası, kütüphane yok, sunucu yok
- Google Gemini API (görsel + PDF okuma, JSON şeması ile yapılandırılmış çıktı)
- Veriler yalnızca tarayıcıda (`localStorage`); fotoğraflar saklanmaz
- Ankommen ile aynı görsel dil; açık ve koyu tema

📐 [Tasarım dokümanı](tasarim.md)

## Durum

- Prototip 1 – Kasım 2026
- Sıradaki adım: 10 kişiyle gerçek belgeler üzerinde test

⚠️ Yapay zekâ hata yapabilir. Tarih ve tutarları her zaman asıl yazıdan kontrol et. Hukuki danışmanlık değildir.
