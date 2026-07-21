# Session 31 — Variables

متغیرهای CSS (یا **Custom Properties**) به شما اجازه می‌دهند یک مقدار را **یک‌بار تعریف** کنید و در چند جای مختلف استفاده کنید.

در این جلسه دو متغیر در `:root` تعریف شده‌اند و روی رنگ متن، رنگ باکس و سایه‌ی باکس اعمال می‌شوند.

---

## 1. چرا متغیر؟

بدون متغیر، اگر رنگ اصلی سایت را در ۱۰ جا نوشته باشید، برای عوض کردنش باید هر ۱۰ جا را دستی تغییر دهید.

با متغیر:

```css
:root {
  --primary-color: rgb(205, 29, 29);
}

h1 { color: var(--primary-color); }
p  { color: var(--primary-color); }
.box { background-color: var(--primary-color); }
```

فقط مقدار `--primary-color` را عوض می‌کنید؛ همه‌جا به‌روز می‌شود.

---

## 2. تعریف متغیر

شکل کلی:

```css
--name: value;
```

نام همیشه با `--` شروع می‌شود.

در این جلسه متغیرها روی `:root` تعریف شده‌اند تا در **کل صفحه** در دسترس باشند:

```css
:root {
  --primary-color: rgb(205, 29, 29);
  --box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.5);
}
```

| متغیر | مقدار | کاربرد |
| --- | --- | --- |
| `--primary-color` | قرمز | رنگ عنوان، پاراگراف و پس‌زمینه باکس |
| `--box-shadow` | سایه نرم | سایه دور `.box` |

`:root` همان عنصر ریشه سند است (معمولاً `html`)؛ متغیرهای تعریف‌شده روی آن به همه فرزندان به ارث می‌رسند.

---

## 3. استفاده با `var()`

```css
.box {
  width: 100px;
  height: 100px;
  background-color: var(--primary-color);
  box-shadow: var(--box-shadow);
}

h1 {
  color: var(--primary-color);
}

p {
  color: var(--primary-color);
}
```

شکل کلی:

```css
property: var(--variable-name);
```

می‌توان مقدار جایگزین (fallback) هم گذاشت:

```css
color: var(--primary-color, blue);
```

اگر `--primary-color` تعریف نشده باشد، `blue` استفاده می‌شود.

---

## 4. مثال این جلسه

صفحه یک `.container` با عنوان، مربع و متن دارد:

| عنصر | استفاده از متغیر |
| --- | --- |
| `h1` | `color: var(--primary-color)` |
| `p` | `color: var(--primary-color)` |
| `.box` | `background-color` و `box-shadow` از متغیرها |

اگر در `:root` مقدار `--primary-color` را عوض کنید، رنگ عنوان، متن و باکس با هم عوض می‌شوند.

---

## 5. محدوده (Scope)

متغیرها قابل ارث‌بری هستند. می‌توان روی یک کلاس هم تعریف کرد:

```css
.card {
  --primary-color: green;
}

.card h1 {
  color: var(--primary-color); /* اینجا سبز */
}
```

داخل `.card` مقدار محلی اولویت دارد؛ بیرون از آن همان مقدار `:root` باقی می‌ماند.

---

## 6. چه چیزهایی را می‌توان در متغیر گذاشت؟

تقریباً هر مقدار CSS:

```css
:root {
  --primary-color: #cd1d1d;
  --gap: 20px;
  --radius: 10px;
  --box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  --font-main: "Segoe UI", sans-serif;
}
```

رنگ، اندازه، سایه، فونت و حتی بخش‌هایی از `transition` قابل ذخیره در متغیرند.

---

## خلاصه مثال این جلسه

| بخش | مقدار | نتیجه |
| --- | --- | --- |
| `:root` | `--primary-color` | رنگ مشترک قرمز |
| `:root` | `--box-shadow` | سایه مشترک باکس |
| `h1`, `p` | `var(--primary-color)` | متن قرمز |
| `.box` | `var(--primary-color)` + `var(--box-shadow)` | مربع قرمز با سایه |

با تغییر فقط دو خط در `:root`، ظاهر چند بخش صفحه یکجا عوض می‌شود.
