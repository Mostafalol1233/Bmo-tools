# دليل النشر على Vercel

## خطوات النشر السريع

### 1. التحضير
```bash
# تأكد من أن جميع الملفات محفوظة
git add .
git commit -m "Ready for Vercel deployment"
git push origin main
```

### 2. النشر من Vercel Dashboard
1. اذهب إلى [vercel.com](https://vercel.com)
2. سجل دخول أو أنشئ حساب
3. اضغط "New Project"
4. اربط مستودع GitHub
5. اختر المشروع
6. تأكد من الإعدادات:
   - Framework Preset: Other
   - Build Command: `npm run build`
   - Output Directory: `dist/client`
   - Install Command: `npm install`
7. اضغط "Deploy"

### 3. النشر من سطر الأوامر
```bash
# تثبيت Vercel CLI
npm install -g vercel

# تسجيل الدخول
vercel login

# النشر
vercel --prod
```

## إعدادات متغيرات البيئة

في لوحة تحكم Vercel → Settings → Environment Variables:

```
NODE_ENV=production
SESSION_SECRET=your-secure-random-string-here
```

## ملفات مهمة للنشر

- ✅ `vercel.json` - إعدادات Vercel
- ✅ `package.json` - التبعيات والبناء
- ✅ `.gitignore` - ملفات يجب تجاهلها
- ✅ `README.md` - وثائق المشروع
- ✅ `public/sitemap.xml` - خريطة الموقع
- ✅ `public/robots.txt` - إرشادات محركات البحث

## مميزات محسنة للنشر

### الأداء
- ضغط الملفات تلقائياً
- تخزين مؤقت محسن للملفات الثابتة
- CDN عالمي من Vercel

### الأمان
- HTTPS تلقائي
- Headers أمان محسنة
- حماية من XSS و CSRF

### Analytics
- Vercel Analytics مدمج
- تتبع أداء تلقائي
- إحصائيات الزوار

## استكشاف الأخطاء

### خطأ في البناء
```bash
# تشغيل البناء محلياً للتحقق
npm run build
```

### خطأ في التبعيات
```bash
# مسح cache وإعادة التثبيت
rm -rf node_modules package-lock.json
npm install
```

### خطأ في الخادم
- تحقق من logs في Vercel Dashboard
- تأكد من متغيرات البيئة
- راجع إعدادات vercel.json

## بعد النشر

1. تحقق من عمل جميع الأدوات
2. اختبر Vercel Analytics
3. تأكد من SEO والفهرسة
4. اختبر الأداء على أجهزة مختلفة

## Domain مخصص (اختياري)

1. في Vercel Dashboard → Settings → Domains
2. أضف نطاقك المخصص
3. اتبع تعليمات DNS
4. انتظر التفعيل (5-60 دقيقة)

---

🎉 مبروك! موقعك الآن مباشر على Vercel