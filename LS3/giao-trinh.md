# BÀI 3: CSS FLEXBOX (Flexible Box Layout)

---

## PHẦN 1: GIỚI THIỆU FLEXBOX

### 1.1 Flexbox là gì?

**Flexbox** (Flexible Box Layout) là một **mô hình bố cục (layout) một chiều** trong CSS, giúp **sắp xếp, căn chỉnh và phân phối khoảng trống** giữa các phần tử bên trong một khối chứa (container) — kể cả khi kích thước của chúng chưa biết trước hoặc thay đổi.

Trước khi có Flexbox, để căn giữa hay chia cột người ta phải dùng `float`, `inline-block`, `table`... rất rắc rối. Flexbox sinh ra để giải quyết những việc đó một cách **đơn giản và mạnh mẽ**.

> 💡 **"Một chiều"** nghĩa là Flexbox sắp xếp các phần tử theo **một hàng (row)** hoặc **một cột (column)** tại một thời điểm. Nếu cần bố cục 2 chiều (cả hàng và cột) thì dùng **CSS Grid** (học sau).

### 1.2 Vì sao cần Flexbox?

- **Căn giữa dễ dàng:** căn giữa theo chiều ngang VÀ dọc chỉ với 2 dòng CSS.
- **Chia cột linh hoạt:** các cột tự co giãn lấp đầy khoảng trống.
- **Tự động xuống dòng:** khi màn hình nhỏ, phần tử có thể tự wrap.
- **Không cần tính toán thủ công** như khi dùng `float`.

### 1.3 Flex Container và Flex Item

Để dùng Flexbox, ta cần phân biệt 2 khái niệm:

- **Flex Container** (khối cha): phần tử được set `display: flex;`.
- **Flex Item** (các con): các phần tử **con trực tiếp** nằm bên trong container.

```html
<div class="container">
  <!-- container = flex container -->
  <div class="item">1</div>
  <!-- mỗi item = flex item -->
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex; /* Kích hoạt Flexbox */
}
```

> ⚠️ Chỉ các **con trực tiếp** mới trở thành flex item. Cháu (con của con) thì không bị ảnh hưởng trực tiếp.

### 1.4 Trục chính (Main Axis) và Trục phụ (Cross Axis)

Đây là khái niệm **quan trọng nhất** của Flexbox. Mọi thuộc tính căn chỉnh đều dựa vào 2 trục này:

- **Main Axis (trục chính):** trục mà các item được xếp theo. Hướng của nó do `flex-direction` quyết định.
- **Cross Axis (trục phụ):** trục **vuông góc** với trục chính.

```
flex-direction: row (mặc định)
   ┌──────────────────────────────►  Main Axis (ngang)
   │  ┌─────┐ ┌─────┐ ┌─────┐
   │  │  1  │ │  2  │ │  3  │
   │  └─────┘ └─────┘ └─────┘
   ▼
 Cross Axis (dọc)
```

```
flex-direction: column
   ┌──────►  Cross Axis (ngang)
   │  ┌─────┐
   │  │  1  │
   │  ├─────┤
   │  │  2  │
   │  ├─────┤
   │  │  3  │
   │  └─────┘
   ▼
 Main Axis (dọc)
```

> 💡 **Ghi nhớ:** `justify-content` luôn căn theo **main axis**, `align-items` luôn căn theo **cross axis**. Khi đổi `flex-direction`, hai trục này đổi chỗ cho nhau!

---

## PHẦN 2: THUỘC TÍNH CỦA FLEX CONTAINER

Các thuộc tính dưới đây đặt trên **container** (phần tử có `display: flex`).

### 2.1 `display: flex`

Biến một phần tử thành flex container. Mặc định các item sẽ:

- Nằm trên **cùng một hàng** (`flex-direction: row`).
- **Không** tự xuống dòng (`flex-wrap: nowrap`).
- Cao bằng nhau (kéo dãn theo cross axis — `align-items: stretch`).

```css
.container {
  display: flex;
}
```

> Có cả `display: inline-flex;` — container hoạt động như flex nhưng bản thân nó là inline (nằm cùng dòng với phần tử khác).

### 2.2 `flex-direction` — Hướng trục chính

Quyết định các item xếp theo hướng nào.

| Giá trị          | Mô tả                                    |
| ---------------- | ---------------------------------------- |
| `row` (mặc định) | Xếp ngang, từ trái → phải                |
| `row-reverse`    | Xếp ngang, từ phải → trái                |
| `column`         | Xếp dọc, từ trên → xuống                 |
| `column-reverse` | Xếp dọc, từ dưới → lên                   |

```css
.container {
  display: flex;
  flex-direction: row; /* hoặc column, row-reverse, column-reverse */
}
```

### 2.3 `flex-wrap` — Cho phép xuống dòng

Mặc định các item bị **ép** vào một dòng (co lại nếu cần). `flex-wrap` cho phép chúng xuống dòng khi không đủ chỗ.

