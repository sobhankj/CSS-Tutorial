# Session 28 — Transition

`transition` به CSS اجازه می‌دهد تغییر یک property را **به‌صورت نرم و تدریجی** انجام دهد؛ به‌جای اینکه مقدار ناگهان عوض شود.

در این جلسه با یک مربع ساده، تغییر `background-color` از قرمز به آبی هنگام `:hover` را با انیمیشن نرم می‌بینیم.

---

## 1. مشکل بدون `transition`

اگر فقط این کد را بنویسیم:

```css
.colorful {
  background-color: red;
}
.colorful:hover {
  background-color: blue;
}
```

رنگ **یک‌باره** از قرمز به آبی می‌پرد. هیچ حرکت یا محو شدن تدریجی وجود ندارد.

---

## 2. ساختار `transition`

شکل کلی:

```css
transition: property duration timing-function delay;
```

| بخش | معنی |
| --- | --- |
| `property` | کدام ویژگی انیمیت شود (`all` = همه) |
| `duration` | مدت زمان انیمیشن (مثلاً `0.5s` یا `500ms`) |
| `timing-function` | منحنی سرعت (`ease`, `linear`, ...) |
| `delay` | تأخیر قبل از شروع (اختیاری) |

---

## 3. مثال این جلسه

```css
.colorful {
  width: 100px;
  height: 100px;
  background-color: red;
  transition: background-color 0.5s ease 20ms;
}

.colorful:hover {
  background-color: blue;
}
```

| بخش | معنی |
| --- | --- |
| `background-color` | فقط رنگ پس‌زمینه انیمیت می‌شود |
| `0.5s` | نیم ثانیه طول می‌کشد |
| `ease` | شروع و پایان نرم (سرعت در وسط بیشتر) |
| `20ms` | ۲۰ میلی‌ثانیه تأخیر قبل از شروع |

یک مربع ۱۰۰×۱۰۰ پیکسل با پس‌زمینه قرمز دیده می‌شود. با hover، رنگ به آبی **به‌آرامی** تغییر می‌کند و با خارج شدن ماوس دوباره به قرمز برمی‌گردد.

---

## 4. `transition` را کجا بنویسیم؟

معمولاً روی **حالت پایه** (نه فقط `:hover`) می‌نویسیم:

```css
.box {
  transition: background-color 0.5s ease;
}
.box:hover {
  background-color: blue;
}
```

این‌طوری هم رفتن به hover و هم برگشت از آن هر دو نرم خواهند بود.

---

## 5. `timing-function` — مقادیر رایج

```css
transition: all 0.5s linear;      /* سرعت ثابت */
transition: all 0.5s ease;          /* پیش‌فرض؛ نرم */
transition: all 0.5s ease-in;     /* آهسته شروع، سریع پایان */
transition: all 0.5s ease-out;    /* سریع شروع، آهسته پایان */
transition: all 0.5s ease-in-out; /* آهسته شروع و پایان */
```

---

## 6. چند property همزمان

```css
transition: background-color 0.5s ease, transform 0.3s ease;
```

یا برای همه propertyها:

```css
transition: all 0.5s ease;
```

`all` راحت است، ولی گاهی propertyهای ناخواسته هم انیمیت می‌شوند؛ در پروژه‌های بزرگ‌تر بهتر است propertyها را صریح بنویسید.

---

## 7. propertyهای قابل transition

فقط propertyهایی که **مقدار عددی یا قابل محاسبه** دارند معمولاً transition می‌گیرند:

| قابل transition | معمولاً نه |
| --- | --- |
| `background-color` | `display` |
| `width`, `height` | `font-family` |
| `opacity` | `visibility` (با نکته) |
| `transform` | — |
| `box-shadow` | — |

---

## 8. `transition` vs `animation`

| | `transition` | `animation` |
| --- | --- | --- |
| نیاز به trigger | بله (مثلاً `:hover`) | می‌تواند خودکار باشد |
| تکرار | فقط بین دو حالت | `@keyframes` با تکرار |
| پیچیدگی | ساده | پیشرفته‌تر |

`transition` برای تغییر بین دو state کافی است؛ برای انیمیشن‌های پیچیده‌تر از `@keyframes` استفاده می‌شود.

---

## خلاصه مثال این جلسه

| بخش | مقدار | نتیجه |
| --- | --- | --- |
| `.colorful` | `100px × 100px` | مربع قرمز |
| `.colorful` | `transition: background-color 0.5s ease 20ms` | تغییر نرم رنگ |
| `.colorful:hover` | `background-color: blue` | آبی شدن با hover |

یک مربع قرمز با hover به آبی تبدیل می‌شود؛ تغییر رنگ نیم ثانیه طول می‌کشد و با ۲۰ms تأخیر شروع می‌شود.
