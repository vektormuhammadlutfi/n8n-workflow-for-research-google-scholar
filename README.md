# Akademik Workflow (n8n)

Workflow ini adalah otomatisasi n8n untuk menghasilkan draft ide skripsi/thesis berbasis data Google Scholar, lalu mengirimkannya ke Telegram. Cocok untuk asisten akademik multidisiplin yang ingin riset cepat dan terstruktur.

![Workflow Diagram](https://raw.githubusercontent.com/vektormuhammadlutfi/n8n-workflow-for-research-google-scholar/main/image.png)

## Fitur Utama

- **Input Chat**: Pengguna memasukkan kata kunci riset via chat window.
- **Ekstraksi Kata Kunci**: Workflow mengambil kata kunci dari input (misal: `kata_kunci="smart city infrastructure"`).
- **Google Scholar Search**: Mengambil hasil pencarian Google Scholar menggunakan SerpAPI.
- **Format Data**: Hasil pencarian diolah menjadi format literatur terstruktur.
- **Prompt LLM**: Data literatur digunakan sebagai sumber utama untuk membuat draft ide skripsi/thesis dengan format akademik dan emoji.
- **Split & Send Telegram**: Hasil akhir dipecah agar sesuai batas karakter Telegram, lalu dikirim ke chat Telegram.

## Alur Workflow

1. **Chat Trigger**  
  Pengguna mengirim pesan melalui chat window.

2. **Parse Input**  
  Ekstrak kata kunci dari input chat.

3. **SerpApi Search**  
  Cari literatur terkait di Google Scholar.

4. **Prepare Batch Prompt**  
  Format hasil pencarian menjadi daftar literatur.

5. **Basic LLM Chain**  
  Generate draft ide skripsi/thesis menggunakan LLM (OpenRouter).

6. **Split Message**  
  Pisahkan hasil agar tidak melebihi batas karakter Telegram.

7. **Telegram Send**  
  Kirim hasil ke Telegram.

## Format Output

Output berisi:
- Alternatif judul skripsi/thesis
- Latar belakang
- Urgensi penelitian
- Langkah penelitian (opsional)
- Metodologi
- Indikator keberhasilan
- Analisis posisi ide
- Referensi jurnal (dengan link Google Scholar)

## Kebutuhan

- Akun SerpAPI
- Akun OpenRouter (LLM)
- Akun Telegram & Bot Token
- n8n v1.7+ (dengan node langchain dan serpapi)

## Cara Pakai

1. Import workflow ke n8n.
2. Isi kredensial SerpAPI, OpenRouter, dan Telegram.
3. Jalankan workflow.
4. Kirim pesan dengan format:  
  `kata_kunci="topik penelitian"`

## Lisensi

© 2025 Lutfi 
Workflow ini untuk demo dan riset akademik.
