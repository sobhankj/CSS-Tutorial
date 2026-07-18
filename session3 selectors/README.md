# Session 3 — CSS Selectors

Selector مشخص می‌کند کدام عنصر HTML استایل بگیرد. در این جلسه چند نوع رایج را می‌بینیم.

## 1. Element Selector
نام خود تگ را می‌نویسیم؛ همه همان تگ‌ها استایل می‌گیرند.

```css
h1 {
  color: red;
}
```

## 2. ID Selector
با `#` و مقدار `id` نوشته می‌شود. هر `id` در صفحه باید یکتا باشد.

```css
#first {
  color: blue;
}
```

```html
<p id="first">...</p>
```

## 3. Class Selector
با `.` و نام `class` نوشته می‌شود. یک کلاس را می‌توان روی چند عنصر گذاشت.

```css
.second {
  color: green;
}
```

```html
<p class="second">...</p>
```

## 4. Universal Selector (`*`)
همه عناصر صفحه را هدف می‌گیرد.

```css
* {
  font-size: 20px;
}
```

## 5. Grouping Selector
چند سلکتور را با `,` کنار هم می‌گذاریم تا یک استایل مشترک بگیرند.

```css
.second,
#fourth {
  font-size: 30px;
}
```

## 6. Element + Class
نام تگ را با کلاس ترکیب می‌کنیم تا فقط همان تگ با آن کلاس انتخاب شود (نه هر عنصری با آن کلاس).

```css
span.first {
  color: purple;
}
```

```html
<span class="first">...</span>
```

در این مثال فقط `<span class="first">` بنفش می‌شود؛ اگر `p` با کلاس `first` داشتیم، این قانون رویش اعمال نمی‌شد.
