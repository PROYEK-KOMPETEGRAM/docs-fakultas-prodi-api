# **Dokumentasi Teknis dan Spesifikasi Public API (Fakultas-Prodi)**

Dokumentasi Teknis dan Spesifikasi ini dibuat untuk memberi penjelasan terkait open proyek KOMPETEGRAM kepada para anggotanya terutama divisi *Research Group*
### **Daftar Isi**
- [1. Penjelasan Umum]()
- [2. Penjelasan Proyek]()
- [3. Luaran]()
- [4. Endpoint API]()
- [5. Spesifikasi]()
- [6. Infrastruktur]()
- [7. Indikator Pengujian]()
- [8. Sampel Program]()
- - -
## **1. Penjelasan Umum**
Dokumentasi Teknis dan Spesifikasi ini dibuat untuk memberi penjelasan terkait open proyek pertama KOMPETEGRAM kepada para anggotanya.
- - -
## **2. Penjelasan Proyek**
Proyek yang diangkat adalah API publik yang berisi data dan informasi fakultas, kampus daerah, dan program studi yang ada di Universitas Pendidikan Indonesia (UPI). 
- - -
## **3. Luaran**
Proyek ini bersifat individu, sehingga terdapat pemilihan program terbaik melalui pengujian dengan *tools* Apache Bench. **Silakan**, lihat pada bagian [indikator]() untuk mengetahui bobot yang diujikan.
- - -
## **4. Endpoint API**
Terdapat lima *endpoint* URL (*resources*) API yang diharapkan dibuat oleh rekan-rekan semua :
### A. Endpoint untuk seluruh fakultas dan program studi :
```
GET /fakultas-prodi
```
### B. Endpoint untuk list seluruh fakultas :
```
GET /fakultas
```
### C. Endpoint untuk list program studi sesuai fakultas :
```
GET /fakultas/{namaFakultas}/prodi
```
### D. Endpoint untuk list seluruh program studi :
```
GET /prodi
```
### E. Endpoint untuk program studi spesifik :
```
GET /prodi/{kodeProdi}
```
- - -
## **5. Spesifikasi**
Saat ini kami telah menyediakan spesifikasi API dan kerangka pesan dari masing-masing *endpoint*. Format yang dipakai adalah **RAML** atau *RESTful API Modelling Language* (mirip seperti YAML). Silakan kunjungi pada folder `raml-specs` atau klik beberapa link berikut :
- [Spesifikasi Endpoint Seluruh Fakultas dan Prodi](raml-specs/api.fakultas-prodi.raml)
- [Spesifikasi Endpoint Fakultas](raml-specs/api.fakultas.raml)
- [Spesifikasi Endpoint Program Studi](raml-specs/api.prodi.raml)

Untuk memahami dan membaca mengenai format RAML, silakan kunjungi referensi atau tutorial [Part 1](https://raml.org/developers/raml-100-tutorial) dan [Part 2](https://raml.org/developers/raml-200-tutorial) dari situs RAML-nya

Selain itu, spesifikasi API yang kita buat mengacu pada *best practice* komunitas dari **JSON API**. Silakan kunjungi referensi berikut untuk membaca lebih lanjut mengenai [Spesifikasi JSON API](https://jsonapi.org/)
- - - 
## **6. Infrastruktur**
Terdapat batasan yang disesuaikan dengan infrastruktur yang dimiliki oleh KOMPETEGRAM
### A. Bahasa Pemrograman 
Sesuai kemampuan dari infrastruktur hosting yang dimiliki, maka kami hanya mengizinkan 5 (lima) bahasa pemrograman berikut dalam proyek ini :
- PHP
- Python
- Ruby
- NodeJS
- Perl
### B. Database
KOMPETEGRAM telah menyediakan dua infrastruktur *database* yang akan digunakan dan dapat dipilih salah satunya :
- PostgreSQL (server Azure - US)
- MongoDB Atlas (server AWS - Singapore)

Informasi selengkapnya terkait kredensial dan tata cara penggunaan dapat melihat pada *handout* yang diberikan
- - -
## **7. Indikator Pengujian**
Kami akan melakukan pengujian *load test* **hanya pada satu endpoint** saja, yaitu endpoint seluruh fakultas dan prodi atau `GET /fakultas-prodi`. Pengujian dilakukan dengan bantuan ApacheBench dengan banyaknya percobaan serta parameter sebagai berikut :
| No Uji | Jumlah | Concurrency |
| -------| -------| ------------|
| 1 | 10 | - |
| 2 | 50 | - |
| 3 | 100 | - |
| 4 | 10 | 10 |
| 5 | 100 | 10 |

Keseluruhan pengujian akan kami akumulasikan pada hasil *request per second*. Program yang memiliki hasil *request per second* terbesar, spesifikasi API yang sesuai, serta memiliki *rate* keberhasilan *request* mencapai 100% adalah yang terpilih.
- - -

## **8. Sampel Program**
Kami juga telah menyediakan sampel program API ini yang dapat digunakan sebagai acuan ataupun referensi. Program ini dibuat dengan bahasa **Python** dan *framework* **Flask** serta menggunakan database **MongoDB Atlas**

[Kunjungi repositori sampel program]()
- - -
### ***Disclaimer***
Proyek ini tidak berafliasi ataupun bekerja sama dengan pihak Universitas Pendidikan Indonesia (UPI). Adapun pembuatan API ini bertujuan untuk memberi kemudahan bagi *developer* khususnya mahasisa UPI untuk mengkonsumsi API yang berisi informasi fakultas, kampus daerah, dan program studi.


