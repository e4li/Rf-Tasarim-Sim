# Project 01 — 2.4 GHz 50 Ω Microstrip Transmission Line

## 🇬🇧 English

### 1. Project Overview

This project investigates the behavior of a 50 Ω microstrip transmission line at 2.4 GHz using Keysight ADS.

The main objective is to understand how the physical parameters of a microstrip line affect its electrical behavior, particularly:

* Characteristic impedance \(Z_0\)
* Reflection coefficient \(S_{11}\)
* Transmission coefficient \(S_{21}\)
* Phase response
* Frequency-dependent behavior

The project was developed as a first practical microwave/RF design study before moving to more advanced structures such as matching networks, filters, power dividers, and active RF circuits.

---

### 2. Design Parameters

The microstrip line was modeled using an MSUB substrate in ADS.

| Parameter                            | Value   |
| ------------------------------------ | ------- |
| Design frequency                     | 2.4 GHz |
| Target characteristic impedance      | 50 Ω    |
| Relative permittivity \(\epsilon_r\) | 4.3     |
| Substrate height \(h\)               | 1.6 mm  |
| Copper thickness                     | 35 µm   |
| Loss tangent                         | ~0.02   |
| Port impedance                       | 50 Ω    |
| Frequency sweep                      | 1–4 GHz |

The microstrip width was calculated using ADS LineCalc to obtain a characteristic impedance close to 50 Ω.

---

### 3. ADS Design

The transmission line was implemented using:

* MSUB
* MLIN
* Term1
* Term2
* S-Parameter simulation

The two ports were terminated with 50 Ω impedances.

The nominal design was used as the reference case for the parameter experiments.

---

### 4. Simulation Results

The nominal transmission line was simulated over the 1–4 GHz frequency range.

The main simulation outputs were:

* \(S_{11}\): input reflection coefficient
* \(S_{21}\): forward transmission
* Smith Chart: impedance/matching behavior

At the nominal design point, the transmission line behaves as a properly matched 50 Ω line around the target design conditions.

![S-Parameter Simulation](03_Simulation/s_parameters.png)

---

## 5. Parameter Experiments

### 5.1 Width Variation — W

The width of the microstrip line was changed while keeping the other parameters constant.

The purpose of this experiment was to observe how the physical width affects the characteristic impedance and therefore the reflection behavior.

#### Observation

When the nominal width is used, the line is designed for approximately 50 Ω.

Increasing the width decreases the characteristic impedance.

Decreasing the width increases the characteristic impedance.

As the characteristic impedance moves away from 50 Ω, impedance mismatch increases and the magnitude of \(S_{11}\) increases.

The Smith Chart also moves away from the center of the chart, indicating increasing impedance mismatch.

**Main conclusion:**

> The width \(W\) is primarily responsible for controlling the characteristic impedance of the microstrip line.

![Width Variation](05_Experiments/W_Variation/width_variation.png)

---

### 5.2 Length Variation — L

The line length was changed while keeping the width fixed at the nominal 50 Ω design value.

Different line lengths were investigated.

#### Observation

Changing the physical length does not fundamentally change the characteristic impedance when the line width and substrate parameters remain unchanged.

Instead, the main effect is on the electrical length and phase response.

For the shorter line, fewer phase variations occur over the same frequency range.

For the longer line, the phase changes more rapidly with frequency and more oscillatory behavior can be observed in the frequency response.

Because the characteristic impedance remains approximately 50 Ω, the impedance matching behavior is preserved.

**Main conclusion:**

> The length \(L\) mainly controls electrical length and phase, while \(W\) primarily controls characteristic impedance.

![Length Variation](05_Experiments/L_Variation/length_variation.png)

---

### 5.3 Frequency Variation

The nominal transmission line was investigated over the 1–4 GHz frequency range.

No physical parameter was changed for this experiment.

The purpose was to observe the frequency-dependent behavior of the transmission line.

The results show that the electrical behavior of a transmission line is frequency dependent. As frequency changes, the electrical length of the line changes, producing corresponding changes in phase and the frequency response.

The 2.4 GHz point was used as the main design frequency.

![Frequency Response](05_Experiments/Frequency_Variation/frequency_response.png)

---

## 6. Smith Chart Analysis

The Smith Chart was used to visualize the impedance and matching behavior of the transmission line.

For the nominal 50 Ω design, the response is located close to the center of the Smith Chart.

When the width is changed, the characteristic impedance changes and the response moves away from the center.

This provides a direct visual relationship between:

$$
W \rightarrow Z_0 \rightarrow \Gamma \rightarrow S_{11}
$$

where:

* \(W\) = microstrip width
* \(Z_0\) = characteristic impedance
* \(\Gamma\) = reflection coefficient
* \(S_{11}\) = input reflection coefficient

![Smith Chart](04_SmithChart/smith_chart.png)

---

## 7. Main Engineering Conclusions

This project demonstrated several fundamental transmission-line concepts:

