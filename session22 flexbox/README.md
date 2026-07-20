# Session 22 — Flexbox

Flexbox یک مدل چیدمان برای قرار دادن عناصر در یک **ردیف یا ستون** است و تراز کردنشان را ساده می‌کند.

برای شروع، روی ظرف (والد) می‌نویسیم:

```css
.container {
  display: flex;
}
```

با این کار، فرزندان مستقیمِ `.container` تبدیل به **flex item** می‌شوند.

---

## مفاهیم اصلی

| مفهوم | معنی |
| --- | --- |
| Flex Container | همان والد با `display: flex` |
| Flex Item | فرزندان مستقیم container |
| Main Axis | محور اصلی (پیش‌فرض: افقی، چپ → راست) |
| Cross Axis | محور عمود بر main axis (پیش‌فرض: عمودی) |

پیش‌فرض Flex این است که آیتم‌ها در یک **ردیف افقی** کنار هم قرار بگیرند (`flex-direction: row`).

---

## خاصیت‌های این جلسه

### 1. `display: flex`
چیدمان flex را فعال می‌کند.

```css
.container {
  display: flex;
}
```

### 2. `justify-content`
آیتم‌ها را روی **محور اصلی (افقی)** تراز می‌کند.

```css
justify-content: center; /* وسط افقی */
```

مقادیر رایج دیگر:

| مقدار | معنی |
| --- | --- |
| `flex-start` | ابتدای محور |
| `flex-end` | انتهای محور |
| `center` | وسط |
| `space-between` | فاصله مساوی بین آیتم‌ها |
| `space-around` | فاصله اطراف هر آیتم |
| `space-evenly` | فاصله کاملاً یکنواخت |

### 3. `align-items`
آیتم‌ها را روی **محور عمودی (cross axis)** تراز می‌کند.

```css
align-items: center; /* وسط عمودی */
```

مقادیر رایج:

| مقدار | معنی |
| --- | --- |
| `stretch` | کشیده شدن تا پر کردن ارتفاع (پیش‌فرض) |
| `flex-start` | بالا |
| `flex-end` | پایین |
| `center` | وسط عمودی |

در این مثال ارتفاع باکس‌ها متفاوت است (`100px`، `300px`، `200px`)؛ با `align-items: center` وسط عمودی container هم‌تراز می‌شوند.

### 4. `gap`
فاصله بین آیتم‌ها را مشخص می‌کند (ساده‌تر از margin بین هر کدام).

```css
gap: 24px;
```

---

## مثال کامل این جلسه

```css
.container {
  width: 1280px;
  height: 500px;
  display: flex;
  justify-content: center; /* وسط افقی */
  align-items: center;     /* وسط عمودی */
  gap: 24px;               /* فاصله بین باکس‌ها */
}
```

سه باکس رنگی داخلش:

| کلاس | رنگ | اندازه |
| --- | --- | --- |
| `.box1` | قرمز | `300 × 100` |
| `.box2` | آبی | `300 × 300` |
| `.box3` | سبز | `300 × 200` |

نتیجه: سه باکس کنار هم، با فاصله ۲۴ پیکسل، و هم در عرض و هم در ارتفاع container وسط‌چین شده‌اند.

---

## جمع‌بندی سریع

```text
display: flex        → فعال‌سازی Flexbox
justify-content      → تراز افقی (main axis)
align-items          → تراز عمودی (cross axis)
gap                  → فاصله بین آیتم‌ها
```

> مقادیر دیگری مثل `flex-direction`، `flex-wrap`، `flex-grow` و ... در جلسات بعدی قابل گسترش هستند.
