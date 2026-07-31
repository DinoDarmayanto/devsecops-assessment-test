# Snyk (SCA)

## Description

Snyk merupakan **Software Composition Analysis (SCA)** tool yang digunakan untuk melakukan security scanning terhadap dependency atau third-party library yang digunakan oleh sebuah aplikasi.

Berbeda dengan SonarQube (SAST) yang menganalisis source code, Snyk berfokus pada library yang digunakan oleh project dan membandingkannya dengan database vulnerability (CVE) yang selalu diperbarui.

---

## Objective

Pada assessment ini, Snyk digunakan untuk melakukan scanning dependency pada aplikasi **OWASP WebGoat** guna mengetahui apakah terdapat library yang memiliki vulnerability.

Target:

```
OWASP WebGoat Source Code
```

---

## Deployment Architecture

```
                  +--------------------------+
                  |      OWASP WebGoat       |
                  |      Maven Project       |
                  +------------+-------------+
                               |
                        Read Dependencies
                               |
                               v
                  +------------+-------------+
                  |          Snyk CLI        |
                  |   Software Composition   |
                  |       Analysis (SCA)     |
                  +------------+-------------+
                               |
                               |
                               v
                   Snyk Vulnerability Database
                               |
                               |
                               v
                     Security Scan Result
```

---

## Prerequisites

Pastikan environment berikut telah tersedia.

- NodeJS
- NPM
- Snyk CLI
- Maven
- Java
- Internet Connection
- OWASP WebGoat Source Code

Verifikasi instalasi:

```bash
snyk --version
```

---

## Authentication

Sebelum melakukan scanning, lakukan autentikasi ke akun Snyk.

```bash
snyk auth
```

Verifikasi akun:

```bash
snyk whoami
```

Contoh hasil:

```
dinodarmayanto22
```

---

## Target Project

Masuk ke direktori project WebGoat.

```bash
cd ~/Dokumen/devsecops-assessment-test/task-03-security-scanning/WebGoat
```

---

## Scan Dependency

Menjalankan dependency scan:

```bash
snyk test
```

Menyimpan output ke file text:

```bash
mkdir -p ../snyk/results

snyk test | tee ../snyk/results/snyk-report.txt
```

Menyimpan output dalam format JSON:

```bash
snyk test --json > ../snyk/results/snyk-report.json
```

---

## Output Files

Hasil scanning berhasil disimpan pada folder berikut.

```
task-03-security-scanning/
└── snyk/
    ├── README.md
    └── results
        ├── snyk-report.txt
        └── snyk-report.json
```

---

## Generated Reports

Output yang dihasilkan terdiri dari dua format.

### Text Report

```
results/snyk-report.txt
```

Berisi hasil scanning yang dapat dibaca langsung melalui terminal maupun text editor.

### JSON Report

```
results/snyk-report.json
```

Berisi hasil scanning dalam format JSON sehingga dapat digunakan untuk proses analisis maupun integrasi dengan tools lain.

---

## Scan Result

Scanning dependency berhasil dijalankan menggunakan **Snyk CLI** terhadap project **OWASP WebGoat**.

Snyk melakukan pemeriksaan terhadap dependency project dan membandingkannya dengan vulnerability database untuk mendeteksi package yang memiliki potensi kerentanan keamanan.

Detail hasil scanning tersimpan pada:

- `results/snyk-report.txt`
- `results/snyk-report.json`

---

## Conclusion

Snyk berhasil digunakan sebagai **Software Composition Analysis (SCA)** tool pada assessment ini.

Dependency scanning berhasil dilakukan terhadap project **OWASP WebGoat**, dan hasilnya telah disimpan dalam format **Text Report** serta **JSON Report** sehingga dapat digunakan sebagai dokumentasi maupun analisis vulnerability pada dependency aplikasi.