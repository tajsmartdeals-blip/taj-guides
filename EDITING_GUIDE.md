# ✏️ دليل التعديل والتخصيص - سهل وبسيط

## مقدمة

هذا الدليل يساعدك على تعديل وتخصيص الموقع بدون الحاجة إلى معرفة برمجية عميقة.

---

## الملفات الأساسية

### 1. ملف HTML الرئيسي (`index.html`)

**الموقع:** `/home/ubuntu/taj-guides-website/index.html`

**ما يمكنك تعديله:**
- العناوين والنصوص
- الروابط
- الصور
- الألوان

### 2. ملف CSS (`styles.css`)

**الموقع:** `/home/ubuntu/taj-guides-website/styles.css`

**ما يمكنك تعديله:**
- الألوان
- الخطوط
- الحجم والمسافات
- التأثيرات والرسوم المتحركة

### 3. ملف JavaScript (`script.js`)

**الموقع:** `/home/ubuntu/taj-guides-website/script.js`

**ما يمكنك تعديله:**
- الوظائف التفاعلية
- الأحداث والنقرات
- التحقق من النماذج

---

## تعديل النصوص والعناوين

### تعديل العنوان الرئيسي

**في `index.html`، ابحث عن:**
```html
<h1>تاج - منصة المتاجر الإلكترونية الذكية</h1>
```

**غيّره إلى:**
```html
<h1>اسمك الجديد - وصفك الجديد</h1>
```

### تعديل الوصف

**ابحث عن:**
```html
<p>أدلة شاملة وأدوات متقدمة لبناء متجر إلكتروني احترافي...</p>
```

**غيّره إلى:**
```html
<p>وصفك الجديد هنا...</p>
```

### تعديل الميزات

**ابحث عن:**
```html
<div class="feature-card">
    <div class="feature-icon">🔔</div>
    <h3>تنبيهات الأسعار</h3>
    <p>نظام ذكي لتتبع انخفاض الأسعار...</p>
</div>
```

**غيّره إلى:**
```html
<div class="feature-card">
    <div class="feature-icon">🎯</div>
    <h3>اسم الميزة الجديدة</h3>
    <p>وصف الميزة الجديدة هنا...</p>
</div>
```

---

## تعديل الألوان

### الألوان الأساسية

**في `styles.css`، ابحث عن:**
```css
:root {
    --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    --secondary-gradient: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
    --dark-bg: #0f0f1e;
    --accent-cyan: #00d4ff;
    --accent-pink: #ff006e;
}
```

### تغيير اللون الأساسي

**الخطوة 1:** ابحث عن الكود أعلاه

**الخطوة 2:** غيّر الألوان:
```css
:root {
    --primary-gradient: linear-gradient(135deg, #YOUR_COLOR1 0%, #YOUR_COLOR2 100%);
    --secondary-gradient: linear-gradient(135deg, #YOUR_COLOR3 0%, #YOUR_COLOR4 100%);
    --dark-bg: #YOUR_DARK_COLOR;
    --accent-cyan: #YOUR_ACCENT_COLOR;
    --accent-pink: #YOUR_ACCENT_COLOR2;
}
```

### أكواد الألوان الشهيرة

| اللون | الكود |
|--------|--------|
| أحمر | #FF0000 |
| أزرق | #0000FF |
| أخضر | #00FF00 |
| أصفر | #FFFF00 |
| برتقالي | #FFA500 |
| بنفسجي | #800080 |
| وردي | #FFC0CB |
| ذهبي | #FFD700 |

---

## تعديل الخطوط

### تغيير عائلة الخط

**ابحث عن:**
```css
body {
    font-family: 'Segoe UI', 'Cairo', Tahoma, Geneva, Verdana, sans-serif;
}
```

**غيّره إلى:**
```css
body {
    font-family: 'Your Font Name', Arial, sans-serif;
}
```

### خطوط شهيرة مجانية

