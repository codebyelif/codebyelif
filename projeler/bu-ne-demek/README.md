# Bu ne demek?

Resmî yazının fotoğrafını çek; ne dediğini, ne yapman gerektiğini ve son tarihi sade dille öğren.

Vergi yazısı, tebligat, sigorta mektubu, kira sözleşmesi… Hangi ülkeden, hangi dilde gelirse gelsin, uygulama yazıyı okur ve şunları söyler:

- **Kısaca:** Kim göndermiş, neden, senin için ne anlama geliyor
- **Son tarihler:** Ne zamana kadar ne yapmalısın, takvime tek tıkla ekle
- **Yapman gerekenler:** Adım adım, işaretlenebilir liste
- **Tutarlar** ve **hiçbir şey yapmazsan ne olur**
- **Yazıdaki terimler:** Resmî kelimelerin sade anlamı
- **Cevap yaz:** Süre uzatma, taksit ya da itiraz için yazının dilinde mektup taslağı ve çevirisi
- **Karart:** Göndermeden önce kimlik no, adres, hesap no gibi bilgilerin üzerini parmağınla kapat
- **Düzelt:** Tarih ya da tutar yanlış okunduysa elle düzelt, eksik son tarihi ekle
- **Hatırlat ve paylaş:** Son tarihi ve 3 gün öncesini takvime ekle; özeti bir yakınına gönder

Bütün belgeler son tarihleriyle birlikte “Belgelerim” listesinde durur. En yakın son tarih ana ekranın en üstünde görünür.

## Nasıl denenir?

**claude.ai’de (en kolayı):** Artifact linkini aç. Uygulama senin Claude hesabınla çalışır, API anahtarı gerekmez; ilk kullanımda izin sorar. Fotoğraf, PDF ve metin gönderilebilir.

**Başka bir yerde (GitHub Pages ya da dosya):**
1. `index.html` dosyasını tarayıcıda aç.
2. Anahtarsız görmek için **Örnek belgeyle dene**’ye bas.
3. Kendi belgen için [Claude Console](https://platform.claude.com)’dan bir API anahtarı al ve ⚙ Ayarlar’a yapıştır. Bir belge yaklaşık 5–15 sent tutar.

## Teknik

- Tek HTML dosyası, sunucu yok
- Claude: claude.ai içinde kullanıcının kendi hesabıyla, başka yerde resmî Anthropic JavaScript kütüphanesiyle (`@anthropic-ai/sdk`) ve kullanıcının API anahtarıyla
- PDF’ler tarayıcıda pdf.js ile sayfa görsellerine çevrilir; dik sayfalar ayrıntı kaybolmasın diye ikiye bölünerek gönderilir
- JSON şeması ile yapılandırılmış çıktı
- Veriler yalnızca tarayıcıda (`localStorage`); fotoğraflar saklanmaz
- Ankommen ile aynı görsel dil; açık ve koyu tema

📐 [Tasarım dokümanı](tasarim.md)

## Durum

- Prototip 1.2 – Kasım 2026: sayfa bölme, düzeltme, karartma, PDF, hatırlatma ve paylaşma eklendi
- Sıradaki adım: [test planı](test-plani.md) ile gerçek belgeler üzerinde test

⚠️ Yapay zekâ hata yapabilir. Tarih ve tutarları her zaman asıl yazıdan kontrol et. Hukuki danışmanlık değildir.
