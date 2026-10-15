# مرسى الأعمال — Landing Page (Business Harbor)

صفحة هبوط ثابتة (HTML/CSS/JS فقط، بدون أي framework أو build step).

## الملفات
```
index.html        الصفحة الرئيسية
thank-you.html    صفحة الشكر (يتم التحويل لها بعد إرسال الفورم)
privacy.html      سياسة الخصوصية
assets/img/       كل الصور (WebP مضغوطة)
```

## النشر (Deploy)
ارفع **كل محتويات هذا الفولدر كما هي** إلى جذر الموقع (أو أي مسار فرعي) على أي استضافة ثابتة:
Netlify / Vercel / Cloudflare Pages / GitHub Pages / cPanel / Nginx / Apache.
كل الروابط نسبية، فالصفحة تعمل على أي دومين بدون تعديل.

نصيحة أداء: فعّل ضغط gzip/brotli وكاش طويل للفولدر `assets/` على السيرفر (أغلب الاستضافات تفعّله تلقائيًا).

## إعدادات موجودة داخل index.html (ابحث عنها بالاسم)
| المتغير | القيمة الحالية | الوظيفة |
|---|---|---|
| `WHATSAPP_NUMBER` | `905541238888` | رقم واتساب لكل الأزرار (موجود أيضًا في thank-you.html) |
| `THANK_YOU_URL` | `thank-you.html` | الصفحة التي يتم التحويل لها بعد إرسال الفورم |
| `LEADS_ENDPOINT` | رابط Google Apps Script | يحفظ كل Lead في Google Sheet ("Leads - مرسى الأعمال (Landing Page)") |

## التتبع (Tracking)
- Google Tag Manager: `GTM-MXP297FD` مركّب في الصفحات الثلاث.
- أحداث dataLayer:
  - `generate_lead` عند إرسال الفورم بنجاح (`form_location`: hero / final، `business_type`)
  - `whatsapp_click` عند الضغط على أي زر واتساب (`click_location`)
  - `thank_you_view` عند فتح صفحة الشكر
- يتم حفظ قيم UTM من رابط الإعلان وإرسالها مع الـ Lead إلى الشيت.

## ملاحظات
- الخطوط من Google Fonts (IBM Plex Sans Arabic).
- قسم فيديوهات "شاهد تجارب عملائنا" ما زال يحتوي على أماكن مؤقتة للفيديوهات.
