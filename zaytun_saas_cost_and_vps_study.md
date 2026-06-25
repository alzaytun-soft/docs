# دراسة تكلفة وتشغيل منصة زيتون سوفت SaaS — ملف موحد

## 1. قاعدة الدراسة المعتمدة

هذه الدراسة مبنية على أن مشروع زيتون سوفت تم بناؤه من الصفر بواسطة الفريق، وأن تكلفة التنفيذ الإجمالية المعتمدة هي:

**20,000 دولار**

وهذا الرقم يشمل كامل رحلة التنفيذ:

1. بناء النظام الأساسي من الصفر.
2. بناء الباك إند.
3. بناء لوحة تحكم التاجر.
4. بناء العمليات التجارية.
5. تنفيذ Backend SaaS.
6. بناء Platform Admin.
7. الاختبارات والإغلاق النهائي.
8. التشغيل الأولي.
9. DevOps داخلي بدون تكلفة خارجية.

---

## 2. تكلفة التطوير المعتمدة

| البند | التكلفة |
|---|---:|
| بناء الباك إند الأساسي من الصفر | 4,000 دولار |
| بناء قاعدة البيانات والموديلات والعلاقات والهجرات | 1,500 دولار |
| بناء لوحة تحكم التاجر الأساسية | 3,500 دولار |
| بناء العمليات التجارية: مبيعات، مخزون، مشتريات، محاسبة، تقارير | 3,000 دولار |
| تنفيذ Backend SaaS: Tenant, Isolation, Plans, Usage, Billing, Platform APIs | 3,500 دولار |
| تعديل لوحة التاجر لتعمل كـ Tenant Dashboard | 1,500 دولار |
| بناء Platform Admin Frontend | 2,000 دولار |
| اختبارات، إصلاحات، إغلاق، توثيق، وتسليم | 1,000 دولار |

## إجمالي التطوير

**20,000 دولار**

---

## 3. عدد الوحدات الرئيسية للنظام

العدد المعتمد:

**33 وحدة تقنية رئيسية**

| رقم | الوحدة |
|---:|---|
| 1 | Auth |
| 2 | Users |
| 3 | Roles |
| 4 | Permissions |
| 5 | Tenants |
| 6 | Tenant Onboarding |
| 7 | Companies |
| 8 | Branches |
| 9 | Warehouses |
| 10 | Categories |
| 11 | Products |
| 12 | Product Variants |
| 13 | Inventory |
| 14 | Customers |
| 15 | Suppliers |
| 16 | Purchasing |
| 17 | Sales |
| 18 | Returns |
| 19 | Accounting |
| 20 | Payments |
| 21 | Currency |
| 22 | Reporting |
| 23 | Audit |
| 24 | Storage / Files |
| 25 | Backup |
| 26 | Sync / Offline |
| 27 | Notifications |
| 28 | Settings |
| 29 | Plans |
| 30 | Entitlements |
| 31 | Subscriptions |
| 32 | Usage / Quotas |
| 33 | Platform Admin |

---

## 4. عدد صفحات لوحة تحكم التاجر

الموجودة بالمشروع :

**47 صفحة**

وعدد المسارات:

**52 Route**

| القسم | عدد الصفحات |
|---|---:|
| Landing / Login / Signup / NotFound | 4 |
| Dashboard | 1 |
| POS | 1 |
| Products | 2 |
| Inventory | 2 |
| Customers | 2 |
| Suppliers | 2 |
| Branches | 2 |
| Warehouses | 2 |
| Sales | 3 |
| Purchasing | 3 |
| Returns | 3 |
| Accounting | 3 |
| Reports | 4 |
| Admin داخل التاجر | 4 |
| Settings | 5 |
| Users | 1 |
| صفحات SaaS : Tenant Status / Subscription / Forbidden | 3 |

---

## 5. عدد صفحات لوحة تحكم الإدارة Platform Admin

الموجودة بالمشروع :

**46 صفحة**

وعدد المسارات:

**31 Route**

