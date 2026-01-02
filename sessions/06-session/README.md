# Session 06 – Kubernetes API Server

در این جلسه به بررسی عمیق **API Server** به‌عنوان قلب Control Plane در Kubernetes پرداخته شد و مسیر کامل پردازش درخواست‌ها، امنیت، و ارتباط با etcd بررسی گردید.

---

## 📘 Topics Covered

### Core Concepts

- API Server Architecture & RESTful API
- Resource objects & API groups (core, apps, batch, etc.)
- API versioning (v1, v1beta1)
- Custom Resource Definitions (CRD)
- Static Pods

### Security & Request Flow

- TLS configuration & certificates
- Authentication → Authorization → Admission → Validation → Storage → Response
- RBAC & Admission control (mutating/validating)
- Audit logging

### Internal Communication

- API Server binary structure
- HTTP request lifecycle
- gRPC communication with etcd
- etcd request batching

---

## 🎯 تکالیف عملی

### تکلیف ۱: Deployment و etcd Backup

1. یک Deployment موجود (nginx) را بررسی کنید
2. از etcd بکاپ بگیرید
3. Deployment را حذف کنید
4. تغییرات را در etcd بررسی کنید

### تکلیف ۲: بررسی رفتار Static Pod

1. با استفاده از `kubectl delete pod` سعی کنید API Server Pod را حذف کنید
2. مشاهده کنید که Pod دوباره به‌صورت خودکار ساخته می‌شود
3. دلیل این رفتار را توضیح دهید (Static Pod)
4. همچنین ولیدیت کنید که این پاد پاک نمیشود در اون لحظه

---

## 📂 فایل‌های مرجع

👉 [`k8s-resources/`](./k8s-resources)

---

## 📚 Self-Study Topics

مطالب زیر باید به‌صورت خودخوان مطالعه شوند:

- آشنایی با Kubernetes SIGs و نقش آن‌ها
- نحوه استفاده از Protobuf در API Server
- مفهوم rc.d در سیستم‌عامل لینوکس
- الگوریتم Raft و نحوه انتخاب Leader