| Giá trị             | Mô tả                              |
| ------------------- | ---------------------------------- |
| `nowrap` (mặc định) | Tất cả trên một dòng (không wrap)  |
| `wrap`              | Xuống dòng khi thiếu chỗ           |
| `wrap-reverse`      | Xuống dòng nhưng theo chiều ngược  |

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

> 💡 Có thể viết gọn `flex-direction` + `flex-wrap` thành `flex-flow`:
>
> ```css
> flex-flow: row wrap;
> ```

### 2.4 `justify-content` — Căn theo TRỤC CHÍNH

Phân phối khoảng trống **dọc theo main axis**.

| Giá trị          | Mô tả                                                  |
| ---------------- | ------------------------------------------------------ |
| `flex-start`     | Dồn về đầu trục (mặc định)                             |
| `flex-end`       | Dồn về cuối trục                                       |
| `center`         | Căn giữa                                               |
| `space-between`  | Cách đều, item đầu/cuối sát mép                        |
| `space-around`   | Cách đều, mỗi item có khoảng trống 2 bên               |
| `space-evenly`   | Cách đều hoàn toàn (mọi khoảng trống bằng nhau)        |

```css
.container {
  display: flex;
  justify-content: center; /* căn giữa theo chiều ngang (khi row) */
}
```

```
flex-start:     [1][2][3]............
center:         ......[1][2][3]......
flex-end:       ............[1][2][3]
space-between:  [1].....[2].....[3]
space-around:   ..[1]...[2]...[3]..
space-evenly:   ...[1]...[2]...[3]...
```

### 2.5 `align-items` — Căn theo TRỤC PHỤ

Căn các item **dọc theo cross axis**.

| Giá trị             | Mô tả                                          |
| ------------------- | ---------------------------------------------- |
| `stretch` (mặc định)| Kéo dãn item lấp đầy cross axis                |
| `flex-start`        | Dồn về đầu trục phụ                            |
| `flex-end`          | Dồn về cuối trục phụ                           |
| `center`            | Căn giữa theo trục phụ                         |
| `baseline`          | Căn theo đường baseline của chữ                |

```css
.container {
  display: flex;
  align-items: center; /* căn giữa theo chiều dọc (khi row) */
}
```

#### ⭐ Công thức CĂN GIỮA hoàn hảo (cả ngang lẫn dọc)

```css
.container {
  display: flex;
  justify-content: center; /* giữa theo main axis */
  align-items: center; /* giữa theo cross axis */
  height: 100vh; /* cần có chiều cao để thấy căn giữa dọc */
}
```

### 2.6 `align-content` — Căn các DÒNG (khi có wrap)

Chỉ có tác dụng khi có **nhiều dòng** (đã `flex-wrap: wrap` và item tràn ≥ 2 dòng). Nó căn chỉnh **khoảng cách giữa các dòng** theo cross axis.

| Giá trị         | Mô tả                          |
| --------------- | ------------------------------ |
| `flex-start`    | Các dòng dồn lên đầu           |
| `center`        | Các dòng dồn vào giữa          |
| `space-between` | Các dòng cách đều              |
| `stretch`       | Kéo dãn các dòng (mặc định)    |

> ⚠️ Phân biệt: `align-items` căn item **trong một dòng**; `align-content` căn **giữa các dòng** với nhau.

### 2.7 `gap` — Khoảng cách giữa các item

Cách hiện đại và gọn nhất để tạo khoảng cách giữa các flex item (thay cho việc dùng `margin`).

```css
.container {
  display: flex;
  gap: 20px; /* khoảng cách đều giữa các item */
  /* hoặc tách riêng: */
  gap: 10px 20px; /* row-gap | column-gap */
}
```

---

## PHẦN 3: THUỘC TÍNH CỦA FLEX ITEM

Các thuộc tính dưới đây đặt trên **item** (phần tử con bên trong container).

### 3.1 `flex-grow` — Độ "phình to"

Quy định item được **chiếm bao nhiêu phần** khoảng trống còn dư. Giá trị là một con số (tỉ lệ).

```css
.item {
  flex-grow: 0; /* mặc định: KHÔNG phình to */
}
.item-special {
  flex-grow: 1; /* chiếm hết khoảng trống dư */
}
```

Nếu 3 item có `flex-grow: 1` → chia đều khoảng trống. Nếu một item có `flex-grow: 2`, nó nhận gấp đôi phần dư so với item `flex-grow: 1`.

### 3.2 `flex-shrink` — Độ "co lại"

Quy định item được phép **co lại bao nhiêu** khi thiếu chỗ.

```css
.item {
  flex-shrink: 1; /* mặc định: được phép co lại */
}
.item-fixed {
  flex-shrink: 0; /* KHÔNG co lại, giữ nguyên kích thước */
}
```

