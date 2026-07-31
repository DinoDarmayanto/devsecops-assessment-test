# Task 02 - Git Version Control

## Objective

Melakukan implementasi version control menggunakan Git dan GitHub, mulai dari membuat repository, melakukan clone, membuat branch, commit, hingga push ke remote repository.

---

# Environment

- Git 2.43.0
- GitHub
- Ubuntu 24.04 LTS

---

# Step 1 - Install Git

Melakukan pengecekan apakah Git sudah terinstall.

```bash
git --version
```

Output:

```
git version 2.43.0
```

---

# Step 2 - Configure Git

Melakukan konfigurasi username dan email.

```bash
git config --global user.name "Dino Darmayanto"
git config --global user.email "dinodarmayanto22@gmail.com"
```

Verifikasi konfigurasi.

```bash
git config --list
```

---

# Step 3 - Create GitHub Repository

Membuat repository baru di GitHub dengan nama:

```
devsecops-assessment-test
```

Repository digunakan sebagai remote repository untuk seluruh task assessment.

---

# Step 4 - Clone Repository

Melakukan clone repository dari GitHub ke local machine.

```bash
git clone git@github.com:DinoDarmayanto/devsecops-assessment-test.git
```

Masuk ke directory project.

```bash
cd devsecops-assessment-test
```

---

# Step 5 - Create Branch

Membuat branch sesuai requirement assessment.

```bash
git checkout -b development
```

Kembali ke branch utama.

```bash
git checkout master
```

Apabila branch master belum ada.

```bash
git checkout -b master
```

---

# Step 6 - Create HTML Files

Pada branch **development**

```bash
touch dev.html
```

Isi file:

```html
<h1>Development Branch</h1>
```

Pada branch **master**

```bash
touch mas.html
```

Isi file:

```html
<h1>Master Branch</h1>
```

---

# Step 7 - Git Add

Menambahkan perubahan ke staging area.

```bash
git add .
```

---

# Step 8 - Commit

Melakukan commit perubahan.

```bash
git commit -m "Add HTML file for development branch"
```

dan

```bash
git commit -m "Add HTML file for master branch"
```

---

# Step 9 - Push to GitHub

Push branch development.

```bash
git push origin development
```

Push branch master.

```bash
git push origin master
```

---

# Step 10 - Verification

Melakukan verifikasi pada GitHub bahwa:

- Repository berhasil dibuat.
- Branch `development` tersedia.
- Branch `master` tersedia.
- File `dev.html` terdapat pada branch `development`.
- File `mas.html` terdapat pada branch `master`.

---

# Result

Version control berhasil diimplementasikan menggunakan Git dan GitHub sesuai requirement assessment. Repository berhasil dikelola menggunakan beberapa branch dan seluruh perubahan berhasil di-push ke remote repository.