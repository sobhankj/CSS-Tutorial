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
نام تگ را با کلاس ترکیب می‌کنیم تا فقط همان تگ با آن کلاس انتخاب شود.

```css
span.first {
  color: purple;
}
```

```html
<span class="first">...</span>
```

## 7. Descendant Selector (` `)
با فاصله نوشته می‌شود. همه فرزندان داخل والد را انتخاب می‌کند (حتی نوه‌ها و عمیق‌تر).

```css
.parent .child {
  color: orange;
}
```

## 8. Child Selector (`>`)
فقط فرزندان مستقیم والد را انتخاب می‌کند؛ نوه‌ها را نه.

```css
.parent2 > .child {
  border: 1px solid black;
}
```

در این مثال فقط `.child`هایی که مستقیم داخل `.parent2` هستند بوردر می‌گیرند؛ `.grandchild` نه.

## 9. Adjacent Sibling (`+`)
عنصر بعدیِ هم‌سطح را انتخاب می‌کند؛ فقط یکی که بلافاصله بعد از آن آمده باشد.

```css
.title + .description {
  border: 1px solid black;
}
```

فقط اولین `.description` درست بعد از `.title` بوردر می‌گیرد؛ دومی نه.

## 10. General Sibling (`~`)
همه عناصر هم‌سطح بعدی با آن سلکتور را انتخاب می‌کند.

```css
.title2 ~ .description2 {
  border: 1px solid black;
}
```

هر دو `.description2` بعد از `.title2` بوردر می‌گیرند.
