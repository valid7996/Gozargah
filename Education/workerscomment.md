<h1 align="center">🚀 نصب از طریق Cloudflare Workers</h1>

### مرحله 1: دانلود کد Worker  
ابتدا کد Worker را از لینک زیر دانلود کنید و به داشبورد **Cloudflare Workers** منتقل کنید. به‌جای Copy-Paste، فایل را آپلود کنید تا کار آسان‌تر باشد.  
[دانلود کد Worker](https://github.com/valid7996/Gozargah/blob/main/worker_vless/%20_worker.js)

در گوشی‌های موبایل، منوی کناری را باز کنید، روی گزینه **Upload** نگه دارید و فایل را آپلود کنید:  
<p align="center">
  <img src="https://github.com/valid7996/Gozargah/blob/main/images/imagwor/IMG_20250104_163617.jpg" alt="آپلود فایل" width="70%">
</p>

### مرحله 2: Save & Deploy  
پس از آپلود کد، می‌توانید از مقادیر پیش‌فرض استفاده کنید یا به بخش **[تنظیمات پیشرفته](#تنظیمات-پیشرفته-اختیاری)** مراجعه کنید.  
در نهایت، روی گزینه `Save and Deploy` کلیک کنید:  
<p align="center">
  <img src="https://github.com/valid7996/Gozargah/blob/main/images/imagwor/IMG_20250104_163647.jpg" alt="ذخیره و انتشار" width="70%">
</p>

---

<h1 align="center">⚙️ تنظیمات پیشرفته (اختیاری)</h1>

<div dir="rtl" align="right">
اگر نیاز به تغییر <strong>UUID</strong> یا <strong>Proxy IP</strong> دارید، می‌توانید این مرحله را انجام دهید. توصیه می‌شود حداقل <strong>UUID</strong> را تغییر دهید.
</div>

---

## تغییر UUID  
<div dir="rtl" align="right">
۱. UUID به‌عنوان یک شناسه در لینک‌های اشتراک و کانفیگ‌ها استفاده می‌شود.  

  ۲. تغییر آن باعث قطع دسترسی کاربران فعلی می‌شود، بنابراین باید کانفیگ‌ها را دوباره به اشتراک بگذارید.
</div>

### مراحل تغییر UUID:
<div dir="rtl" align="right">
<ul>
<li>از منوی سمت چپ، به بخش <strong>Workers & Pages</strong> بروید.</li>
<li>روی Worker ساخته‌شده کلیک کنید، به <strong>Settings</strong> بروید و گزینه <strong>Variables and Secrets</strong> را پیدا کنید:</li>
</ul>
</div>

<p align="center">
  <img src="https://github.com/valid7996/Gozargah/blob/main/images/imagwor/IMG_20250104_163547.jpg" alt="تنظیمات" width="70%">
</p>

<div dir="rtl" align="right">
<ul>
<li>گزینه <strong>Add Variable</strong> را انتخاب کنید:</li>
<ul>
<li>در فیلد اول `uuid` را وارد کنید.</li>
<li>از <a href="https://www.uuidgenerator.net/">اینجا</a> یک UUID جدید بگیرید و در فیلد دوم قرار دهید.</li>
</ul>
</ul>
</div>

<p align="center">
  <img src="https://github.com/valid7996/Gozargah/blob/main/images/imagwor/InShot_20250104_155744172.jpg" alt="افزودن UUID" width="70%">
</p>

---

## ثابت کردن Proxy IP  
<div dir="rtl" align="right">
اگر نیاز دارید IP ثابت برای پروکسی تعریف کنید:
<ul>
<li>دوباره <strong>Add Variable</strong> را بزنید.</li>
<li>در فیلد اول `proxyip` را بنویسید.</li>
<li>از <a href="https://www.nslookup.io/domains/bpb.yousef.isegaro.com/dns-records/">Proxy IP</a> یک IP انتخاب کنید و در فیلد دوم وارد کنید.</li>
</ul>
</div>

<p align="center">
  <img src="https://github.com/valid7996/Gozargah/blob/main/images/imagwor/InShot_20250104_155719489.jpg" alt="افزودن Proxy IP" width="70%">
</p>

---

<h1 align="center">🌐 اتصال دامنه به Worker</h1>

<div dir="rtl" align="right">
برای اتصال دامنه به Worker:
<ol>
<li>به داشبورد Cloudflare بروید و از بخش <strong>Workers and Pages</strong>، Worker خود را انتخاب کنید.</li>
<li>به قسمت <strong>Settings</strong> رفته و <strong>Domains & Routes</strong> را باز کنید.</li>
<li>گزینه <strong>Add +</strong> را بزنید و <strong>Custom Domain</strong> را انتخاب کنید.</li>
<li>دامنه یا زیردامنه موردنظر (مثلاً `xyz.bv.com`) را وارد کنید.</li>
<li>روی <strong>Add Domain</strong> کلیک کنید.</li>
<li>سپس <strong>Route</strong> را اضافه کنید و دامنه را به شکل زیر وارد کنید:</li>
</ol>
</div>
<div dir="rtl" align="right">
بعد از این می‌توانید از آدرس <code>https://domin.com/uuid</code> وارد پنل شوید و تنظیمات را مشاهده کنید.
</div>

---

<h1 align="center">🔧 مقادیر پیش‌فرض</h1>

| شرح          | مقدار پیش‌فرض                      | مقدار سفارشی      |
|:-------------|:----------------------------------|:------------------|
| **UUID**     | 86c50e3a-5687-49dd-bd20-03c7f2735 | سفارشی‌شده توسط شما |
| **Proxy IP** | ts.hpc.tw                         | تنظیم‌شده توسط شما |

<div dir="rtl" align="right">
<strong>توجه:</strong> اگر دامنه را به Worker وصل کنید، ترافیک به‌صورت <strong>نامحدود</strong> خواهد شد.
</div>