### 3.3 `flex-basis` — Kích thước cơ sở

Kích thước **ban đầu** của item dọc theo main axis (trước khi grow/shrink). Giống `width` (khi row) nhưng ưu tiên cao hơn trong Flexbox.

```css
.item {
  flex-basis: 200px; /* rộng cơ sở 200px */
  flex-basis: auto; /* mặc định: dựa theo nội dung/width */
}
```

### 3.4 `flex` — Viết gọn (shorthand)

Gộp `flex-grow`, `flex-shrink`, `flex-basis` vào một dòng.

```css
.item {
  /* flex: grow shrink basis; */
  flex: 1 1 0; /* grow=1, shrink=1, basis=0 → chia đều tuyệt đối */
}
```

**Các giá trị thường gặp:**

| Cú pháp        | Ý nghĩa                                                  |
| -------------- | -------------------------------------------------------- |
| `flex: 1;`     | = `1 1 0` → các item chia đều khoảng trống               |
| `flex: auto;`  | = `1 1 auto` → co giãn dựa theo nội dung                 |
| `flex: none;`  | = `0 0 auto` → kích thước cố định, không co giãn         |

```css
/* 3 cột bằng nhau */
.column {
  flex: 1;
}
```

### 3.5 `align-self` — Tự căn riêng một item

Ghi đè `align-items` cho **riêng một item** trên cross axis.

```css
.item-special {
  align-self: flex-end; /* riêng item này dồn xuống cuối trục phụ */
}
```

| Giá trị      | Mô tả                                  |
| ------------ | -------------------------------------- |
| `auto`       | Theo `align-items` của container (mặc định) |
| `flex-start` | Đầu trục phụ                            |
| `center`     | Giữa trục phụ                           |
| `flex-end`   | Cuối trục phụ                           |
| `stretch`    | Kéo dãn                                 |

### 3.6 `order` — Thứ tự hiển thị

Thay đổi **thứ tự sắp xếp** mà không cần sửa HTML. Mặc định mọi item có `order: 0`. Số nhỏ hiển thị trước.

```css
.item-1 {
  order: 2;
}
.item-2 {
  order: 1;
} /* item-2 sẽ hiển thị TRƯỚC item-1 */
```

> 💡 `order` rất hữu ích cho responsive: đổi thứ tự cột trên mobile mà không sửa HTML.

---

## PHẦN 4: ỨNG DỤNG THỰC TẾ

### 4.1 Căn giữa tuyệt đối một phần tử

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
```

### 4.2 Navigation Bar (Navbar)

Logo bên trái, menu bên phải:

```css
.navbar {
  display: flex;
  justify-content: space-between; /* đẩy logo và menu ra 2 đầu */
  align-items: center;
  padding: 16px 32px;
}
.menu {
  display: flex;
  gap: 24px; /* khoảng cách giữa các mục menu */
}
```

### 4.3 Bố cục nhiều cột bằng nhau

```css
.row {
  display: flex;
  gap: 20px;
}
.col {
  flex: 1; /* mỗi cột chia đều */
}
```

### 4.4 Card Layout tự xuống dòng (Responsive)

```css
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
.card {
  flex: 1 1 250px; /* tối thiểu ~250px, tự co giãn & wrap */
}
```

### 4.5 Sidebar Layout

Sidebar cố định, nội dung chính co giãn:

```css
.layout {
  display: flex;
}
.sidebar {
  flex: 0 0 250px; /* cố định 250px, không co giãn */
}
.main-content {
  flex: 1; /* chiếm hết phần còn lại */
}
```

---

## PHẦN 5: TỔNG KẾT NHANH (Cheat Sheet)

**Đặt trên CONTAINER:**

| Thuộc tính        | Tác dụng                                  |
| ----------------- | ----------------------------------------- |
| `display: flex`   | Kích hoạt Flexbox                         |
| `flex-direction`  | Hướng trục chính (row/column)             |
| `flex-wrap`       | Cho phép xuống dòng                       |
| `justify-content` | Căn theo **trục chính**                   |
| `align-items`     | Căn theo **trục phụ**                     |
| `align-content`   | Căn giữa các dòng (khi wrap nhiều dòng)   |
| `gap`             | Khoảng cách giữa các item                 |

**Đặt trên ITEM:**

| Thuộc tính     | Tác dụng                              |
| -------------- | ------------------------------------- |
| `flex-grow`    | Độ phình to                           |
| `flex-shrink`  | Độ co lại                             |
| `flex-basis`   | Kích thước cơ sở                      |
| `flex`         | Viết gọn grow/shrink/basis            |
| `align-self`   | Tự căn riêng trên trục phụ            |
| `order`        | Thứ tự hiển thị                       |

> 💡 **Mẹo học:** Luyện tập trực quan với trò chơi [Flexbox Froggy](https://flexboxfroggy.com/) — vừa chơi vừa nhớ thuộc tính.