| القسم | عدد الصفحات |
|---|---:|
| Login / 2FA | 2 |
| Dashboard | 1 |
| Tenants | 10 |
| Plans | 3 |
| Subscriptions | 5 |
| Billing | 4 |
| Usage | 3 |
| Platform Users / RBAC | 4 |
| Audit Logs | 1 |
| Support / Impersonation | 3 |
| Health / Metrics / Incidents | 3 |
| Announcements | 2 |
| Settings | 3 |
| Forbidden / NotFound | 2 |

---

## 6. عدد العمليات الموجودة في النظام

تعريف العملية في هذه الدراسة:

**Backend HTTP Operation**

أي عملية API من نوع:

- GET
- POST
- PATCH
- PUT
- DELETE

الموجود في الباك إند الحالي:

**399 عملية Backend HTTP**

---

## 7. مواصفات VPS المعتمدة

سعر كل VPS:

**10 دولار شهريًا**

مواصفات كل VPS:

```txt
CPU: 8 Cores
RAM: 12 GB
Storage: 100 GB NVMe
```

DevOps خارجي:

**0 دولار**

لأن DevOps يتم داخليًا.

---

## 8. تقسيم VPS حسب مراحل التشغيل

### المرحلة الأولى: أول شهر — تجربة وتشغيل أولي

عدد VPS:

**3 VPS**

التكلفة الشهرية:

**30 دولار**

| VPS | الاسم | الوظيفة |
|---:|---|---|
| VPS 1 | zaytun-edge-app-01 | Nginx + Backend API + Customer Web + Platform Admin |
| VPS 2 | zaytun-db-01 | PostgreSQL Primary + Backups محلية مؤقتة |
| VPS 3 | zaytun-services-01 | Redis + RabbitMQ + Workers + Cron Jobs + Monitoring بسيط |

---

### المرحلة الثانية: MVP منظم بعد التجربة

عدد VPS:

**4 VPS**

التكلفة الشهرية:

**40 دولار**

| VPS | الاسم | الوظيفة |
|---:|---|---|
| VPS 1 | zaytun-api-01 | Backend API + Nginx + Customer Web + Platform Admin |
| VPS 2 | zaytun-db-01 | PostgreSQL Primary |
| VPS 3 | zaytun-cache-queue-01 | Redis + RabbitMQ |
| VPS 4 | zaytun-worker-01 | Workers + Cron Jobs + Scheduled Tasks + Reports Export |

---

### المرحلة الثالثة: إنتاج أولي احترافي

عدد VPS:

**6 VPS**

التكلفة الشهرية:

**60 دولار**

| VPS | الاسم | الوظيفة |
|---:|---|---|
| VPS 1 | zaytun-gateway-01 | Nginx / Reverse Proxy / SSL / Rate Limit / Frontends |
| VPS 2 | zaytun-api-01 | Backend API |
| VPS 3 | zaytun-db-01 | PostgreSQL Primary |
| VPS 4 | zaytun-cache-queue-01 | Redis + RabbitMQ |
| VPS 5 | zaytun-worker-01 | Workers + Jobs + Reports + Notifications |
| VPS 6 | zaytun-backup-monitor-01 | Backups + Monitoring + Logs + احتياطي تشغيلي |

---

### المرحلة الرابعة: إنتاج مستقر

عدد VPS:

**8 VPS**

التكلفة الشهرية:

**80 دولار**

| VPS | الاسم | الوظيفة |
|---:|---|---|
| VPS 1 | zaytun-gateway-01 | Gateway / Nginx / SSL / Frontends |
| VPS 2 | zaytun-api-01 | Backend API Instance 1 |
| VPS 3 | zaytun-api-02 | Backend API Instance 2 |
| VPS 4 | zaytun-db-01 | PostgreSQL Primary |
| VPS 5 | zaytun-db-replica-01 | PostgreSQL Replica / Read Replica / Failover Manual |
| VPS 6 | zaytun-cache-queue-01 | Redis + RabbitMQ Primary |
| VPS 7 | zaytun-worker-01 | Workers Instance 1 |
| VPS 8 | zaytun-backup-monitor-01 | Backups + Monitoring + Logs + Snapshots |

