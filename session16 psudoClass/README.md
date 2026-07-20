# Session 16 — Pseudo-classes

Pseudo-class با `:` نوشته می‌شود و وقتی عنصر در یک **حالت خاص** باشد، استایل اعمال می‌کند (مثلاً هاور، فوکوس، تیک‌خورده، خالی بودن).

شکل کلی:

```css
selector:pseudo-class {
  /* styles */
}
```

---

## 1. `:hover`
وقتی ماوس روی عنصر باشد.

```css
.btn:hover {
  background-color: azure;
  border: 1px solid #ff0000;
}
```

---

## 2. `:active`
لحظه‌ای که عنصر را **کلیک/فشار** می‌دهید.

```css
.btn:active {
  background-color: #000;
  color: #fff;
  border: 1px solid #00ff48;
}
```

---

## 3. `:visited`
برای لینک‌هایی که قبلاً باز شده‌اند.

```css
a:visited {
  color: #00ff48;
}
```

> روی `:visited` معمولاً فقط چند خاصیت محدود مثل `color` قابل اعتماد هستند.

---

## 4. `:focus`
وقتی عنصر فوکوس دارد (کلیک داخل input یا کلید Tab).

```css
.textinput:focus {
  width: 500px;
  padding: 10px;
}
```

---

## 5. `:checked`
وقتی checkbox یا radio انتخاب شده باشد.

در این مثال با **Adjacent Sibling** (`+`) ترکیب شده: اگر checkbox تیک بخورد، پاراگراف بعدی نمایش داده می‌شود.

```css
.alertCheckbox {
  display: none;
}

.checkbox:checked + .alertCheckbox {
  display: block;
}
```

`+` یعنی فقط عنصری که بلافاصله بعد از checkbox آمده است.

---

## 6. `:first-child` / `:last-child` / `:nth-child()`
انتخاب بر اساس **موقعیت** بین خواهر و برادرها (siblings).

```css
.list .item:first-child {
  background-color: #000000; /* اولین آیتم */
  color: #fff;
}

.list .item:last-child {
  background-color: #ff0000; /* آخرین آیتم */
}

.list .item:nth-child(3) {
  background-color: #00ff48; /* سومین آیتم */
}
```

`:nth-child(n)` شماره موقعیت را می‌گیرد (`1`، `2`، `3`، ...).

---

## 7. `:not()`
همه موارد را انتخاب می‌کند **به‌جز** آنچه داخل پرانتز است.

```css
.list .item:not(.notActive) {
  background-color: #0071a5;
  color: #fff;
}
```

یعنی همه `.item`ها به‌جز آن‌هایی که کلاس `notActive` دارند.

در لیست این جلسه، آیتم‌های ۴، ۶ و ۹ کلاس `notActive` دارند و این قانون رویشان اعمال نمی‌شود.

---

## 8. `:empty`
عنصری را انتخاب می‌کند که **هیچ محتوایی** داخلش نباشد (نه متن، نه تگ فرزند).

```css
div:empty {
  background-color: #ff0000;
  height: 100px;
  width: 100px;
}
```

در HTML یک `<div></div>` خالی داریم که قرمز دیده می‌شود؛ ولی `<div class="box">class not empty</div>` چون محتوا دارد، انتخاب نمی‌شود.

---

## ترتیب رایج برای لینک‌ها (LVHA)

```text
:link → :visited → :hover → :active
```

---

## خلاصه مثال‌های این جلسه

| عنصر | Pseudo-class | اثر |
| --- | --- | --- |
| `.btn` | `:hover` | پس‌زمینه azure، border قرمز |
| `.btn` | `:active` | پس‌زمینه سیاه، متن سفید |
| `a` | `:visited` | رنگ سبز بعد از بازدید |
| `.textinput` | `:focus` | عرض و padding بیشتر |
| `.checkbox` | `:checked` + `+` | نمایش متن قوانین |
| `.item` | `:first-child` | اولین آیتم |
| `.item` | `:last-child` | آخرین آیتم |
| `.item` | `:nth-child(3)` | سومین آیتم |
| `.item` | `:not(.notActive)` | همه به‌جز غیرفعال‌ها |
| `div` | `:empty` | باکس قرمز برای div خالی |
