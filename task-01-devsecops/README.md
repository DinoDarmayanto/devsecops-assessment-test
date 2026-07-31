# Task 01 - DevSecOps Fundamentals

## 1. What is DevSecOps?

**DevSecOps** adalah pendekatan dalam software development yang mengintegrasikan **Security** ke dalam proses **Development** dan **Operations**. Berbeda dengan pendekatan tradisional yang melakukan security testing di akhir development, DevSecOps memastikan security dilakukan sejak tahap awal hingga aplikasi berjalan di production.

Tujuan utama DevSecOps adalah menghasilkan aplikasi yang **lebih cepat, lebih aman, dan lebih berkualitas** melalui automation dan continuous security.

---

# 2. Software Development Life Cycle (SDLC)

**Software Development Life Cycle (SDLC)** merupakan tahapan dalam proses pengembangan perangkat lunak.

Tahapan SDLC meliputi:

1. Planning
2. Requirement Analysis
3. Design
4. Development
5. Testing
6. Deployment
7. Maintenance

Pada DevSecOps, proses security tidak hanya dilakukan saat Testing, tetapi diintegrasikan pada setiap tahapan SDLC.

---

# 3. DevSecOps Lifecycle

Secara umum workflow DevSecOps terdiri dari:

```
                        ┌─────────────────────┐
                        │       PLAN          │
                        └─────────┬───────────┘
                                  │
                                  ▼
                        ┌─────────────────────┐
                        │       CODE          │
                        └─────────┬───────────┘
                                  │
                                  ▼
                        ┌─────────────────────┐
                        │       BUILD         │
                        └─────────┬───────────┘
                                  │
                                  ▼
                        ┌─────────────────────┐
                        │       TEST          │
                        └─────────┬───────────┘
                                  │
                                  ▼
                        ┌─────────────────────┐
                        │      RELEASE        │
                        └─────────┬───────────┘
                                  │
                                  ▼
                        ┌─────────────────────┐
                        │      DEPLOY         │
                        └─────────┬───────────┘
                                  │
                                  ▼
                        ┌─────────────────────┐
                        │      OPERATE        │
                        └─────────┬───────────┘
                                  │
                                  ▼
                        ┌─────────────────────┐
                        │      MONITOR        │
                        └─────────────────────┘
```

Pada setiap tahapan tersebut dilakukan automation dan security validation sehingga potensi vulnerability dapat ditemukan lebih awal.

---

# 4. Monolithic Architecture

**Monolithic Architecture** adalah arsitektur aplikasi yang seluruh komponennya berada dalam satu project dan di-deploy sebagai satu kesatuan.

### Advantages

- Mudah dikembangkan untuk aplikasi kecil.
- Deployment lebih sederhana.
- Proses debugging relatif mudah.

### Disadvantages

- Sulit melakukan scaling pada satu module tertentu.
- Deployment menjadi lebih lama ketika project semakin besar.
- Jika satu module mengalami masalah, seluruh aplikasi dapat terdampak.
- Maintenance menjadi lebih kompleks.

---

# 5. Microservices Architecture

**Microservices** membagi aplikasi menjadi beberapa service yang berdiri sendiri.

Setiap service:

- Memiliki business logic sendiri.
- Dapat di-deploy secara independen.
- Dapat menggunakan database yang berbeda.
- Berkomunikasi menggunakan REST API atau Message Broker.

### Advantages

- Independent Deployment.
- Easier Scalability.
- Better Maintainability.
- Fault Isolation.
- Faster Development.

### Disadvantages

- Infrastruktur lebih kompleks.
- Monitoring lebih sulit.
- Membutuhkan service communication.
- Konfigurasi deployment lebih banyak.

---

# 6. Continuous Integration (CI)

**Continuous Integration (CI)** adalah proses otomatis untuk melakukan build dan testing setiap kali developer melakukan push code ke repository.

Contoh tools:

- Jenkins
- GitHub Actions
- GitLab CI

Benefits:

- Early Bug Detection
- Faster Feedback
- Better Collaboration
- Mengurangi konflik saat merge code

---

# 7. Continuous Delivery / Continuous Deployment (CD)

**Continuous Delivery** memungkinkan aplikasi selalu siap untuk di-deploy setelah seluruh testing berhasil.

Sedangkan **Continuous Deployment** akan langsung melakukan deployment ke production secara otomatis apabila seluruh pipeline berhasil.

---

# 8. Security Testing

## SAST (Static Application Security Testing)

SAST melakukan analisis terhadap **source code** tanpa menjalankan aplikasinya.

Example Tool:

- SonarQube

Fungsi:

- Mendeteksi code vulnerability.
- Meningkatkan code quality.
- Menemukan bug sejak proses development.

---

## SCA (Software Composition Analysis)

SCA melakukan analisis terhadap dependency dan third-party library yang digunakan dalam project.

Example Tool:

- Snyk

Fungsi:

- Mendeteksi dependency yang vulnerable.
- Memberikan rekomendasi versi yang lebih aman.
- Monitoring keamanan open-source package.

---

## DAST (Dynamic Application Security Testing)

DAST melakukan scanning terhadap aplikasi yang sedang berjalan.

Example Tool:

- Nikto

Fungsi:

- Mendeteksi web server vulnerability.
- Mengecek misconfiguration.
- Mengidentifikasi security issue pada aplikasi yang sudah running.

---

# 9. Benefits of DevSecOps

Implementasi DevSecOps memberikan beberapa manfaat, antara lain:

- Security diterapkan sejak awal development.
- Vulnerability dapat ditemukan lebih cepat.
- Deployment menjadi lebih cepat dan konsisten.
- Kolaborasi antara Development, Security, dan Operations menjadi lebih baik.
- Mengurangi risiko security issue di production.

---

# 10. Conclusion

DevSecOps merupakan kombinasi antara **Development**, **Security**, dan **Operations** yang terintegrasi dalam satu workflow. Dengan menggunakan tools seperti **Git**, **SonarQube**, **Snyk**, **Nikto**, **Docker**, dan **Kubernetes**, proses pengembangan aplikasi menjadi lebih cepat, aman, dan efisien.