# Session 25 — Gradients

Gradient یعنی یک **انتقال نرم بین رنگ‌ها**؛ معمولاً به‌عنوان `background` استفاده می‌شود، نه یک رنگ تخت.

در این جلسه دو نوع مهم را می‌بینیم:

- `linear-gradient` — گرادیانت خطی
- `radial-gradient` — گرادیانت دایره‌ای/شعاعی

---

## 1. `linear-gradient`
رنگ‌ها در یک **جهت خطی** از هم عبور می‌کنند.

شکل کلی:

```css
background: linear-gradient(direction, color1, color2, ...);
```

### مثال این جلسه

```css
.gradient {
  width: 100vw;
  height: 100vh;
  background: linear-gradient(45deg, #0000ff99, #ff0000);
}
```

| بخش | معنی |
| --- | --- |
| `45deg` | زاویه جهت گرادیانت (۴۵ درجه) |
| `#0000ff99` | آبی نیمه‌شفاف (دو رقم آخر = alpha در HEX هشت‌رقمی) |
| `#ff0000` | قرمز |

صفحه کامل (`100vw × 100vh`) با این گرادیانت خطی پر شده است.

### جهت‌های رایج

```css
linear-gradient(to right, blue, red);   /* چپ → راست */
linear-gradient(to bottom, blue, red);  /* بالا → پایین */
linear-gradient(to top left, blue, red);
linear-gradient(90deg, blue, red);      /* با زاویه */
```

می‌توان بیش از دو رنگ هم گذاشت:

```css
linear-gradient(90deg, red, yellow, green);
```

---

## 2. `radial-gradient`
رنگ‌ها از یک **مرکز** به سمت بیرون پخش می‌شوند (دایره یا بیضی).

شکل کلی:

```css
background: radial-gradient(shape, color1, color2, ...);
```

### مثال این جلسه

```css
.gradient-item {
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, #4a4aff, #ffb0d2);
  border-radius: 50%;
}
```

| بخش | معنی |
| --- | --- |
| `circle` | شکل شعاعی دایره |
| `#4a4aff` | رنگ مرکز (آبی) |
| `#ffb0d2` | رنگ بیرونی (صورتی) |

با `border-radius: 50%` خود عنصر هم دایره شده و گرادیانت شعاعی داخلش دیده می‌شود.

### شکل‌های رایج

```css
radial-gradient(circle, blue, pink);
radial-gradient(ellipse, blue, pink);
radial-gradient(circle at top, blue, pink); /* مرکز بالا */
```

---

## نکته مهم
Gradient معمولاً روی `background` یا `background-image` نوشته می‌شود:

```css
background: linear-gradient(...);
/* معادل تقریبی: */
background-image: linear-gradient(...);
```

اگر بعداً `background-color` جدا بنویسید، ممکن است گرادیانت را نپوشاند؛ ولی `background` shorthand ممکن است مقادیر قبلی را عوض کند.

---

## خلاصه مثال‌های این جلسه

| کلاس | نوع | نتیجه |
| --- | --- | --- |
| `.gradient` | `linear-gradient(45deg, ...)` | پس‌زمینه تمام‌صفحه آبی → قرمز |
| `.gradient-item` | `radial-gradient(circle, ...)` | دایره با مرکز آبی و لبه صورتی |

وسط صفحه یک دایره با گرادیانت شعاعی روی پس‌زمینه گرادیانت خطی دیده می‌شود.
