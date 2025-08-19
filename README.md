# LSTM Hava Durumu Tahmin Projesi


**LSTM (Long Short-Term Memory)**, tekrarlayan sinir ağlarının (RNN) özel bir türüdür ve özellikle **zaman serisi verilerinde geçmiş bilgiyi öğrenip geleceği tahmin etmek** için kullanılır.
Standart RNN’lerin unutkanlık problemlerini çözmek için tasarlanmış olan LSTM, “hafıza hücreleri” ve kapılar (giriş, unutma, çıktı) sayesinde önemli bilgiyi uzun süre hatırlayabilir.
Bu özellik, finans, hava durumu ve diğer ardışık veri problemlerinde LSTM’i güçlü bir araç haline getirir.

---

## 🔹 Projede Kullanılan Veri Seti
- Veri seti: **Daily Minimum Temperatures in Melbourne**  
- İçerik: Günlük minimum sıcaklıklar, tarih ve sıcaklık sütunları  
- Kaynak: [GitHub Raw Dataset](https://raw.githubusercontent.com/jbrownlee/Datasets/master/daily-min-temperatures.csv)  
- Amaç: Önceki 7 günün sıcaklık bilgisi ile bir sonraki günün sıcaklığını tahmin etmek  

---

## 🔹 Kullanılan Teknolojiler
- Python 3.x  
- Pandas & NumPy (veri işleme)  
- Scikit-learn (MinMaxScaler ile normalize)  
- TensorFlow / Keras (LSTM modeli)

---

## 🔹 Model Yapısı
- Girdi: 7 günün sıcaklık verisi  
- Katmanlar:
  1. **LSTM**: 50 nöron, `tanh` aktivasyon  
  2. **Dense**: Tek çıktı, tahmin edilen sıcaklık  
- Çıkış: Normalized tahmin → `inverse_transform` ile gerçek sıcaklık değerine çevrilir.

---
("Gerçek sıcaklık tahmini:", scaler.inverse_transform(pred
