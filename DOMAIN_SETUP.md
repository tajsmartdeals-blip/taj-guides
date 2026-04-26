# 🌐 دليل إعداد النطاق وشهادة SSL

## خطوات إعداد نطاق مخصص وتفعيل HTTPS

### 1. اختيار وشراء النطاق

#### الخيارات الموصى بها:
- **Namecheap** - رخيص وموثوق
- **GoDaddy** - معروف وسهل الاستخدام
- **Domain.com** - خدمة عملاء جيدة
- **Google Domains** - بسيط وآمن

#### النطاقات المقترحة:
- `taj-guides.com` (الموصى به)
- `tajsmartdeals.com`
- `taj-ecommerce.com`
- `tajmarketplace.com`

### 2. إعداد DNS

#### مع Vercel:
```
1. اذهب إلى Vercel Dashboard
2. اختر المشروع
3. اذهب إلى Settings > Domains
4. أضف النطاق الجديد
5. اتبع التعليمات لإضافة DNS records
```

#### مع Netlify:
```
1. اذهب إلى Netlify Dashboard
2. اختر الموقع
3. اذهب إلى Domain settings
4. أضف النطاق الجديد
5. اتبع التعليمات لإضافة DNS records
```

#### مع GitHub Pages:
```
1. اذهب إلى Settings > Pages
2. أضف النطاق الجديد
3. أضف CNAME record:
   CNAME: yourusername.github.io
```

### 3. إعدادات DNS الشاملة

#### A Records:
```
Host: @
Type: A
Value: (يختلف حسب الخدمة)
TTL: 3600
```

#### CNAME Records:
```
Host: www
Type: CNAME
Value: (يختلف حسب الخدمة)
TTL: 3600
```

#### MX Records (للبريد الإلكتروني):
```
Host: @
Type: MX
Value: mail.google.com
Priority: 10
TTL: 3600
```

### 4. تفعيل HTTPS و SSL

#### مع Vercel (تلقائي):
- Vercel يفعّل SSL تلقائياً عند إضافة النطاق
- الشهادة تتجدد تلقائياً

#### مع Netlify (تلقائي):
- Netlify يفعّل SSL تلقائياً
- يستخدم Let's Encrypt

#### مع GitHub Pages (تلقائي):
- GitHub يفعّل SSL تلقائياً
- يستخدم Let's Encrypt

### 5. التحقق من HTTPS

```bash
# التحقق من شهادة SSL
curl -I https://taj-guides.com

# يجب أن ترى:
# HTTP/2 200
# Strict-Transport-Security: max-age=31536000
```

### 6. إعادة التوجيه من HTTP إلى HTTPS

#### في Vercel:
```json
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

#### في Netlify:
```toml
[[redirects]]
  from = "http://taj-guides.com/*"
  to = "https://taj-guides.com/:splat"
  status = 301
  force = true
```

### 7. إعدادات الأمان الإضافية

#### HSTS Header:
```
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
```

#### Content Security Policy:
```
Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline'; style-src 'self' 'unsafe-inline'
```

#### X-Frame-Options:
```
X-Frame-Options: SAMEORIGIN
```

### 8. اختبار النطاق

```bash
# اختبار DNS
nslookup taj-guides.com

# اختبار الاتصال
ping taj-guides.com

# اختبار HTTPS
openssl s_client -connect taj-guides.com:443
```

### 9. البريد الإلكتروني المخصص (اختياري)

#### مع Google Workspace:
```
1. اشترك في Google Workspace
2. أضف النطاق الخاص بك
3. تحقق من ملكية النطاق
4. أضف MX records
5. أنشئ حسابات بريد مخصصة
```

#### مع Zoho Mail:
```
1. اشترك في Zoho Mail
2. أضف النطاق الخاص بك
3. تحقق من ملكية النطاق
4. أضف MX records
5. أنشئ حسابات بريد مخصصة
```

### 10. مراقبة وصيانة

#### فحص دوري:
```bash
# فحص صحة الموقع
curl -I https://taj-guides.com

# فحص شهادة SSL
echo | openssl s_client -servername taj-guides.com -connect taj-guides.com:443 2>/dev/null | openssl x509 -noout -dates

# فحص DNS
dig taj-guides.com
```

#### تحديث السجلات:
- تحقق من صحة DNS records شهرياً
- تأكد من تجديد شهادة SSL
- راقب وقت التحميل والأداء

## 💡 نصائح مهمة

1. **اختر مسجل نطاقات موثوق** - تجنب المسجلات الرخيصة جداً
2. **فعّل المصادقة الثنائية** - لحماية حساب النطاق
3. **احتفظ بنسخة احتياطية من DNS** - احفظ جميع السجلات
4. **استخدم HTTPS دائماً** - أمان وثقة العملاء
5. **راقب شهادة SSL** - تجدد قبل انتهاء الصلاحية

## 🔗 روابط مفيدة

- [Vercel Domains](https://vercel.com/docs/concepts/projects/domains)
- [Netlify Domains](https://docs.netlify.com/domains-https/custom-domains/)
- [GitHub Pages Custom Domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [Let's Encrypt](https://letsencrypt.org/)
- [SSL Labs](https://www.ssllabs.com/ssltest/)

---

**آخر تحديث**: 22 أبريل 2026
