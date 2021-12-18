# **Spesifikasi Teknis API Fakultas/Kamda - Prodi UPI**

## **List Seluruh Fakultas dan Prodi**
Menampilkan informasi seluruh fakultas, kampus daerah, dan program studi beserta kode bersangkutan

**URL** : `/fakultas-prodi/`

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
## **List Seluruh Fakultas**
---
## **List Program Studi Spesifik dengan Fakultas**
---
## **List Seluruh Program Studi**
---
## **List Program Studi Spesifik**
