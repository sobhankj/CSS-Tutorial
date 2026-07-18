# Session 2 — CSS Insertion

سه راه برای اضافه کردن CSS به HTML وجود دارد:

## 1. Inline CSS
استایل مستقیم روی خود تگ با ویژگی `style` نوشته می‌شود.

```html
<div style="width: 100px; height: 100px; background-color: blue;"></div>
```

## 2. Internal CSS (Style در Header)
استایل‌ها داخل تگ `<style>` در بخش `<head>` قرار می‌گیرند.

```html
<style>
  .CSS_in {
    width: 100px;
    height: 100px;
    background-color: red;
  }
</style>
```

## 3. External CSS (Link کردن فایل CSS)
استایل‌ها در یک فایل جدا مثل `styles/style.css` نوشته می‌شوند و با `<link>` به HTML وصل می‌شوند.

```html
<link rel="stylesheet" href="./styles/style.css">
```

```css
.CSS_out {
  width: 100px;
  height: 100px;
  background-color: green;
}
```

در این جلسه هر سه روش در `index.html` کنار هم پیاده شده‌اند: آبی (inline)، قرمز (internal)، سبز (external).