1. Microstrip width strongly affects characteristic impedance.
2. Impedance mismatch increases the magnitude of \(S_{11}\).
3. Increasing microstrip width generally decreases \(Z_0\).
4. Decreasing microstrip width generally increases \(Z_0\).
5. Changing the line length mainly changes electrical length and phase.
6. A correctly designed 50 Ω transmission line remains matched when only its physical length is changed.
7. Transmission-line behavior is frequency dependent.
8. Smith Charts provide an intuitive way to observe impedance matching.
9. ADS LineCalc can be used to synthesize an initial physical width for a desired characteristic impedance.

---

## 8. Project Structure

```text
01_2.4GHz_Microstrip/
│
├── 01_Design/
│   └── schematic.png
│
├── 02_LineCalc/
│   ├── msub.png
│   └── linecalc.png
│
├── 03_Simulation/
│   └── s_parameters.png
│
├── 04_SmithChart/
│   └── smith_chart.png
│
├── 05_Experiments/
│   ├── W_Variation/
│   ├── L_Variation/
│   └── Frequency_Variation/
│
├── results/
│   └── results.txt
│
└── README.md
```

---

## 9. Tools

* Keysight ADS
* ADS LineCalc
* Smith Chart
* S-Parameter Simulation
* Microstrip Transmission-Line Theory

---

# 🇹🇷 Türkçe

## 1. Proje Özeti

Bu projede 2.4 GHz merkez frekansında çalışan 50 Ω'luk bir mikroşerit iletim hattının davranışı Keysight ADS kullanılarak incelenmiştir.

Temel amaç, mikroşerit hattın fiziksel parametrelerinin elektriksel davranış üzerindeki etkisini pratik olarak gözlemlemektir.

Özellikle:

* Karakteristik empedans \(Z_0\)
* Yansıma katsayısı \(S_{11}\)
* İletim katsayısı \(S_{21}\)
* Faz davranışı
* Frekansa bağlı davranış

incelenmiştir.

Bu çalışma, daha ileri RF/mikrodalga tasarımlarına geçmeden önce yapılan temel bir uygulama projesidir.

---

## 2. Tasarım Parametreleri

Mikroşerit hat ADS içerisindeki MSUB modeli kullanılarak oluşturulmuştur.

| Parametre                              | Değer   |
| -------------------------------------- | ------- |
| Tasarım frekansı                       | 2.4 GHz |
| Hedef empedans                         | 50 Ω    |
| Bağıl dielektrik sabiti \(\epsilon_r\) | 4.3     |
| Substrat yüksekliği \(h\)              | 1.6 mm  |
| Bakır kalınlığı                        | 35 µm   |
| Kayıp tanjantı                         | ~0.02   |
| Port empedansı                         | 50 Ω    |
| Frekans taraması                       | 1–4 GHz |

Mikroşerit genişliği, yaklaşık 50 Ω karakteristik empedans elde etmek amacıyla ADS LineCalc kullanılarak belirlenmiştir.

---

## 3. ADS Tasarımı

Devrede:

* MSUB
* MLIN
* Term1
* Term2
* S-Parameter simülasyonu

kullanılmıştır.

Her iki port 50 Ω olarak tanımlanmıştır.

Nominal tasarım, diğer deneylerde referans olarak kullanılmıştır.

---

## 4. Deneyler

### W Değişimi

W değiştirilerek mikroşerit hattın karakteristik empedansındaki değişim incelenmiştir.

W arttığında karakteristik empedans düşmekte, W azaldığında ise artmaktadır.

Empedans 50 Ω değerinden uzaklaştıkça uyumsuzluk artmakta ve \(S_{11}\) kötüleşmektedir.

**Sonuç:**

> W parametresi esas olarak mikroşerit hattın karakteristik empedansını belirler.

### L Değişimi

W sabit tutulup hattın uzunluğu değiştirilmiştir.

Uzunluğun temel etkisi karakteristik empedansı değiştirmekten ziyade hattın elektriksel uzunluğunu ve faz davranışını değiştirmektir.

Hat uzadıkça frekans eksenindeki faz değişimi daha belirgin hale gelmektedir.

**Sonuç:**

> L parametresi esas olarak elektriksel uzunluğu ve faz davranışını kontrol eder.

### Frekans Değişimi

Nominal tasarım 1–4 GHz arasında incelenmiştir.

Frekans değiştikçe hattın elektriksel uzunluğu değiştiği için \(S_{11}\), \(S_{21}\) ve faz davranışında frekansa bağlı değişimler gözlenmiştir.

2.4 GHz tasarım frekansı olarak kullanılmıştır.

---

## 5. Genel Sonuç

Bu proje sonucunda mikroşerit iletim hatlarında:

$$
W \rightarrow Z_0
$$

ve

$$
L \rightarrow \text{Elektriksel uzunluk / Faz}
$$

ilişkisi pratik olarak incelenmiştir.

Ayrıca Smith Chart kullanılarak empedans uyumu ve yansıma davranışı görsel olarak analiz edilmiştir.

Bu çalışma, daha ileri seviyedeki mikroşerit matching networkleri, filtreler, Wilkinson güç bölücüler ve aktif RF devreleri için temel oluşturmuştur.
