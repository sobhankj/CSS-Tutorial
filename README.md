# Session 1 — CSS Syntax

سینتکس CSS دو بخش اصلی دارد:

1. **Selector** — مشخص می‌کند کدام عنصر HTML استایل بگیرد.
2. **Declaration** — مشخص می‌کند چه استایلی اعمال شود (شامل `property` و `value`).

شکل کلی:

```css
selector {
  property: value;
}
```

## مثال این جلسه

در `session1_syntax/index.html`:

```css
div {
  width: 100px;
  height: 100px;
  background-color: red;
}
```

- `div` همان **selector** است و همه تگ‌های `<div>` را هدف می‌گیرد.
- داخل `{ }` چند **declaration** داریم؛ مثلاً `width: 100px` یعنی عرض ۱۰۰ پیکسل، و `background-color: red` یعنی پس‌زمینه قرمز.

به همین شکل برای `p`، سلکتور پاراگراف را انتخاب می‌کند و سایز فونت، ضخامت و رنگ آبی را روی آن اعمال می‌کند.