---

### المرحلة الخامسة: إنتاج أقوى

عدد VPS:

**10 VPS**

التكلفة الشهرية:

**100 دولار**

| VPS | الاسم | الوظيفة |
|---:|---|---|
| VPS 1 | zaytun-gateway-01 | Gateway / Nginx / SSL / Routing |
| VPS 2 | zaytun-frontend-01 | Customer Web + Platform Admin Static Hosting |
| VPS 3 | zaytun-api-01 | Backend API Instance 1 |
| VPS 4 | zaytun-api-02 | Backend API Instance 2 |
| VPS 5 | zaytun-db-01 | PostgreSQL Primary |
| VPS 6 | zaytun-db-replica-01 | PostgreSQL Replica |
| VPS 7 | zaytun-redis-01 | Redis |
| VPS 8 | zaytun-rabbitmq-01 | RabbitMQ |
| VPS 9 | zaytun-worker-01 | Workers Instance 1 |
| VPS 10 | zaytun-backup-monitor-01 | Backups + Monitoring + Logs |

---

### المرحلة السادسة: إنتاج متقدم

عدد VPS:

**12 VPS**

التكلفة الشهرية:

**120 دولار**

| VPS | الاسم | الوظيفة |
|---:|---|---|
| VPS 1 | zaytun-gateway-01 | Gateway / Nginx / SSL / Load Balancing |
| VPS 2 | zaytun-frontend-01 | Customer Web + Platform Admin |
| VPS 3 | zaytun-api-01 | Backend API 1 |
| VPS 4 | zaytun-api-02 | Backend API 2 |
| VPS 5 | zaytun-api-03 | Backend API 3 |
| VPS 6 | zaytun-db-01 | PostgreSQL Primary |
| VPS 7 | zaytun-db-replica-01 | PostgreSQL Replica |
| VPS 8 | zaytun-redis-01 | Redis |
| VPS 9 | zaytun-rabbitmq-01 | RabbitMQ |
| VPS 10 | zaytun-worker-01 | Workers 1 |
| VPS 11 | zaytun-worker-02 | Workers 2 |
| VPS 12 | zaytun-backup-monitor-01 | Backups + Monitoring + Logs |

---

## 9. خطة VPS المعتمدة للسنة الأولى

| الفترة | عدد VPS | تكلفة VPS الشهرية | المدة | إجمالي VPS |
|---|---:|---:|---:|---:|
| الشهر 1 | 3 | 30 دولار | شهر واحد | 30 دولار |
| الشهر 2 - 4 | 4 | 40 دولار | 3 أشهر | 120 دولار |
| الشهر 5 - 9 | 6 | 60 دولار | 5 أشهر | 300 دولار |
| الشهر 10 - 12 | 8 | 80 دولار | 3 أشهر | 240 دولار |

## إجمالي VPS في السنة الأولى

**690 دولار**

---

## 10. مصاريف التشغيل الخارجية الإضافية

### 10.1 الدومين

القيمة المعتمدة:

**20 دولار سنويًا**

---

### 10.2 البريد الإلكتروني

القيمة المعتمدة:

**10 دولار شهريًا**

إجمالي السنة:

```txt
10 × 12 = 120 دولار
```

---

### 10.3 Google Play Console

يتم احتسابه فقط إذا كان يوجد تطبيق Android سيتم رفعه على Google Play.

القيمة المعتمدة:

**25 دولار مرة واحدة**

---

### 10.4 Apple Developer Program

يتم احتسابه فقط إذا كان يوجد تطبيق iOS سيتم رفعه على App Store.

القيمة المعتمدة في الدراسة:

**100 دولار سنويًا**

ملاحظة: السعر الرسمي هو 99 دولار سنويًا، وتم اعتماد 100 دولار كرقم مالي مبسط.

---

### 10.5 Coolify

يوجد خياران:

