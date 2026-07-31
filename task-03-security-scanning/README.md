# Task 03 - Security Scanning

## Objective

Pada task ini dilakukan implementasi beberapa tools DevSecOps untuk melakukan security scanning terhadap sebuah aplikasi.

Tools yang digunakan:

- SonarQube (SAST)
- Snyk (SCA)
- Nikto (DAST)

Target aplikasi yang digunakan adalah **OWASP WebGoat** karena aplikasi ini memang dibuat untuk kebutuhan security testing dan memiliki beberapa vulnerability yang dapat dideteksi oleh tools DevSecOps.

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