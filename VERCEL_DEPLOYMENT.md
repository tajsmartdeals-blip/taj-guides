# 🚀 دليل النشر على Vercel - خطوة بخطوة

## المتطلبات الأساسية

قبل البدء، تأكد من توفر:
- حساب GitHub (مجاني)
- حساب Vercel (مجاني)
- النطاق الخاص بك (اختياري)

---

## الخطوة 1: إعداد مستودع GitHub

### 1.1 إنشاء حساب GitHub

```
1. اذهب إلى https://github.com
2. انقر على "Sign up"
3. أدخل البريد الإلكتروني والكلمة المرورية
4. أكمل التحقق
5. اختر الخطة المجانية
```

### 1.2 إنشاء مستودع جديد

```
1. اذهب إلى https://github.com/new
2. أدخل اسم المستودع: "taj-guides"
3. أضف وصف: "Taj Smart Deals - Comprehensive E-commerce Guide"
4. اختر "Public"
5. انقر على "Create repository"
```

### 1.3 رفع الملفات إلى GitHub

```bash
# في مجلد المشروع
cd /home/ubuntu/taj-guides-website

# تهيئة Git
git init
git add .
git commit -m "Initial commit: Taj Guides Website"

# إضافة المستودع البعيد
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/taj-guides.git

# رفع الملفات
git push -u origin main
```

**ملاحظة:** استبدل `YOUR_USERNAME` باسم مستخدمك على GitHub

---

## الخطوة 2: إعداد حساب Vercel

### 2.1 إنشاء حساب Vercel

```
1. اذهب إلى https://vercel.com
2. انقر على "Sign Up"
3. اختر "Continue with GitHub"
4. وافق على الأذونات
5. أكمل الإعدادات
```

### 2.2 ربط GitHub مع Vercel

```
1. اذهب إلى https://vercel.com/account/integrations
2. ابحث عن "GitHub"
3. انقر على "Install"
4. اختر الحساب الخاص بك
5. اختر المستودعات التي تريد ربطها
```

---

## الخطوة 3: نشر الموقع على Vercel

### 3.1 استيراد المشروع

```
1. اذهب إلى https://vercel.com/dashboard
2. انقر على "Add New"
3. اختر "Project"
4. ابحث عن "taj-guides"
5. انقر على "Import"
```

### 3.2 إعدادات المشروع

```
الإعدادات الافتراضية كافية:
- Framework: Other (Static)
- Root Directory: ./
- Build Command: (اترك فارغاً)
- Output Directory: (اترك فارغاً)
- Environment Variables: (لا توجد)
```

### 3.3 النشر

```
1. انقر على "Deploy"
2. انتظر حتى ينتهي النشر (عادة 1-2 دقيقة)
3. ستحصل على URL مؤقت مثل: taj-guides.vercel.app
```

---

## الخطوة 4: ربط النطاق المخصص

### 4.1 شراء النطاق

اختر أحد الخيارات:

#### الخيار 1: شراء من Namecheap
```
1. اذهب إلى https://www.namecheap.com
2. ابحث عن "taj-guides.com"
3. أضفه إلى السلة
4. أكمل الشراء
5. احفظ معلومات الحساب
```

#### الخيار 2: شراء من GoDaddy
```
1. اذهب إلى https://www.godaddy.com
2. ابحث عن "taj-guides.com"
3. أضفه إلى السلة
4. أكمل الشراء
5. احفظ معلومات الحساب
```

#### الخيار 3: شراء من Google Domains
```
1. اذهب إلى https://domains.google.com
2. ابحث عن "taj-guides.com"
3. أضفه إلى السلة
4. أكمل الشراء
5. احفظ معلومات الحساب
```

### 4.2 إضافة النطاق إلى Vercel

```
1. اذهب إلى Vercel Dashboard
2. اختر المشروع "taj-guides"
3. اذهب إلى "Settings"
4. اختر "Domains"
5. انقر على "Add Domain"
6. أدخل النطاق: "taj-guides.com"
7. انقر على "Add"
```

### 4.3 إعداد DNS Records

Vercel سيعطيك DNS records لإضافتها:

```
عادة يكون شيء مثل:
Type: A
Name: @
Value: 76.76.19.165

Type: CNAME
Name: www
Value: cname.vercel-dns.com
```

**اذهب إلى لوحة تحكم مسجل النطاق:**

#### في Namecheap:
```
1. اذهب إلى "Manage Domain"
2. اختر "Advanced DNS"
3. أضف السجلات من Vercel
4. انتظر التحديث (24-48 ساعة)
```

#### في GoDaddy:
```
1. اذهب إلى "Manage DNS"
2. أضف السجلات من Vercel
3. انتظر التحديث (24-48 ساعة)
```

#### في Google Domains:
```
1. اذهب إلى "DNS"
2. اختر "Custom name servers"
3. أضف name servers من Vercel
4. انتظر التحديث (24-48 ساعة)
```

---

## الخطوة 5: تفعيل HTTPS

### 5.1 شهادة SSL تلقائية