#### الخيار الأول: Coolify Self-hosted

التكلفة:

**0 دولار**

لأن النسخة self-hosted مجانية.

#### الخيار الثاني: Coolify Cloud

هذا هو الخيار المعتمد في حساب هذه الدراسة لأن المطلوب إضافة رسوم Coolify.

تسعير Coolify Cloud:

```txt
5 دولار شهريًا Base Price ويشمل أول 2 servers
+ 3 دولار شهريًا لكل server إضافي
```

#### حساب Coolify Cloud حسب مراحل VPS

| الفترة | عدد VPS | معادلة Coolify | التكلفة الشهرية | المدة | الإجمالي |
|---|---:|---|---:|---:|---:|
| الشهر 1 | 3 | 5 + 3 | 8 دولار | 1 | 8 دولار |
| الشهر 2 - 4 | 4 | 5 + 6 | 11 دولار | 3 | 33 دولار |
| الشهر 5 - 9 | 6 | 5 + 12 | 17 دولار | 5 | 85 دولار |
| الشهر 10 - 12 | 8 | 5 + 18 | 23 دولار | 3 | 69 دولار |

## إجمالي Coolify Cloud في السنة الأولى

**195 دولار**

---

### 10.6 Firebase

الاستخدام المعتمد:

- Firebase Cloud Messaging للإشعارات.
- Web Push Notifications.
- إشعارات Android / iOS / Web.

القيمة المعتمدة:

**0 دولار**

لأن Firebase Cloud Messaging ضمن خدمات Firebase التي لا تُحتسب عليها تكلفة مباشرة.

ملاحظة فنية مهمة:

الـ WebSocket الحقيقي للنظام لا يجب أن يكون عبر Firebase، بل عبر:

- Backend API
- Socket.io أو WebSocket server
- Redis Pub/Sub عند الحاجة
- RabbitMQ للرسائل غير اللحظية والJobs

لذلك Firebase في هذه الدراسة يُستخدم للإشعارات Push Notifications، وليس كبديل كامل للـ WebSocket.

---

## 11. إجمالي مصاريف التشغيل الخارجية للسنة الأولى

### سيناريو 1: بدون تطبيق Mobile

| البند | التكلفة السنوية |
|---|---:|
| VPS | 690 دولار |
| Domain | 20 دولار |
| Email | 120 دولار |
| Coolify Cloud | 195 دولار |
| Firebase FCM | 0 دولار |
| Google Play | 0 دولار |
| Apple Developer | 0 دولار |

## إجمالي التشغيل بدون تطبيق

**1,025 دولار**

---

### سيناريو 2: مع تطبيق Android فقط

| البند | التكلفة السنوية |
|---|---:|
| VPS | 690 دولار |
| Domain | 20 دولار |
| Email | 120 دولار |
| Coolify Cloud | 195 دولار |
| Firebase FCM | 0 دولار |
| Google Play Console | 25 دولار |
| Apple Developer | 0 دولار |

## إجمالي التشغيل مع Android فقط

**1,050 دولار**

---

### سيناريو 3: مع تطبيق Android و iOS

| البند | التكلفة السنوية |
|---|---:|
| VPS | 690 دولار |
| Domain | 20 دولار |
| Email | 120 دولار |
| Coolify Cloud | 195 دولار |
| Firebase FCM | 0 دولار |
| Google Play Console | 25 دولار |
| Apple Developer Program | 100 دولار |

## إجمالي التشغيل مع Android و iOS

**1,150 دولار**

---

## 12. إجمالي السنة الأولى مع تكلفة التطوير

### سيناريو 1: Web SaaS فقط بدون تطبيق Mobile

| البند | التكلفة |
|---|---:|
| التطوير الكامل | 20,000 دولار |
| التشغيل السنوي بدون تطبيق | 1,025 دولار |

## الإجمالي

**21,025 دولار**

---

### سيناريو 2: مع تطبيق Android فقط

| البند | التكلفة |
|---|---:|
| التطوير الكامل | 20,000 دولار |
| التشغيل السنوي مع Android فقط | 1,050 دولار |

