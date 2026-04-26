# 📊 دليل إعداد Google Analytics

## خطوات إعداد Google Analytics 4

### الخطوة 1: إنشاء حساب Google Analytics

```
1. اذهب إلى https://analytics.google.com
2. انقر على "ابدأ الآن" (Start Measuring)
3. أدخل اسم الحساب: "Taj Smart Deals"
4. اختر إعدادات المشاركة (اختياري)
5. انقر على "التالي"
```

### الخطوة 2: إنشاء خاصية (Property)

```
1. أدخل اسم الخاصية: "taj-guides.com"
2. اختر المنطقة الزمنية: (UTC+3) Arabia Standard Time
3. اختر العملة: SAR (Saudi Riyal) أو USD
4. انقر على "التالي"
```

### الخطوة 3: إعداد الأعمال التجارية

```
1. اختر الفئة: "E-commerce / Shopping"
2. اختر الأهداف:
   - Track website traffic
   - Measure engagement
   - Track conversions
   - Understand user behavior
3. انقر على "إنشاء"
```

### الخطوة 4: إضافة كود التتبع

بعد الإنشاء، ستحصل على كود التتبع. أضفه إلى موقعك:

```html
<!-- Google Analytics 4 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

**ملاحظة:** استبدل `G-XXXXXXXXXX` برقم معرّف الخاصية الخاص بك

---

## إضافة كود التتبع إلى الموقع

### في ملف HTML:

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Google Analytics 4 -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-YOUR_PROPERTY_ID"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', 'G-YOUR_PROPERTY_ID');
    </script>
    
    <!-- باقي الـ HEAD -->
</head>
<body>
    <!-- محتوى الصفحة -->
</body>
</html>
```

### في ملف JavaScript منفصل:

```javascript
// analytics.js
window.dataLayer = window.dataLayer || [];
function gtag(){dataLayer.push(arguments);}
gtag('js', new Date());
gtag('config', 'G-YOUR_PROPERTY_ID');

// تتبع الأحداث المخصصة
gtag('event', 'page_view', {
  'page_title': document.title,
  'page_path': window.location.pathname
});
```

---

## تتبع الأحداث المخصصة

### 1. تتبع النقرات على الأزرار

```javascript
// عند النقر على زر "ابدأ الآن"
document.getElementById('start-button').addEventListener('click', function() {
  gtag('event', 'button_click', {
    'button_name': 'Start Now',
    'button_location': 'hero_section'
  });
});
```

### 2. تتبع الروابط الخارجية

```javascript
// تتبع النقر على رابط خارجي
document.querySelectorAll('a[target="_blank"]').forEach(link => {
  link.addEventListener('click', function() {
    gtag('event', 'external_link_click', {
      'link_url': this.href,
      'link_text': this.textContent
    });
  });
});
```

### 3. تتبع الوقت على الصفحة

```javascript
// تتبع الوقت الذي يقضيه المستخدم
let timeOnPage = 0;
setInterval(() => {
  timeOnPage++;
  if (timeOnPage % 60 === 0) { // كل دقيقة
    gtag('event', 'time_on_page', {
      'minutes': timeOnPage / 60
    });
  }
}, 1000);
```

### 4. تتبع التمرير

```javascript
// تتبع عمق التمرير
let maxScroll = 0;
window.addEventListener('scroll', function() {
  const scrollPercent = (window.scrollY / (document.documentElement.scrollHeight - window.innerHeight)) * 100;
  if (scrollPercent > maxScroll) {
    maxScroll = scrollPercent;
    if (maxScroll % 25 === 0) { // كل 25%
      gtag('event', 'scroll_depth', {
        'percent': Math.round(maxScroll)
      });
    }
  }
});
```

### 5. تتبع البحث

```javascript
// تتبع عمليات البحث
function trackSearch(query) {
  gtag('event', 'search', {
    'search_term': query
  });
}
```

---

## إعداد الأهداف (Goals)

### الخطوة 1: الذهاب إلى الأهداف

```
1. اذهب إلى Google Analytics
2. اختر الخاصية الخاصة بك
3. اذهب إلى الإدارة (Admin)
4. اختر "الأهداف" (Goals)
5. انقر على "إنشاء هدف"
```

### الخطوة 2: إنشاء أهداف مخصصة

#### الهدف 1: زيارة صفحة الأدلة
```
- الاسم: Visit Guides Page
- نوع الهدف: Destination
- الوجهة: /guides
```

#### الهدف 2: تحميل الدليل
```
- الاسم: Download Guide
- نوع الهدف: Event
- الحدث: guide_download
```

#### الهدف 3: الاشتراك في النشرة الإخبارية
```
- الاسم: Newsletter Signup
- نوع الهدف: Event
- الحدث: newsletter_signup
```

#### الهدف 4: الاتصال بنا
```
- الاسم: Contact Form Submit
- نوع الهدف: Event
- الحدث: contact_submit
```

---

## إعداد التحويلات (Conversions)

### تحديد التحويلات المهمة:

```javascript
// تحويل 1: زيارة صفحة الأدلة
gtag('event', 'page_view', {
  'page_title': 'Guides',
  'page_location': window.location.href
});

// تحويل 2: تحميل دليل
function trackGuideDownload(guideName) {
  gtag('event', 'guide_download', {
    'guide_name': guideName
  });
}

// تحويل 3: الاشتراك في النشرة
function trackNewsletterSignup(email) {
  gtag('event', 'newsletter_signup', {
    'email_domain': email.split('@')[1]
  });
}

// تحويل 4: إرسال نموذج الاتصال
function trackContactSubmit(name, email) {
  gtag('event', 'contact_submit', {
    'contact_name': name,
    'email_domain': email.split('@')[1]
  });
}
```

