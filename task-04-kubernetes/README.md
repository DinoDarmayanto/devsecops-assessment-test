# Task 04 - Kubernetes

## Objective

Pada task ini dilakukan implementasi **Kubernetes** menggunakan **Minikube** sebagai local Kubernetes Cluster.

Deployment yang dilakukan adalah menjalankan **Apache HTTP Server** di dalam Kubernetes, kemudian membuat **Service** agar aplikasi dapat diakses melalui browser.

---

## Technologies

Tools yang digunakan pada task ini:

- Kubernetes
- Minikube
- Docker
- kubectl
- Apache HTTP Server (`httpd:2.4`)

---

## Deployment Architecture

```text
                    +----------------------+
                    |      Browser         |
                    |  http://localhost    |
                    +----------+-----------+
                               |
                               |
                     minikube service
                               |
                               ▼
                  +-------------------------+
                  |     apache-service      |
                  |     Kubernetes Service  |
                  +------------+------------+
                               |
                               |
                               ▼
                  +-------------------------+
                  |      Apache Pod         |
                  |      httpd:2.4          |
                  +------------+------------+
                               |
                               ▼
                  +-------------------------+
                  |     Apache Deployment   |
                  +------------+------------+
                               |
                               ▼
                  +-------------------------+
                  |      Minikube Cluster   |
                  +-------------------------+
```

---

## Project Structure

```
task-04-kubernetes/
├── README.md
├── manifests
│   ├── apache-deployment.yaml
│   └── apache-service.yaml
└── outputs
    ├── apache-homepage.html
    ├── kubectl-get-deployments.txt
    ├── kubectl-get-nodes.txt
    ├── kubectl-get-pods.txt
    ├── kubectl-get-services.txt
    └── minikube-service-url.txt
```

---

## Prerequisites

Pastikan environment telah terinstall:

- Docker
- Kubernetes CLI (`kubectl`)
- Minikube

Verifikasi versi:

```bash
docker --version
kubectl version --client
minikube version
```

---

## Start Kubernetes Cluster

Menjalankan Minikube:

```bash
minikube start
```

Verifikasi node:

```bash
kubectl get nodes
```

Output command disimpan pada:

```
outputs/kubectl-get-nodes.txt
```

---

## Create Apache Deployment

Deployment Apache dilakukan menggunakan manifest Kubernetes.

File manifest:

```
manifests/apache-deployment.yaml
```

Deploy:

```bash
kubectl apply -f apache-deployment.yaml
```

Output:

```
deployment.apps/apache-deployment created
```

Verifikasi deployment:

```bash
kubectl get deployments
```

Output disimpan pada:

```
outputs/kubectl-get-deployments.txt
```

---

## Create Kubernetes Service

Service dibuat untuk mengekspos Apache Pod.

Manifest:

```
manifests/apache-service.yaml
```

Deploy Service:

```bash
kubectl apply -f apache-service.yaml
```

Output:

```
service/apache-service created
```

Verifikasi Service:

```bash
kubectl get svc
```

Output disimpan pada:

```
outputs/kubectl-get-services.txt
```

---

## Verify Running Pod

Memastikan Pod berhasil dijalankan.

```bash
kubectl get pods
```

Status Pod yang diharapkan:

```
Running
```

Output command disimpan pada:

```
outputs/kubectl-get-pods.txt
```

---

## Access Apache Application

Mengakses aplikasi menggunakan Minikube.

```bash
minikube service apache-service --url
```

URL yang dihasilkan disimpan pada:

```
outputs/minikube-service-url.txt
```

Untuk memastikan aplikasi berhasil diakses, halaman Apache disimpan menggunakan:

```bash
curl $(minikube service apache-service --url)
```

Output halaman disimpan pada:

```
outputs/apache-homepage.html
```

---

## Output Files

Seluruh hasil deployment terdokumentasi pada folder berikut.

```
outputs/
├── apache-homepage.html
├── kubectl-get-deployments.txt
├── kubectl-get-nodes.txt
├── kubectl-get-pods.txt
├── kubectl-get-services.txt
└── minikube-service-url.txt
```

---

## Result

Deployment Apache Web Server berhasil dijalankan menggunakan Kubernetes pada Minikube.

Beberapa proses yang berhasil dilakukan:

- Minikube Cluster berhasil dijalankan.
- Apache Deployment berhasil dibuat.
- Apache Service berhasil dibuat.
- Pod berhasil berjalan (Running).
- Service berhasil diakses menggunakan Minikube.
- Halaman Apache berhasil diakses melalui browser.
- Seluruh output command berhasil disimpan sebagai dokumentasi assessment.

---

## Conclusion

Task ini berhasil mengimplementasikan deployment sederhana menggunakan Kubernetes pada Minikube.

Proses deployment dilakukan menggunakan manifest Kubernetes (`Deployment` dan `Service`), kemudian diverifikasi menggunakan `kubectl`. Seluruh hasil deployment disimpan dalam bentuk **raw output (.txt)** dan **HTML response** sebagai dokumentasi, sehingga lebih mudah untuk direview dibandingkan hanya menggunakan screenshot.