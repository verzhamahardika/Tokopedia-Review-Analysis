# Sentiment Analysis Ulasan Aplikasi Tokopedia menggunakan IBM Granite LLM

## 🔍 Project Overview

Proyek ini bertujuan untuk menganalisis sentimen dari ulasan pengguna aplikasi Tokopedia secara otomatis menggunakan teknologi Large Language Model (LLM) dari IBM, yaitu Granite.
Permasalahan yang diangkat adalah bagaimana memanfaatkan model AI untuk memahami opini pengguna dalam bentuk teks dan mengklasifikasikannya ke dalam kategori positif, netral, atau negatif.

Ulasan pengguna sering kali memiliki gaya bahasa yang beragam, seperti sarkasme, singkatan, atau emotikon. Oleh karena itu, pendekatan berbasis LLM digunakan karena lebih mampu memahami konteks linguistik dibanding pendekatan berbasis keyword atau rule-based.

## 🧪 Analysis Process

1. Data Preparation
   Dataset berisi kolom content (ulasan pengguna) dan score (nilai 1–5). Label manual dibentuk berdasarkan aturan: - Skor 1–2: Negatif - Skor 3: Netral - Skor 4–5: Positif

2. Model Setup
   Model yang digunakan adalah ibm/granite-13b-instruct-v2 dari IBM Watsonx AI. Model ini diakses melalui API menggunakan SDK Watsonx.

3. Prompt Engineering
   Model diberi prompt yang menjelaskan instruksi klasifikasi. Setiap ulasan dikirim sebagai input dan model mengembalikan satu dari tiga label.

4. Inference & Evaluation
   Sebagian data (10 sampel acak) diproses menggunakan model Granite. Hasil prediksi dibandingkan dengan label manual untuk mengevaluasi konsistensi model.

## 📊 Insight & Findings

Mayoritas prediksi dari Granite konsisten dengan label manual, terutama untuk ulasan dengan ekspresi yang eksplisit.

Untuk ulasan yang ambigu (misalnya bernada netral atau mengandung sarkasme), Granite menunjukkan pemahaman yang lebih baik dibanding klasifikasi berbasis angka score.

Model dapat menyesuaikan respons terhadap variasi bahasa pengguna (bahasa informal, emoticon, dll).

Hal ini membuktikan bahwa LLM cocok untuk tugas klasifikasi opini dalam bentuk teks pendek.

Contoh Hasil:
| Ulasan Singkat | Label Manual | Granite Prediksi |
| ----------------------------------------- | ------------ | ---------------- |
| Aplikasinya sangat lambat dan bikin kesel | Negatif | Negatif |
| Top banget, cepat dan ramah | Positif | Positif |
| Lumayan sih, tapi belum yakin | Netral | Netral |

## ✅ Conclusion & Recommendation

Kesimpulan:
Model Granite dapat digunakan untuk mengotomatisasi klasifikasi sentimen secara cepat dan cukup akurat, bahkan dalam kondisi teks ulasan yang tidak terstruktur.

Rekomendasi:
Solusi ini dapat diintegrasikan dalam sistem monitoring feedback pelanggan, membantu tim produk memahami keluhan dan apresiasi pengguna dalam skala besar.
Model juga bisa dikembangkan untuk deteksi opini terhadap fitur tertentu di aplikasi Tokopedia (feature-level sentiment analysis).

## 🤖 AI Support Explanation

- Model yang digunakan: ibm/granite-13b-instruct-v2
- Platform: IBM Watsonx Foundation Models
- Fungsi: Classification
- Cara kerja: Model menerima prompt berisi instruksi klasifikasi dan teks ulasan, lalu mengembalikan label sebagai prediksi.
- Keunggulan AI:
  LLM mampu memahami konteks, emosi, serta variasi gaya bahasa secara lebih akurat dibanding pendekatan tradisional.
  Hal ini mendukung aplikasi pada use-case real seperti monitoring feedback atau review e-commerce secara otomatis.

## 🔗 Raw Dataset Link

📎 Link Dataset: [Google Drive](https://drive.google.com/file/d/16rrtwb3uzMtg_Dd0TbE0smFco26d4mza/view?usp=sharing).