---

## التقارير المهمة

### 1. تقرير الجمهور (Audience)

يوضح معلومات عن زوارك:
- العمر والجنس
- الاهتمامات
- المواقع الجغرافية
- الأجهزة المستخدمة

### 2. تقرير الاستحواذ (Acquisition)

يوضح كيف وصل الزوار إليك:
- محركات البحث
- وسائل التواصل الاجتماعي
- الروابط المباشرة
- الإحالات

### 3. تقرير السلوك (Behavior)

يوضح ما يفعله الزوار:
- الصفحات الأكثر زيارة
- معدل الارتداد
- الوقت على الصفحة
- التحويلات

### 4. تقرير التحويلات (Conversions)

يوضح الأهداف المحققة:
- عدد التحويلات
- معدل التحويل
- قيمة التحويل
- مسار التحويل

---

## لوحة المعلومات المخصصة

### إنشاء لوحة معلومات:

```
1. اذهب إلى Google Analytics
2. اختر "لوحات المعلومات" (Dashboards)
3. انقر على "إنشاء لوحة معلومات"
4. أضف الأدوات التالية:
   - عدد الزيارات
   - عدد المستخدمين
   - معدل الارتداد
   - متوسط مدة الجلسة
   - أعلى الصفحات
   - مصادر الحركة
   - التحويلات
```

---

## التحليلات المتقدمة

### 1. تحليل المسار (Path Analysis)

```javascript
// تتبع مسار المستخدم
gtag('event', 'user_path', {
  'from_page': document.referrer,
  'to_page': window.location.pathname
});
```

### 2. تحليل الجلسات (Session Analysis)

```javascript
// تتبع معلومات الجلسة
gtag('event', 'session_start', {
  'session_id': generateSessionId(),
  'timestamp': new Date().toISOString()
});
```

### 3. تحليل المستخدمين (User Analysis)

```javascript
// تتبع معرف المستخدم (إذا كان متاحاً)
gtag('config', 'G-YOUR_PROPERTY_ID', {
  'user_id': userId
});
```

---

## الاختبار والتحقق

### 1. استخدام Google Analytics Debugger

```
1. ثبّت إضافة "Google Analytics Debugger" من Chrome Web Store
2. افتح موقعك
3. افتح Developer Tools (F12)
4. اذهب إلى تبويب "Google Analytics"
5. تحقق من الأحداث المُرسلة
```

### 2. اختبار الأحداث المخصصة

```javascript
// اختبر حدث مخصص
gtag('event', 'test_event', {
  'test_parameter': 'test_value'
});

// تحقق من الحدث في Google Analytics Debugger
```

---

## الإبلاغ والتنبيهات

### إعداد التنبيهات:

```
1. اذهب إلى Google Analytics
2. اختر "الإدارة" (Admin)
3. اختر "التنبيهات المخصصة" (Custom Alerts)
4. انقر على "إنشاء تنبيه"
5. اختر الشروط:
   - معدل الارتداد > 50%
   - الزيارات < 100 يومياً
   - معدل التحويل < 1%
```

### إرسال التقارير:

```
1. اذهب إلى Google Analytics
2. اختر "الإدارة" (Admin)
3. اختر "التقارير المجدولة" (Scheduled Reports)
4. انقر على "إنشاء تقرير"
5. اختر التكرار: يومي / أسبوعي / شهري
6. أدخل البريد الإلكتروني
```

---

## أفضل الممارسات

### 1. الخصوصية والامتثال
- احترم خصوصية المستخدمين
- أضف سياسة الخصوصية
- اطلب الموافقة على تتبع البيانات
- امتثل لـ GDPR و CCPA

### 2. تنظيف البيانات
- استثن حركة المسؤولين
- استثن حركة الاختبار
- استثن الروبوتات والعناكب

### 3. التسمية والتنظيم
- استخدم أسماء واضحة للأحداث
- نظّم الأحداث في فئات
- استخدم معايير تسمية موحدة

### 4. الاختبار والتحقق
- اختبر الأحداث قبل النشر
- تحقق من البيانات بانتظام
- راجع التقارير أسبوعياً

---

## استكشاف الأخطاء

### المشكلة: لا تظهر البيانات في Google Analytics

**الحل:**
1. تحقق من كود التتبع (يجب أن يكون صحيحاً)
2. تحقق من أن الموقع يحمّل الكود
3. انتظر 24 ساعة لظهور البيانات الأولى
4. استخدم Google Analytics Debugger للتحقق

### المشكلة: الأحداث المخصصة لا تُسجّل

**الحل:**
1. تحقق من اسم الحدث (يجب أن يكون صحيحاً)
2. تحقق من أن الحدث يُطلق بشكل صحيح
3. تحقق من وحدة التحكم (Console) بحثاً عن الأخطاء
4. استخدم Google Analytics Debugger

### المشكلة: معدل الارتداد مرتفع جداً

**الحل:**
1. حسّن سرعة تحميل الموقع
2. حسّن تجربة المستخدم
3. أضف محتوى جذاب
4. حسّن الكلمات المفتاحية

---

## الموارد الإضافية

- [Google Analytics Documentation](https://support.google.com/analytics)
- [Google Analytics Academy](https://analytics.google.com/analytics/academy/)
- [Google Analytics Community](https://support.google.com/analytics/community)

---

**آخر تحديث:** 22 أبريل 2026  
**الإصدار:** 1.0.0