```
Vercel يفعّل HTTPS تلقائياً:
1. انتظر 24-48 ساعة بعد إضافة النطاق
2. Vercel سيصدر شهادة SSL مجانية
3. الموقع سيكون آمناً تلقائياً
```

### 5.2 التحقق من HTTPS

```bash
# اختبر الاتصال الآمن
curl -I https://taj-guides.com

# يجب أن ترى:
# HTTP/2 200
# Strict-Transport-Security: max-age=31536000
```

---

## الخطوة 6: إعادة التوجيه من HTTP إلى HTTPS

### 6.1 إضافة إعادة التوجيه

Vercel يفعّل هذا تلقائياً، لكن يمكنك التحقق:

```json
// في vercel.json
{
  "redirects": [
    {
      "source": "/:path*",
      "destination": "https://taj-guides.com/:path*",
      "permanent": true
    }
  ]
}
```

---

## الخطوة 7: إعدادات متقدمة

### 7.1 متغيرات البيئة

```
1. اذهب إلى Settings > Environment Variables
2. أضف المتغيرات المطلوبة
3. مثال:
   - SITE_NAME: Taj Smart Deals
   - ANALYTICS_ID: G-XXXXXXXXXX
```

### 7.2 رؤوس الأمان

```json
// في vercel.json
{
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        {
          "key": "X-Content-Type-Options",
          "value": "nosniff"
        },
        {
          "key": "X-Frame-Options",
          "value": "SAMEORIGIN"
        },
        {
          "key": "X-XSS-Protection",
          "value": "1; mode=block"
        }
      ]
    }
  ]
}
```

---

## الخطوة 8: المراقبة والصيانة

### 8.1 مراقبة الأداء

```
1. اذهب إلى Vercel Dashboard
2. اختر المشروع
3. اذهب إلى "Analytics"
4. راقب:
   - وقت الاستجابة
   - عدد الطلبات
   - معدل الأخطاء
```

### 8.2 تحديث الموقع

```bash
# لتحديث الموقع، ما عليك سوى:
git add .
git commit -m "Update: [وصف التغييرات]"
git push origin main

# Vercel سيعيد النشر تلقائياً
```

### 8.3 إعادة النشر اليدوية

```
1. اذهب إلى Vercel Dashboard
2. اختر المشروع
3. انقر على "Deployments"
4. اختر الإصدار الذي تريده
5. انقر على "Redeploy"
```

---

## استكشاف الأخطاء

### المشكلة: النطاق لا يعمل

**الحل:**
1. تحقق من DNS records
2. انتظر 24-48 ساعة
3. امسح ذاكرة التخزين المؤقتة
4. جرب متصفح مختلف

### المشكلة: HTTPS لا يعمل

**الحل:**
1. تأكد من أن النطاق مضاف بشكل صحيح
2. انتظر 24 ساعة لإصدار الشهادة
3. تحقق من DNS records
4. اتصل بدعم Vercel

### المشكلة: الموقع بطيء

**الحل:**
1. ضغط الصور
2. قلل حجم الملفات
3. استخدم CDN
4. قلل عدد الطلبات

### المشكلة: الملفات لا تحدّث

**الحل:**
1. تحقق من أن الملفات مرفوعة على GitHub
2. امسح ذاكرة التخزين المؤقتة
3. أعد النشر يدوياً
4. تحقق من السجلات (Logs)

---

## الخطوات التالية

### 1. إضافة Google Analytics

```
1. اتبع دليل ANALYTICS_SETUP.md
2. أضف كود التتبع إلى HTML
3. راقب الزيارات والسلوك
```

### 2. إعداد البريد الإلكتروني

```
1. اتبع دليل SOCIAL_MEDIA_GUIDE.md
2. أنشئ حسابات بريد احترافية
3. ابدأ التسويق
```

### 3. تحسين SEO

```
1. اتبع دليل SEO_MARKETING.md
2. أضف meta tags
3. أرسل sitemap إلى Google
```

---

## الموارد المفيدة

- [Vercel Documentation](https://vercel.com/docs)
- [Vercel Support](https://vercel.com/support)
- [DNS Records Guide](https://vercel.com/docs/concepts/projects/domains/dns)
- [SSL/TLS Certificate](https://vercel.com/docs/concepts/projects/domains/ssl-tls)

---

## ملخص سريع

| الخطوة | الوقت | الملاحظات |
|--------|-------|---------|
| إعداد GitHub | 5 دقائق | مجاني |
| إعداد Vercel | 5 دقائق | مجاني |
| النشر الأولي | 5 دقائق | تلقائي |
| شراء النطاق | 10 دقائق | حوالي $10-15/سنة |
| إعداد DNS | 5 دقائق | يدوي |
| انتظار DNS | 24-48 ساعة | تلقائي |
| تفعيل HTTPS | 24 ساعة | تلقائي |

**الإجمالي:** حوالي ساعة واحدة (+ 24-48 ساعة انتظار)

---

**آخر تحديث:** 22 أبريل 2026  
**الإصدار:** 1.0.0
