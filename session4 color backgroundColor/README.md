# Session 4 — Color & Background Color

در این جلسه دو خاصیت مهم رنگ را می‌بینیم:

- `color` — رنگ متن
- `background-color` — رنگ پس‌زمینه

رنگ را می‌توان به چند شکل نوشت:

## 1. Named Color
نام آماده رنگ، مثل `red`، `blue`، `yellow`.

```css
h1 {
  color: red;
  background-color: black;
}

p {
  color: blue;
  background-color: yellow;
}
```

## 2. RGB
با `rgb(red, green, blue)` نوشته می‌شود. هر عدد از `0` تا `255` است.

```css
.rgb {
  color: rgb(255, 0, 0);           /* قرمز */
  background-color: rgb(0, 0, 255); /* آبی */
}
```

## 3. RGBA
مثل RGB است، ولی پارامتر چهارم (`alpha`) شفافیت را مشخص می‌کند؛ از `0` (کاملاً شفاف) تا `1` (کاملاً مات).

```css
.rgba {
  color: rgba(255, 0, 0, 0.5);
  background-color: rgba(0, 0, 255, 0.5);
}
```

## 4. HEX
با `#` و کد شش‌رقمی رنگ نوشته می‌شود: دو رقم برای قرمز، دو رقم سبز، دو رقم آبی.

```css
.hex {
  color: #ff0000;           /* قرمز */
  background-color: #0000ff; /* آبی */
}
```

در این جلسه هر چهار روش در `index.html` کنار هم پیاده شده‌اند.
