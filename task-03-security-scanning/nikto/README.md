# Nikto (DAST)

## Description

Nikto merupakan Dynamic Application Security Testing (DAST) tool yang digunakan untuk melakukan scanning terhadap web application yang sedang berjalan.

## Purpose

- Detect Security Misconfiguration
- Detect Missing Header
- Detect Information Disclosure
- Detect Common Vulnerability

## Target

```
http://localhost:8080
```

## Scan Command

```bash
nikto -h http://localhost:8080
```

## Expected Output

- Server Information
- Missing Header
- Directory Listing
- Security Finding

## Result

_(akan diisi setelah proses scanning selesai)_