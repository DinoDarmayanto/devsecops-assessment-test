# Nikto (DAST)

## Description

Nikto merupakan **Dynamic Application Security Testing (DAST)** tool yang digunakan untuk melakukan security assessment terhadap web application yang sedang berjalan (*running application*).

Berbeda dengan SonarQube yang melakukan analisis source code (*SAST*), Nikto melakukan scanning langsung terhadap web server untuk mengidentifikasi potensi vulnerability, security misconfiguration, serta informasi yang dapat diungkap oleh server.

---

## Objective

Pada assessment ini, Nikto digunakan untuk melakukan scanning terhadap aplikasi **OWASP WebGoat** yang berjalan pada environment lokal.

Target:

```
http://localhost:8080
```

---

## Deployment Architecture

```
                 +----------------------+
                 |   OWASP WebGoat      |
                 |   localhost:8080     |
                 +----------+-----------+
                            ^
                            |
                       HTTP Request
                            |
                 +----------+-----------+
                 |       Nikto          |
                 |     DAST Scanner     |
                 +----------------------+
```

---

## Prerequisites

Pastikan environment berikut sudah siap:

- Nikto telah terinstall
- OWASP WebGoat berhasil dijalankan
- Target dapat diakses melalui browser

Verifikasi versi Nikto:

```bash
nikto -Version
```

---

## Verify Target

Pastikan WebGoat dapat diakses melalui browser.

```
http://localhost:8080
```

---

## Scan Command

Menjalankan scanning:

```bash
nikto -h http://localhost:8080
```

Menyimpan hasil scanning ke file:

```bash
mkdir -p outputs

nikto \
-h http://localhost:8080 \
-o outputs/nikto-report.txt
```

---

## Output Files

Hasil scanning disimpan pada:

```
task-03-security-scanning/
└── nikto/
    ├── README.md
    └── outputs/
        └── nikto-report.txt
```

---

## Scan Result

Scanning berhasil dijalankan terhadap aplikasi WebGoat dan menghasilkan laporan dalam bentuk text file.

Lokasi laporan:

```
outputs/nikto-report.txt
```

Laporan tersebut berisi informasi hasil scanning yang dihasilkan oleh Nikto terhadap target aplikasi.

---

## Conclusion

Nikto berhasil digunakan sebagai **Dynamic Application Security Testing (DAST)** tool untuk melakukan scanning terhadap aplikasi **OWASP WebGoat** yang berjalan pada `http://localhost:8080`.

Output hasil scanning berhasil disimpan dalam file:

```
outputs/nikto-report.txt
```

Hasil tersebut akan digunakan sebagai dasar analisis security findings pada tahap berikutnya.