- **Cairo** - خط عربي جميل
- **Segoe UI** - خط احترافي
- **Roboto** - خط حديث
- **Open Sans** - خط شهير
- **Lato** - خط ودود

---

## تعديل الصور

### إضافة صورة جديدة

**في `index.html`:**
```html
<img src="path/to/your/image.png" alt="وصف الصورة">
```

### استبدال الصور الموجودة

**ابحث عن:**
```html
<div class="graphic-item">📱</div>
```

**غيّره إلى:**
```html
<img src="your-image.png" alt="وصف">
```

### مواقع صور مجانية

- [Unsplash](https://unsplash.com) - صور عالية الجودة
- [Pexels](https://www.pexels.com) - صور مجانية
- [Pixabay](https://pixabay.com) - صور ورسوميات
- [Freepik](https://www.freepik.com) - رسوميات وصور

---

## تعديل الروابط

### تغيير رابط الزر

**ابحث عن:**
```html
<a href="#guides" class="btn btn-primary">ابدأ الآن</a>
```

**غيّره إلى:**
```html
<a href="your-link.html" class="btn btn-primary">اسم الزر الجديد</a>
```

### إضافة رابط خارجي

```html
<a href="https://your-website.com" target="_blank">اسم الرابط</a>
```

---

## تعديل الأقسام

### إضافة قسم جديد

```html
<section id="new-section" class="features">
    <div class="container">
        <h2>عنوان القسم الجديد</h2>
        <div class="features-grid">
            <!-- أضف الميزات هنا -->
        </div>
    </div>
</section>
```

### حذف قسم

ابحث عن `<section>` وحذف الكود بالكامل:
```html
<!-- احذف هذا الكود -->
<section id="section-name">
    ...
</section>
```

---

## تعديل النماذج

### إضافة نموذج اتصال

```html
<form id="contact-form">
    <input type="text" placeholder="اسمك" required>
    <input type="email" placeholder="بريدك الإلكتروني" required>
    <textarea placeholder="رسالتك"></textarea>
    <button type="submit">إرسال</button>
</form>
```

### إضافة حقل جديد

```html
<input type="text" name="field-name" placeholder="اسم الحقل" required>
```

---

## تعديل الرسوم المتحركة

### تغيير سرعة الرسم المتحرك

**ابحث عن:**
```css
@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

**غيّر المدة:**
```css
.feature-card {
    animation: slideIn 0.5s ease-out;  /* غيّر 0.5s إلى مدة أخرى */
}
```

### تعطيل الرسوم المتحركة

```css
* {
    animation: none !important;
    transition: none !important;
}
```

---

## تعديل التخطيط والمسافات

### تغيير عرض الصفحة

**ابحث عن:**
```css
.container {
    max-width: 1400px;
}
```

**غيّره إلى:**
```css
.container {
    max-width: 1200px;  /* أضيق */
    /* أو */
    max-width: 1600px;  /* أوسع */
}
```

### تغيير المسافات

**ابحث عن:**
```css
.feature-card {
    padding: 2.5rem;
}
```

**غيّره إلى:**
```css
.feature-card {
    padding: 1.5rem;  /* أصغر */
    /* أو */
    padding: 3.5rem;  /* أكبر */
}
```

---

## تعديل الاستجابة للأجهزة المحمولة

### تغيير حجم الخط على الهاتف

**ابحث عن:**
```css
@media (max-width: 768px) {
    .hero-content h1 {
        font-size: 2.2rem;
    }
}
```

**غيّره إلى:**
```css
@media (max-width: 768px) {
    .hero-content h1 {
        font-size: 1.8rem;  /* أصغر */
    }
}
```

---

## تعديل الأيقونات

### تغيير الأيقونة

**ابحث عن:**
```html
<div class="feature-icon">🔔</div>
```

**غيّره إلى:**
```html
<div class="feature-icon">⭐</div>
```

### أيقونات شهيرة

| الأيقونة | الرمز |
|----------|--------|
| نجمة | ⭐ |
| قلب | ❤️ |
| سهم | ➡️ |
| تحقق | ✅ |
| خطأ | ❌ |
| سؤال | ❓ |
| معلومات | ℹ️ |
| تحذير | ⚠️ |

---

## تعديل البيانات الوصفية (Meta Tags)

### تغيير العنوان والوصف

**في `index.html`، ابحث عن:**
```html
<title>تاج - منصة المتاجر الإلكترونية الذكية</title>
<meta name="description" content="أدلة شاملة وأدوات متقدمة...">
```

**غيّره إلى:**
```html
<title>عنوانك الجديد</title>
<meta name="description" content="وصفك الجديد...">
```

---

## استخدام أدوات التعديل

### أداة 1: Visual Studio Code

```
1. حمّل من https://code.visualstudio.com
2. افتح مجلد المشروع
3. عدّل الملفات
4. احفظ التغييرات (Ctrl+S)
```

### أداة 2: Sublime Text

```
1. حمّل من https://www.sublimetext.com
2. افتح المشروع
3. عدّل الملفات
4. احفظ التغييرات
```

### أداة 3: Notepad++

```
1. حمّل من https://notepad-plus-plus.org
2. افتح الملفات
3. عدّل النصوص
4. احفظ التغييرات
```

---

## اختبار التغييرات

### الاختبار المحلي

```bash
# في مجلد المشروع
python3 -m http.server 8000

# ثم افتح: http://localhost:8000
```

### الاختبار على الهاتف

```
1. تأكد من أن الموقع يحمّل بشكل صحيح
2. اختبره على أجهزة مختلفة
3. اختبر الروابط والأزرار
4. اختبر الاستجابة
```

---

## رفع التغييرات

### الخطوة 1: حفظ التغييرات

```bash
git add .
git commit -m "تحديث: وصف التغييرات"
```

### الخطوة 2: رفع إلى GitHub

```bash
git push origin main
```

### الخطوة 3: النشر التلقائي

```
Vercel سيعيد النشر تلقائياً خلال دقيقة واحدة
```

---

## استكشاف الأخطاء

### المشكلة: الموقع لا يظهر بشكل صحيح

**الحل:**
1. افتح Developer Tools (F12)
2. تحقق من الأخطاء في Console
3. تحقق من الملفات المفقودة
4. امسح ذاكرة التخزين المؤقتة

### المشكلة: الألوان لا تتغير

**الحل:**
1. تأكد من حفظ الملف
2. امسح ذاكرة التخزين المؤقتة
3. تحقق من الكود (قد يكون هناك خطأ)
4. أعد تحميل الصفحة

### المشكلة: الروابط لا تعمل

**الحل:**
1. تحقق من مسار الرابط
2. تأكد من أن الملف موجود
3. تحقق من الأقواس والعلامات
4. جرب رابط مختلف

---

## نصائح مهمة

### 1. احفظ نسخة احتياطية

```bash
# قبل أي تعديل كبير
cp -r taj-guides-website taj-guides-website-backup
```

### 2. استخدم Git للتتبع

```bash
# تتبع التغييرات
git status

# عرض الفروقات
git diff
```

### 3. اختبر قبل النشر

```bash
# اختبر محلياً أولاً
python3 -m http.server 8000
```

### 4. استخدم التعليقات

```html
<!-- هذا تعليق -->
<!-- يساعدك على تذكر ما فعلت -->
```

---

## موارد مفيدة

- [HTML Tutorial](https://www.w3schools.com/html/)
- [CSS Tutorial](https://www.w3schools.com/css/)
- [JavaScript Tutorial](https://www.w3schools.com/js/)
- [Color Picker](https://htmlcolorcodes.com/)
- [Icon Search](https://emojipedia.org/)

---

**آخر تحديث:** 22 أبريل 2026  
**الإصدار:** 1.0.0
