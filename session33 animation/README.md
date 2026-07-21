# Session 33 — Animation

`animation` برخلاف `transition` نیازی به hover یا trigger ندارد؛ با `@keyframes` یک مسیر حرکت تعریف می‌کنید و عنصر **خودکار** آن را اجرا می‌کند.

در این جلسه یک مربع ساده با شش property جداگانه انیمیت می‌شود:

- `animation-name`
- `animation-duration`
- `animation-timing-function`
- `animation-delay`
- `animation-iteration-count`
- `animation-direction`

---

## 1. `@keyframes` — تعریف مسیر انیمیشن

```css
@keyframes moveBox {
  from {
    transform: translateX(-150px);
    background-color: #e63946;
  }
  to {
    transform: translateX(150px);
    background-color: #457b9d;
  }
}
```

| بخش | معنی |
| --- | --- |
| `@keyframes moveBox` | نام انیمیشن = `moveBox` |
| `from` | شروع (معادل `0%`) |
| `to` | پایان (معادل `100%`) |

می‌توان با درصد هم نوشت:

```css
@keyframes moveBox {
  0% { transform: translateX(-150px); }
  50% { transform: translateX(0); }
  100% { transform: translateX(150px); }
}
```

---

## 2. شش property این جلسه

```css
.box {
  width: 100px;
  height: 100px;
  background-color: #e63946;
  border-radius: 12px;
  animation-name: moveBox;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: 0.5s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```

### `animation-name`

نام همان `@keyframes` که باید اجرا شود:

```css
animation-name: moveBox;
```

بدون این نام، انیمیشن پیدا نمی‌شود.

### `animation-duration`

مدت زمان **یک دور** کامل از `from` تا `to`:

```css
animation-duration: 2s;
```

| مقدار | معنی |
| --- | --- |
| `2s` | دو ثانیه |
| `500ms` | نیم ثانیه |

### `animation-timing-function`

منحنی سرعت حرکت:

```css
animation-timing-function: ease-in-out;
```

| مقدار | رفتار |
| --- | --- |
| `linear` | سرعت ثابت |
| `ease` | نرم (پیش‌فرض) |
| `ease-in` | آهسته شروع |
| `ease-out` | آهسته پایان |
| `ease-in-out` | آهسته شروع و پایان |

### `animation-delay`

تأخیر قبل از شروع اولین دور:

```css
animation-delay: 0.5s;
```

در این جلسه نیم ثانیه صبر می‌کند، بعد انیمیشن شروع می‌شود.

### `animation-iteration-count`

چند بار تکرار شود:

```css
animation-iteration-count: infinite;
```

| مقدار | معنی |
| --- | --- |
| `1` | یک‌بار (پیش‌فرض) |
| `3` | سه بار |
| `infinite` | بی‌نهایت |

### `animation-direction`

جهت پخش هر دور:

```css
animation-direction: alternate;
```

| مقدار | معنی |
| --- | --- |
| `normal` | همیشه `from` → `to` |
| `reverse` | همیشه `to` → `from` |
| `alternate` | یک دور رفت، دور بعد برگشت |
| `alternate-reverse` | اول برگشت، بعد رفت |

با `alternate` مربع به راست می‌رود و بعد به چپ برمی‌گردد؛ حرکت رفت‌وبرگشتی دیده می‌شود.

---

## 3. نتیجه مثال این جلسه

مربع قرمز وسط صفحه:

1. ۰.۵ ثانیه صبر می‌کند (`delay`)
2. در ۲ ثانیه از چپ به راست می‌رود و رنگش آبی می‌شود (`duration` + `keyframes`)
3. با `ease-in-out` نرم حرکت می‌کند
4. با `alternate` برمی‌گردد
5. با `infinite` این چرخه قطع نمی‌شود

---

## 4. `animation` vs `transition`

| | `animation` | `transition` |
| --- | --- | --- |
| شروع | خودکار با `@keyframes` | نیاز به تغییر state (مثل `:hover`) |
| مراحل | چند نقطه (`0%`, `50%`, ...) | معمولاً دو حالت |
| تکرار | `iteration-count` | فقط بین دو state |

برای حرکت مستقل و تکراری از `animation` استفاده کنید؛ برای واکنش به hover از `transition`.

---

## 5. شکل shorthand (اختیاری)

همان شش property را می‌توان یک‌جا نوشت:

```css
animation: moveBox 2s ease-in-out 0.5s infinite alternate;
```

ترتیب رایج:

```text
name | duration | timing-function | delay | iteration-count | direction
```

در این جلسه عمداً جدا نوشته شده‌اند تا هر کدام واضح باشد.

---

## خلاصه مثال این جلسه

| Property | مقدار | نقش |
| --- | --- | --- |
| `animation-name` | `moveBox` | اتصال به `@keyframes` |
| `animation-duration` | `2s` | طول هر دور |
| `animation-timing-function` | `ease-in-out` | سرعت نرم |
| `animation-delay` | `0.5s` | تأخیر شروع |
| `animation-iteration-count` | `infinite` | تکرار بی‌نهایت |
| `animation-direction` | `alternate` | رفت و برگشت |

یک مربع که بعد از نیم ثانیه بین چپ و راست حرکت می‌کند، رنگش عوض می‌شود و این حرکت مدام تکرار می‌شود.
