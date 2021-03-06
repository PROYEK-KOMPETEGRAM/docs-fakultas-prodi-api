# **Spesifikasi Teknis API Fakultas/Kamda - Prodi UPI**

## **A) List Seluruh Fakultas-Kamda dan Prodi**
Menampilkan informasi seluruh fakultas, kampus daerah, dan program studi beserta kode bersangkutan

**URL** : `/fakultas-prodi`

**Link** : [Public API](https://app.kompetegram.com/fakultas-prodi)

**Method** : `GET`

### **Respon Sukses**

**Kode** : 200

**Contoh** :
```json
{
    "data": {
        "universitas": "Universitas Pendidikan Indonesia", 
        "listFakultas": [
            {
            "namaFakultas": "FIP", 
            "listProdi": [
                {
                    "kodeProdi": "A015", 
                    "namaProdi": "Administrasi Pendidikan"
                }, 
                {
                    "kodeProdi": "A025", 
                    "namaProdi": "Bimbingan dan Konseling"
                }]
            }
        ]
    }
}
```

---
## **B) List Seluruh Fakultas-Kamda**
Menampilkan daftar fakultas dan kampus daerah

**URL** : `/fakultas`

**Link** : [Public API](https://app.kompetegram.com/fakultas)

**Method** : `GET`

### **Respon Sukses**

**Kode** : 200

**Contoh** :
```json
{
    "data": [
        {
            "namaFakultas": "FIP"
        }
    ]
}
```
---
## **C) List Program Studi Spesifik dengan Fakultas**
Menampilkan daftar program studi yang spesifik dengan fakultas atau kampus daerah

**URL** : `/fakultas/{namaFakultas}/prodi`

**Link** : [Public API](https://app.kompetegram.com/fakultas/FPIPS/prodi)

**Method** : `GET`

### **Respon Sukses**

**Kode** : 200

**Contoh** :
```json
{
    "data": {
        "namaFakultas": "FIP", 
        "listProdi": [
        {
            "kodeProdi": "A015", 
            "namaProdi": "Administrasi Pendidikan"
        }
    ]}
}
```
### **Respon Gagal**

**Kode** : 404

**Contoh** :
```json
{
    "errors": [
        {
            "status": "404", 
            "title": "Tidak ditemukan", 
            "detail": "Prodi dari fakultas bersangkutan tidak ditemukan"
        }
    ]
}
```
---
## **D) List Seluruh Program Studi**
Menampilkan seluruh program studi

**URL** : `/prodi`

**Link** : [Public API](https://app.kompetegram.com/prodi)

**Method** : `GET`

### **Respon Sukses**

**Kode** : 200

**Contoh** :
```json
{
    "data": [
        {
            "kode": "A015", 
            "prodi": "Administrasi Pendidikan"
        },
        {
            "kode": "A025", 
            "prodi": "Bimbingan dan Konseling"
        }
    ]
}
```
---
## **E) List Program Studi Spesifik**
Menampilkan program studi secara spesifik sesuai kode

**URL** : `/prodi/{kodeProdi}`

**Link** : [Public API](https://app.kompetegram.com/prodi/G505)

**Method** : `GET`

### **Respon Sukses**

**Kode** : 200

**Contoh** :
```json
{
    "data": {
        "kode": "G505", 
        "prodi": "Rekayasa Perangkat Lunak", 
        "fakultas": "Kampus UPI Cibiru"
    }
}
```
### **Respon Gagal**

**Kode** : 404

**Contoh** :
```json
{
    "errors": [
        {
            "status": "404", 
            "title": "Tidak ditemukan", 
            "detail": "Kode prodi tidak ditemukan"
        }
    ]
}
```