## الإجمالي

**21,050 دولار**

---

### سيناريو 3: مع تطبيق Android و iOS

| البند | التكلفة |
|---|---:|
| التطوير الكامل | 20,000 دولار |
| التشغيل السنوي مع Android و iOS | 1,150 دولار |

## الإجمالي

**21,150 دولار**

---

## 13. توزيع مصاريف السنة الأولى حسب الأشهر — مع Android و iOS

هذا هو السيناريو الأعلى ضمن الدراسة.

| الفترة | VPS | Coolify | Email | Domain | Stores | Firebase | الإجمالي |
|---|---:|---:|---:|---:|---:|---:|---:|
| الشهر 1 | 30 | 8 | 10 | 20 | 125 | 0 | 193 دولار |
| الشهر 2 - 4 | 120 | 33 | 30 | 0 | 0 | 0 | 183 دولار |
| الشهر 5 - 9 | 300 | 85 | 50 | 0 | 0 | 0 | 435 دولار |
| الشهر 10 - 12 | 240 | 69 | 30 | 0 | 0 | 0 | 339 دولار |

## إجمالي التشغيل في السنة الأولى مع Android و iOS

**1,150 دولار**

---

## 14. الملخص النهائي المعتمد

| البند | الرقم النهائي |
|---|---:|
| تكلفة التطوير الكاملة | 20,000 دولار |
| عدد الوحدات التقنية الرئيسية | 33 وحدة |
| عدد صفحات لوحة التاجر | 47 صفحة |
| عدد Routes لوحة التاجر | 52 Route |
| عدد صفحات Platform Admin | 46 صفحة |
| عدد Routes Platform Admin | 31 Route |
| عدد عمليات الباك إند النهائية | 399 عملية |
| إجمالي VPS في السنة الأولى | 690 دولار |
| Domain | 20 دولار سنويًا |
| Email | 120 دولار سنويًا |
| Coolify Cloud | 195 دولار سنويًا |
| Firebase FCM | 0 دولار |
| Google Play | 25 دولار مرة واحدة |
| Apple Developer | 100 دولار سنويًا |
| إجمالي التشغيل بدون تطبيق | 1,025 دولار |
| إجمالي التشغيل مع Android فقط | 1,050 دولار |
| إجمالي التشغيل مع Android و iOS | 1,150 دولار |
| إجمالي السنة الأولى بدون تطبيق | 21,025 دولار |
| إجمالي السنة الأولى مع Android فقط | 21,050 دولار |
| إجمالي السنة الأولى مع Android و iOS | 21,150 دولار |

---

## 15. الخلاصة النهائية

القيمة النهائية المعتمدة لمشروع زيتون سوفت SaaS بعد الإغلاق الكامل هي:

## بدون تطبيق Mobile

**21,025 دولار للسنة الأولى**

## مع تطبيق Android فقط

**21,050 دولار للسنة الأولى**

## مع تطبيق Android و iOS

**21,150 دولار للسنة الأولى**

وهذا يشمل:

- 20,000 دولار تكلفة تطوير كاملة.
- VPS بتقسيم احترافي متدرج حتى 8 VPS في نهاية السنة الأولى.
- دومين.
- بريد إلكتروني.
- Coolify Cloud.
- Firebase FCM للإشعارات.
- رسوم نشر Android و iOS إذا تم اعتماد التطبيق.
- DevOps داخلي بدون تكلفة خارجية.

---

## 16. مصادر الأسعار الرسمية المستخدمة

- Google Play Console: رسوم تسجيل مطور 25 دولار مرة واحدة.
- Apple Developer Program: 99 دولار سنويًا، وتم اعتماد 100 دولار في الدراسة.
- Coolify: Self-hosted مجاني، وCloud يبدأ بـ 5 دولار شهريًا لأول خادمين + 3 دولار لكل خادم إضافي.
- Firebase: Cloud Messaging ضمن المنتجات المتاحة بدون تكلفة مباشرة.

