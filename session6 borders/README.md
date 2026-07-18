# Session 6 — Borders

در این جلسه یاد می‌گیریم چطور برای عناصر **حاشیه (border)** و **گوشه گرد (border-radius)** تعریف کنیم.

هر سه باکس ابعاد یکسان دارند:

```css
width: 300px;
height: 300px;
```

---

## 1. اجزای Border
هر border سه بخش دارد:

| خاصیت | معنی | مثال |
| --- | --- | --- |
| `border-width` | ضخامت | `3px` |
| `border-style` | نوع خط | `solid`، `dashed` |
| `border-color` | رنگ | `red` |

```css
border-width: 3px;
border-style: solid;   /* خط توپر */
border-style: dashed;  /* خط چین */
border-color: red;
```

بدون `border-style` معمولاً border دیده نمی‌شود.

---

## 2. Shorthand: `border`
هر سه مورد را می‌توان در یک خط نوشت:

```css
.box {
  border: 3px solid red;
}
```

ترتیب رایج:

```text
border: [width] [style] [color];
```

---

## 3. Border فقط یک طرف
به‌جای هر چهار طرف، می‌توان فقط یک سمت را تنظیم کرد:

| خاصیت | سمت |
| --- | --- |
| `border-top` | بالا |
| `border-right` | راست |
| `border-bottom` | پایین |
| `border-left` | چپ |

```css
.box2 {
  border-right: 3px solid rgb(34, 0, 255);
}
```

در این مثال فقط ضلع راست آبی است.

---

## 4. `border-radius`
گوشه‌های عنصر را گرد می‌کند.

```css
.box3 {
  background-color: rgba(0, 255, 85, 0.5);
  border-radius: 40px;
}
```

هرچه عدد بزرگ‌تر باشد، گوشه‌ها گردتر می‌شوند. برای دایره کامل، معمولاً `50%` یا مقداری برابر نصف عرض/ارتفاع استفاده می‌شود.

---

## خلاصه مثال‌های این جلسه

| کلاس | چه می‌کند |
| --- | --- |
| `.box` | border کامل قرمز با shorthand |
| `.box2` | فقط border سمت راست (آبی) |
| `.box3` | پس‌زمینه سبز نیمه‌شفاف + گوشه گرد |
