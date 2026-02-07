# Araç Fiyat Tahmin Sistemi (Vehicle Price Prediction)

Bu proje, ikinci el araçların teknik özelliklerine (yıl, motor hacmi, yakıt tüketimi vb.) dayanarak piyasa fiyatını tahmin eden bir Derin Öğrenme (Deep Learning) modelidir.

# Proje Amacı
Mercedes (Merc-Tec) veri setini kullanarak; araç özellikleriyle fiyat arasındaki doğrusal olmayan ilişkiyi modellemek ve kullanıcıdan alınan yeni araç verileriyle tutarlı fiyat tahmini yapmak.

# Veri Mühendisliği ve Analiz 
Modelin başarısını artırmak için kapsamlı veri temizliği ve analiz yapılmıştır:

* **Aykırı Veri (Outlier) Temizliği:** Fiyat dağılımını bozan ve genel tabloyu yansıtmayan en pahalı **%1'lik araç dilimi** veri setinden çıkarıldı. (`len(df) * 0.01`).
* **Hatalı Veri Giderimi:** Veri setinde "1970" model olarak görünen hatalı kayıtlar tespit edilerek temizlendi.
* **Korelasyon Analizi:** `dataframe.corr()` matrisi incelenerek fiyatı en çok etkileyen faktörler (Yıl ve Motor Hacmi) belirlendi.

# Model Mimarisi 
**TensorFlow & Keras** kullanılarak oluşturulan Yapay Sinir Ağı yapısı:
* **Giriş Katmanı:** 6 adet özellik (Year, Mileage, Tax, MPG, EngineSize, vb.)
* **Gizli Katmanlar:** 4 adet Dense katman (her biri 12 nöron, ReLU aktivasyonlu).
* **Çıkış Katmanı:** Tek nöron (Fiyat tahmini için).
* **Optimizer:** Adam
* **Loss Function:** MSE (Mean Squared Error)

# Sonuçlar ve Test
* **Başarım:** Model, eğitim verisinden ayrılan test setindeki araçların fiyatlarını yüksek doğrulukla tahmin etmiştir (Scatter Plot analizinde doğrulandı).
* **Örnek Uygulama:** Modele daha önce görmediği **2020 model, 3999 mil** yapmış bir araç verisi girildiğinde, piyasa koşullarına uygun olarak **~64.000 Birim** fiyat tahmini yapmıştır.

---
# Kullanılan Teknolojiler
`Python` | `TensorFlow` | `Pandas` | `Matplotlib` | `Seaborn` | `Scikit-Learn`

---
*Geliştirici: İlayda Sude Demir*
