# Siber Saldırı Risk Tahmini — R & WEKA

2015–2024 küresel siber saldırı verileriyle finansal etki ve risk seviyesi tahmini.

## Problem
Siber saldırıların finansal etkisini ve risk seviyesini önceden tahmin ederek, kurumların kaynaklarını daha etkin yönetmesini ve proaktif stratejiler geliştirmesini sağlamak.

## Veri Seti
- **Kaynak:** Kaggle — "Global Cybersecurity Threats (2015–2024)"
- **Boyut:** 3000 gözlem, 10 değişken (ülke, yıl, saldırı türü, hedef sektör, finansal kayıp vb.)
- **Hedef Değişkenler:** Finansal Etki (Yüksek/Düşük) ve Risk Seviyesi (Düşük/Orta/Yüksek)

## Yöntem
1. **Veri Ön İşleme (R):** Kategorik değişkenlerin faktöre dönüştürülmesi, eksik veri kontrolü, Min-Max normalizasyonu.
2. **Özellik Mühendisliği:** Risk skoru (finansal kayıp, etkilenen kullanıcı, çözüm süresi ortalaması) ve eşit frekanslı kantil ile risk seviyesi oluşturma.
3. **Modelleme:** C4.5 (J48) Karar Ağacı ve Naive Bayes algoritmaları.
4. **Değerlendirme:** %60-40, %70-30, %80-20, %90-10 eğitim-test oranları; stratified sampling; Accuracy, Precision, Recall, F1-Score.

## Sonuçlar
| Model | Veri Bölme Oranı | Doğruluk (Accuracy) |
|-------|------------------|---------------------|
| **J48 (C4.5)** | **%70 - %30** | **~%90** |
| Naive Bayes | %70 - %30 | Daha düşük (J48'e kıyasla) |

* **Risk Seviyesi Tahmini:** J48 algoritması %70-30 bölünmesinde en yüksek başarıyı gösterdi.
* **Finansal Etki Tahmini:** Her iki model de %50-52 aralığında kaldı (çok boyutlu ve karmaşık bir problem olduğu için sınırlı tahmin gücü).

## İş Önerisi
Risk seviyesi sınıflandırması, kurumların olay müdahale ekiplerini önceliklendirmesine ve kaynaklarını daha etkin yönetmesine olanak tanır. J48 gibi yorumlanabilir karar ağaçları, güvenlik analistlerine şeffaf bir karar destek mekanizması sunar.

## Dosyalar
- `R/01_data_prep_and_modeling.R` — Veri temizleme, özellik mühendisliği ve modelleme adımları
- `reports/Donemsonuproje1.pdf` — Detaylı proje raporu (metodoloji, bulgular, tartışma)

## Araçlar ve Kütüphaneler
R (caret, RWeka, dplyr, ggplot2 vb.), WEKA