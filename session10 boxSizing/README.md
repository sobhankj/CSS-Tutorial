# Session 10 — Box Sizing (`border-box`)

`box-sizing` مشخص می‌کند که `width` و `height` دقیقاً **چه بخش‌هایی از باکس** را شامل شوند.

در این جلسه برای همه عناصر می‌نویسیم:

```css
* {
  box-sizing: border-box;
}
```

و روی باکس مثال:

```css
.box1 {
  width: 200px;
  height: 200px;
  padding: 20px;
  border: 10px solid #000000;
}
```

---

## مدل پیش‌فرض: `content-box`
اگر `box-sizing` ننویسید، مقدار پیش‌فرض `content-box` است.

در این حالت:

```text
width / height = فقط اندازه محتوا (content)
```

`padding` و `border` **اضافه** می‌شوند و باکس را بزرگ‌تر از `200px` می‌کنند.

محاسبه عرض واقعی روی صفحه:

```text
عرض نهایی = width + padding-left + padding-right + border-left + border-right
عرض نهایی = 200 + 20 + 20 + 10 + 10 = 260px
```

ارتفاع هم به همین شکل `260px` می‌شود.

مشکل: فکر می‌کنید باکس `200px` است، ولی در عمل `260px` اشغال می‌کند. در لایه‌بندی‌ها (مثلاً دو ستون ۵۰٪) این موضوع خیلی اذیت می‌کند.

---

## مدل `border-box`
با `box-sizing: border-box`:

```text
width / height = content + padding + border
```

یعنی `200px` کل باکس است؛ padding و border از همان فضای داخل کم می‌شوند.

محاسبه فضای محتوا:

```text
عرض محتوا = width - padding-left - padding-right - border-left - border-right
عرض محتوا = 200 - 20 - 20 - 10 - 10 = 140px
```

ارتفاع محتوا هم `140px` می‌شود.

نتیجه: اندازه نهایی باکس روی صفحه همان `200px × 200px` می‌ماند.

---

## مقایسه سریع

| | `content-box` (پیش‌فرض) | `border-box` |
| --- | --- | --- |
| `width: 200px` یعنی چه؟ | فقط محتوا | کل باکس |
| padding و border | بیرون از width اضافه می‌شوند | داخل width جا می‌گیرند |
| اندازه نهایی این مثال | `260px` | `200px` |
| پیش‌بینی‌پذیری در layout | سخت‌تر | راحت‌تر |

---

## چرا معمولاً `* { box-sizing: border-box; }` می‌گذارند؟
چون رفتار اندازه‌ها منطقی‌تر می‌شود:

- وقتی می‌نویسید `width: 50%`، دقیقاً نصف والد می‌ماند (حتی با padding/border)
- محاسبات ذهنی ساده‌تر است
- باکس‌ها از ظرفشان بیرون نمی‌زنند

این یکی از رایج‌ترین resetهای CSS در پروژه‌های واقعی است.

---

## نکته درباره `margin`
`margin` در هیچ‌کدام از مدل‌ها داخل `width` حساب نمی‌شود. فاصله بیرونی همیشه جداست.

```text
content-box:  [margin][border][padding][content][padding][border][margin]
border-box:   [margin][==== width شامل border+padding+content ====][margin]
```

---

## خلاصه مثال این جلسه

```css
* {
  box-sizing: border-box;
}

.box1 {
  width: 200px;   /* کل باکس = 200px */
  height: 200px;  /* کل باکس = 200px */
  padding: 20px;  /* از داخل کم می‌شود */
  border: 10px solid #000000; /* از داخل کم می‌شود */
}
```

اگر `box-sizing: border-box` را حذف کنید و صفحه را رفرش کنید، باکس بزرگ‌تر از `200px` دیده می‌شود.
