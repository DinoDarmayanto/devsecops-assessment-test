# Task 03 - Security Scanning

## Objective

Pada task ini dilakukan implementasi beberapa **DevSecOps Security Scanning Tools** untuk melakukan pengujian keamanan terhadap sebuah aplikasi.

Tools yang digunakan meliputi:

- **SonarQube** — Static Application Security Testing (SAST)
- **Snyk** — Software Composition Analysis (SCA)
- **Nikto** — Dynamic Application Security Testing (DAST)

Target aplikasi yang digunakan adalah **OWASP WebGoat**, yaitu aplikasi yang memang dirancang sebagai vulnerable web application untuk kebutuhan security training dan security testing.

---

## Security Scanning Architecture

```text
                    ┌──────────────────────────┐
                    │     OWASP WebGoat        │
                    │     Source Repository    │
                    └─────────────┬────────────┘
                                  │
          ┌───────────────────────┼────────────────────────┐
          │                       │                        │
          ▼                       ▼                        ▼
┌──────────────────┐   ┌──────────────────┐    ┌──────────────────┐
│ SonarQube        │   │ Snyk             │    │ Run WebGoat App  │
│ Static Analysis  │   │ Dependency Scan  │    │ localhost:8080   │
└────────┬─────────┘   └────────┬─────────┘    └────────┬─────────┘
         │                      │                       │
         ▼                      ▼                       ▼
┌──────────────────┐   ┌──────────────────┐    ┌──────────────────┐
│ Bugs             │   │ Vulnerable Lib   │    │ Nikto Scan       │
│ Vulnerabilities  │   │ CVE              │    │ DAST             │
│ Code Smells      │   │ License Issue    │    └────────┬─────────┘
└────────┬─────────┘   └────────┬─────────┘             │
         │                      │                       ▼
         └──────────────┬───────┴───────────────────────┘
                        ▼
              ┌──────────────────────┐
              │ Security Assessment  │
              │      Report          │
              └──────────────────────┘
```

---

## Security Scanning Workflow

Tahapan yang dilakukan pada task ini adalah sebagai berikut:

1. Clone repository **OWASP WebGoat**.
2. Menjalankan **SonarQube Server** menggunakan Docker.
3. Membuat project dan menghasilkan **SonarQube User Token**.
4. Melakukan scanning source code menggunakan **SonarScanner Docker**.
5. Menginstall serta melakukan autentikasi **Snyk CLI**.
6. Melakukan dependency scanning menggunakan **Snyk**.
7. Menjalankan aplikasi **OWASP WebGoat** pada environment lokal.
8. Melakukan vulnerability scanning menggunakan **Nikto** terhadap aplikasi yang sedang berjalan.
9. Menyimpan seluruh hasil scanning sebagai dokumentasi assessment.

---

## Tools Summary

| Tool | Category | Status |
|------|----------|--------|
| SonarQube | SAST | ✅ Completed |
| Snyk | SCA | ✅ Completed |
| Nikto | DAST | ✅ Completed |

---

## Project Structure

```
task-03-security-scanning/
├── README.md
├── WebGoat/
├── sonarqube/
│   ├── README.md
│   └── screenshots/
├── snyk/
│   ├── README.md
│   └── results/
│       ├── snyk-report.txt
│       └── snyk-report.json
└── nikto/
    ├── README.md
    └── results/
        └── nikto-report.txt
```

---

## Output

Output yang dihasilkan pada task ini meliputi:

- SonarQube Analysis Dashboard
- Snyk Scan Report (`.txt` dan `.json`)
- Nikto Scan Report (`.txt`)

Seluruh hasil digunakan sebagai dokumentasi proses **Security Assessment** terhadap aplikasi OWASP WebGoat.