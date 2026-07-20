# Session 24 — Attribute Selectors

Attribute Selector عناصر را بر اساس **ویژگی (attribute)** HTML انتخاب می‌کند؛ مثل `type`، `name`، `placeholder`.

شکل کلی داخل `[ ]` نوشته می‌شود:

```css
[attribute] { }
[attribute="value"] { }
```

---

## 1. مقدار دقیق: `[attr="value"]`
عنصرهایی که آن attribute دقیقاً برابر مقدار داده‌شده باشد.

```css
[name="username"] {
  background-color: #ff0000;
  color: #fff;
}

[name="password"] {
  background-color: #00ff00;
  color: #fff;
}
```

در این مثال:
- ورودی با `name="username"` → قرمز
- ورودی با `name="password"` → سبز

---

## 2. وجود attribute: `[attr]`
فقط کافی است آن ویژگی روی عنصر باشد؛ مقدارش مهم نیست.

```css
[placeholder] {
  border: 1px solid #d400ff;
  color: #fff;
}
```

چون همه inputهای این جلسه `placeholder` دارند، همه border بنفش می‌گیرند.

---

## 3. شروع با مقدار: `[attr^="value"]`
مقدار attribute با آن متن **شروع** شود.

```css
[type^="nu"] {
  background-color: #0000ff;
  color: #fff;
}
```

`type="number"` با `nu` شروع می‌شود → پس‌زمینه آبی.

---

## 4. پایان با مقدار: `[attr$="value"]`
مقدار attribute با آن متن **تمام** شود.

```css
[type$="te"] {
  background-color: #00a6ff;
  color: #fff;
}
```

`type="date"` با `te` تمام می‌شود → پس‌زمینه آبی روشن.

---

## سایر حالت‌های رایج (برای آشنایی)

| سلکتور | معنی |
| --- | --- |
| `[attr*="val"]` | مقدار شامل `val` باشد |
| `[attr~="val"]` | یکی از کلمات فاصله‌دار برابر `val` باشد |
| `[attr\|="val"]` | برابر `val` یا شروع با `val-` |

در این جلسه از این‌ها استفاده نشده، ولی کنار `^=` و `$=` خیلی کاربردی‌اند.

---

## می‌توان با تگ ترکیب کرد

```css
input[type="email"] { }
a[href^="https"] { }
```

یعنی فقط همان تگ، با آن شرط attribute.

---

## خلاصه مثال‌های این جلسه

| سلکتور | معنی | اثر در صفحه |
| --- | --- | --- |
| `[name="username"]` | name دقیقاً username | پس‌زمینه قرمز |
| `[name="password"]` | name دقیقاً password | پس‌زمینه سبز |
| `[placeholder]` | هر عنصری که placeholder دارد | border بنفش |
| `[type^="nu"]` | type با nu شروع شود | `number` آبی |
| `[type$="te"]` | type با te تمام شود | `date` آبی روشن |

> نکته: اگر چند قانون روی یک عنصر بخورد، قانون‌های بعدی (یا specificity بالاتر) ممکن است رنگ نهایی را عوض کنند.
