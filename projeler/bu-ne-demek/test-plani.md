# Bu ne demek? – Test planı

Amaç: Claude’un gerçek resmî yazıları doğru okuyup okumadığını ve insanların uygulamayı tekrar kullanmak isteyip istemediğini görmek. Kod yazmaya devam etmeden önce yapılır.

## 1. Belge seti (önce kendin, 10–15 belge)

Farklı türlerden ve dillerden seç. Her satır için bir belge yeter.

| # | Tür | Dil | Neden önemli |
|---|---|---|---|
| 1 | Vergi / borç bildirimi | Almanca | Tutar ve son tarih var |
| 2 | Randevu yazısı (yabancılar dairesi, belediye) | Almanca | Tarih ve saat, yanında getirilecekler |
| 3 | Sigorta ya da sağlık kasası mektubu | Almanca | Uzun, resmî dil |
| 4 | Kira sözleşmesi ya da ev sahibi yazısı | Almanca | Çok sayfalı |
| 5 | Banka yazısı | Almanca ya da Türkçe | Hesap no gibi gizli bilgi (karartmayı dene) |
| 6 | e-Devlet / e-Tebligat çıktısı | Türkçe | Türkçe resmî dil |
| 7 | Trafik cezası | Türkçe ya da Almanca | “Şu tarihe kadar öde, yoksa artar” türü |
| 8 | Okul ya da üniversite yazısı | Herhangi | Son tarih göreli olabilir (“14 gün içinde”) |
| 9 | E-postayla gelen PDF | Herhangi | PDF yolu |
| 10 | Kötü fotoğraf (eğik, gölgeli) | Herhangi | Okunamayanı uyduruyor mu? |

## 2. Her belgede kontrol et

1. **Son tarih doğru mu?** Yanlışsa “Düzenle” ile düzelt.
2. **Tutar doğru mu?** Yanlışsa düzelt.
3. **Yapılacaklar mantıklı mı?** Eksik ya da yanlış adım var mı?
4. **Uydurma var mı?** Yazıda olmayan bir bilgi söylendi mi?
5. **Okunamayan yer** “Emin olamadığım yerler”de söylendi mi?
6. Sonunda **“Bu açıklama doğru mu?”** sorusuna cevap ver. Hatalıysa ne yanlış olduğunu bir cümleyle yaz.

## 3. Sonuçları toplama

Ayarlar → **Test notlarını kopyala**. Çıkan metni buraya ya da bir tabloya yapıştır. Bu metinde dosya numarası ve özet yer almaz.

Bakılacak sayılar:
- Doğru / hatalı oranı. Hedef: 10 belgenin en az 8’i doğru.
- Elle düzeltilen tarih ve tutar sayısı. Hedef: sıfıra yakın.
- Hataların türü: tarih mi, tutar mı, yanlış anlama mı, uydurma mı?

## 4. Başkalarıyla test (10 kişi)

- Almanya’daki tanıdıklar, anne-babasının işlerini takip edenler, öğrenciler.
- Artifact linkini Paylaş menüsünden onlarla paylaş. Kendi Claude hesaplarıyla açacaklar.
- Onlara sadece şunu söyle: “Elindeki bir resmî yazının fotoğrafını çek, ne çıktığına bak.” Nasıl kullanılacağını anlatma; nerede takıldıklarını gözle.
- Sonra üç soru sor:
  1. Açıklama doğru muydu?
  2. Bir dahaki yazıda tekrar kullanır mısın?
  3. Bunun için ayda ne öderdin? (0 da geçerli bir cevap)

## 5. Karar

- Doğruluk iyi ve insanlar tekrar kullanmak istiyorsa → Prototip 2 (sunucu, gerçek bildirim, hesap).
- Doğruluk kötüyse → hataların türüne göre talimatı ve fotoğraf hazırlamayı düzelt, testi tekrarla.
- İnsanlar ilgisizse → hangi kısmı sevdiklerine bak (örneğin sadece cevap mektubu) ve oraya odaklan.
