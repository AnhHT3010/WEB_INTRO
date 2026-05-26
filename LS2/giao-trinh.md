# BÀI 2: HTML (tiếp), CSS & Box Model

---

## PHẦN 1: GIỚI THIỆU HTML (tiếp)

### 1.1 Thẻ Block và Inline

Trong HTML, mọi phần tử đều thuộc một trong hai loại hiển thị chính: **Block** và **Inline**.

#### Thẻ Block

- Chiếm **toàn bộ chiều ngang** của phần tử cha (tự động xuống dòng).
- Luôn bắt đầu trên **một dòng mới**.
- Có thể chứa các phần tử Block và Inline khác bên trong.
- Ví dụ: `<div>`, `<h1>`-`<h6>`, `<p>`, `<ul>`, `<ol>`, `<li>`, `<table>`, `<form>`...

#### Thẻ Inline

- Chỉ chiếm **đúng phần không gian cần thiết** cho nội dung bên trong.
- **Không tự xuống dòng**, nằm cùng dòng với các phần tử khác.
- Thường nằm bên trong một phần tử Block.
- Ví dụ: `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<br>`, `<input>`...

#### Thẻ `<div>` (Block)

`<div>` là thẻ **block-level** dùng để **nhóm các phần tử lại với nhau**, tạo thành một khối. Bản thân `<div>` không có ý nghĩa ngữ nghĩa, nó chỉ là một "hộp chứa" (container).

```html
<div>
  <h2>Tiêu đề bài viết</h2>
  <p>Đây là nội dung bài viết.</p>
</div>

<div>
  <h2>Bài viết khác</h2>
  <p>Nội dung bài viết khác.</p>
</div>
```

**Khi nào dùng `<div>`?**
- Khi cần nhóm các phần tử để áp dụng CSS chung.
- Khi cần tạo layout (bố cục) cho trang web.
- Khi không có thẻ semantic nào phù hợp hơn.

#### Thẻ `<span>` (Inline)

`<span>` là thẻ **inline-level** dùng để **đánh dấu một phần nhỏ** trong dòng văn bản. Tương tự `<div>`, nó không có ý nghĩa ngữ nghĩa.

```html
<p>Giá sản phẩm: <span style="color: red;">500.000đ</span></p>
<p>Trạng thái: <span style="color: green;">Còn hàng</span></p>
```

**Khi nào dùng `<span>`?**
- Khi cần style một phần nhỏ của văn bản.
- Khi cần đánh dấu một đoạn text để JavaScript xử lý.

#### So sánh `<div>` và `<span>`

| Đặc điểm | `<div>` | `<span>` |
|-----------|---------|----------|
| Loại | Block | Inline |
| Xuống dòng | Có | Không |
| Chiều rộng | Toàn bộ dòng | Vừa đủ nội dung |
| Mục đích | Nhóm nhiều phần tử | Đánh dấu text nhỏ |

---

### 1.2 Các thẻ tiện dụng: `<hr>`, `<br>`, `<sup>`, `<sub>`

#### Thẻ `<hr>` - Horizontal Rule (Đường kẻ ngang)

Tạo một **đường kẻ ngang** để phân tách nội dung. Đây là thẻ tự đóng (self-closing).

```html
<h2>Phần 1: Giới thiệu</h2>
<p>Nội dung phần 1...</p>
<hr>
<h2>Phần 2: Nội dung chính</h2>
<p>Nội dung phần 2...</p>
```

#### Thẻ `<br>` - Line Break (Xuống dòng)

Tạo một **ngắt dòng** trong văn bản. Cũng là thẻ tự đóng.

```html
<p>
  Nguyễn Văn A<br>
  123 Đường ABC<br>
  Quận 1, TP.HCM
</p>
```

> ⚠️ **Lưu ý:** Không nên lạm dụng `<br>` để tạo khoảng cách. Hãy dùng CSS margin/padding thay thế.

#### Thẻ `<sup>` - Superscript (Chỉ số trên)

Hiển thị văn bản ở vị trí **phía trên** và nhỏ hơn bình thường.

```html
<p>Công thức: E = mc<sup>2</sup></p>
<p>Ngày 20<sup>th</sup> tháng 5</p>
<p>Chú thích<sup>[1]</sup></p>
```

**Kết quả:** E = mc² | Ngày 20ᵗʰ tháng 5

#### Thẻ `<sub>` - Subscript (Chỉ số dưới)

Hiển thị văn bản ở vị trí **phía dưới** và nhỏ hơn bình thường.

```html
<p>Công thức nước: H<sub>2</sub>O</p>
<p>Carbon dioxide: CO<sub>2</sub></p>
```

**Kết quả:** H₂O | CO₂

---

### 1.3 Semantic Markup (Đánh dấu ngữ nghĩa)

#### Semantic là gì?

**Semantic HTML** là việc sử dụng các thẻ HTML có **ý nghĩa rõ ràng** về nội dung bên trong, thay vì chỉ dùng `<div>` và `<span>` cho mọi thứ.

#### Tại sao cần Semantic?

1. **SEO tốt hơn:** Công cụ tìm kiếm hiểu cấu trúc trang web.
2. **Accessibility:** Trình đọc màn hình (screen reader) hỗ trợ người khiếm thị tốt hơn.
3. **Dễ bảo trì:** Code dễ đọc và hiểu hơn.

#### Các thẻ Semantic quan trọng

| Thẻ | Ý nghĩa |
|-----|---------|
| `<header>` | Phần đầu trang hoặc đầu một section |
| `<nav>` | Thanh điều hướng (navigation) |
| `<main>` | Nội dung chính của trang |
| `<section>` | Một phần/mục trong trang |
| `<article>` | Một bài viết độc lập |
| `<aside>` | Nội dung phụ, sidebar |
| `<footer>` | Phần chân trang |
| `<figure>` | Hình ảnh kèm chú thích |
| `<figcaption>` | Chú thích cho `<figure>` |

#### So sánh: Non-Semantic vs Semantic

**❌ Non-Semantic (khó hiểu):**
```html
<div id="header">
  <div id="nav">...</div>
</div>
<div id="main">
  <div class="article">...</div>
  <div class="sidebar">...</div>
</div>
<div id="footer">...</div>
```

**✅ Semantic (dễ hiểu):**
```html
<header>
  <nav>...</nav>
</header>
<main>
  <article>...</article>
  <aside>...</aside>
</main>
<footer>...</footer>
```

#### Ví dụ thực tế

```html
<header>
  <h1>Blog Công Nghệ</h1>
  <nav>
    <a href="#home">Trang chủ</a>
    <a href="#about">Giới thiệu</a>
    <a href="#contact">Liên hệ</a>
  </nav>
</header>

<main>
  <article>
    <h2>iPhone 18 Pro - Đánh giá chi tiết</h2>
    <p>Nội dung bài viết...</p>
    <figure>
      <img src="iphone18.jpg" alt="iPhone 18 Pro">
      <figcaption>Hình ảnh iPhone 18 Pro</figcaption>
    </figure>
  </article>

  <aside>
    <h3>Bài viết liên quan</h3>
    <ul>
      <li><a href="#">Samsung Galaxy S26</a></li>
      <li><a href="#">Google Pixel 10</a></li>
    </ul>
  </aside>
</main>

<footer>
  <p>&copy; 2026 Blog Công Nghệ. All rights reserved.</p>
</footer>
```

---

## PHẦN 2: LÀM QUEN VỚI CSS VÀ CSS SELECTOR

### 2.1 CSS là gì? Vai trò của CSS

**CSS** (Cascading Style Sheets) là ngôn ngữ dùng để **mô tả cách trình bày** (giao diện) của tài liệu HTML.

#### Vai trò của CSS

- **Tách biệt nội dung và giao diện:** HTML lo cấu trúc, CSS lo hiển thị.
- **Tùy chỉnh giao diện:** Màu sắc, font chữ, kích thước, bố cục...
- **Responsive Design:** Giao diện thích ứng với nhiều thiết bị.
- **Tái sử dụng:** Một file CSS có thể áp dụng cho nhiều trang HTML.

#### Cú pháp CSS cơ bản

```css
selector {
  property: value;
  property: value;
}
```

**Ví dụ:**
```css
h1 {
  color: blue;
  font-size: 24px;
}
```

- **Selector:** Chọn phần tử HTML cần style (`h1`).
- **Property:** Thuộc tính cần thay đổi (`color`, `font-size`).
- **Value:** Giá trị của thuộc tính (`blue`, `24px`).

---

### 2.2 Inline CSS

Inline CSS là cách viết CSS **trực tiếp trong thẻ HTML** bằng thuộc tính `style`.

```html
<h1 style="color: red; font-size: 32px;">Tiêu đề đỏ</h1>
<p style="background-color: yellow; padding: 10px;">Đoạn văn nền vàng</p>
```

**Ưu điểm:**
- Nhanh, tiện cho test nhanh.
- Độ ưu tiên cao nhất.

**Nhược điểm:**
- Khó bảo trì, code lộn xộn.
- Không tái sử dụng được.
- Trộn lẫn HTML và CSS.

> ⚠️ **Trong thực tế**, hạn chế dùng Inline CSS. Chỉ dùng khi thật sự cần thiết.

---

### 2.3 Các thuộc tính style cơ bản với văn bản

| Thuộc tính | Mô tả | Ví dụ |
|------------|--------|-------|
| `color` | Màu chữ | `color: red;` hoặc `color: #FF0000;` |
| `font-size` | Kích thước chữ | `font-size: 16px;` |
| `font-weight` | Độ đậm | `font-weight: bold;` hoặc `font-weight: 700;` |
| `font-style` | Kiểu chữ | `font-style: italic;` |
| `font-family` | Font chữ | `font-family: Arial, sans-serif;` |
| `text-align` | Căn chỉnh văn bản | `text-align: center;` |
| `text-decoration` | Trang trí chữ | `text-decoration: underline;` |
| `text-transform` | Biến đổi chữ | `text-transform: uppercase;` |
| `line-height` | Chiều cao dòng | `line-height: 1.5;` |
| `letter-spacing` | Khoảng cách chữ cái | `letter-spacing: 2px;` |
| `background-color` | Màu nền | `background-color: #f0f0f0;` |

#### Cách viết màu trong CSS

```css
/* Tên màu */
color: red;
color: blue;

/* Hex (thập lục phân) */
color: #FF0000;   /* đỏ */
color: #00FF00;   /* xanh lá */
color: #0000FF;   /* xanh dương */

/* RGB */
color: rgb(255, 0, 0);     /* đỏ */

/* RGBA (có độ trong suốt) */
color: rgba(255, 0, 0, 0.5);  /* đỏ, 50% trong suốt */
```

---

### 2.4 Internal CSS và CSS Selector

#### Internal CSS

Internal CSS viết trong thẻ `<style>` đặt trong `<head>`.

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    h1 {
      color: navy;
      text-align: center;
    }
    p {
      font-size: 16px;
      line-height: 1.6;
    }
  </style>
</head>
<body>
  <h1>Tiêu đề</h1>
  <p>Nội dung văn bản.</p>
</body>
</html>
```

**Ưu điểm so với Inline CSS:**
- Tách biệt CSS khỏi HTML.
- Có thể tái sử dụng selector cho nhiều phần tử.
- Dễ bảo trì hơn.

---

### 2.5 Universal Selector và Element Selector

#### Universal Selector (`*`)

Chọn **tất cả** các phần tử trên trang.

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

> Thường dùng để **reset** style mặc định của trình duyệt.

#### Element Selector (Type Selector)

Chọn tất cả phần tử có **cùng tên thẻ**.

```css
/* Tất cả thẻ h1 sẽ có màu xanh */
h1 {
  color: blue;
}

/* Tất cả thẻ p sẽ có font-size 16px */
p {
  font-size: 16px;
}

/* Tất cả thẻ a sẽ không có gạch chân */
a {
  text-decoration: none;
}
```

---

### 2.6 ID Selector

Chọn phần tử dựa trên thuộc tính `id`. Mỗi `id` là **duy nhất** trên trang (không được trùng).

**Cú pháp:** Dùng dấu `#` trước tên id.

```html
<style>
  #main-title {
    color: darkblue;
    font-size: 36px;
    text-align: center;
  }

  #warning-text {
    color: red;
    font-weight: bold;
  }
</style>

<h1 id="main-title">Chào mừng đến Website</h1>
<p id="warning-text">Cảnh báo: Trang web đang bảo trì!</p>
```

**Quy tắc đặt tên ID:**
- Bắt đầu bằng chữ cái, không bắt đầu bằng số.
- Không chứa khoảng trắng.
- Phân biệt hoa thường (`myId` ≠ `myid`).
- Nên đặt tên có ý nghĩa: `main-title`, `nav-bar`, `footer-info`.

#### Độ ưu tiên (Specificity) - Giới thiệu sơ bộ

Khi nhiều CSS rule cùng áp dụng cho một phần tử, trình duyệt ưu tiên theo thứ tự:

1. **Inline CSS** (cao nhất)
2. **ID Selector** (`#id`)
3. **Element Selector** (`h1`, `p`...)
4. **Universal Selector** (`*`) (thấp nhất)

---

## PHẦN 3: BOX MODEL

### 3.1 Box Model là gì?

Trong CSS, mọi phần tử HTML đều được coi là một **hộp chữ nhật** (box). Box Model mô tả cấu trúc của hộp này gồm 4 lớp từ trong ra ngoài:

```
┌──────────────────────────────────────┐
│              MARGIN                  │
│  ┌────────────────────────────────┐  │
│  │           BORDER               │  │
│  │  ┌──────────────────────────┐  │  │
│  │  │        PADDING           │  │  │
│  │  │  ┌──────────────────┐    │  │  │
│  │  │  │    CONTENT       │    │  │  │
│  │  │  │  (width x height)│    │  │  │
│  │  │  └──────────────────┘    │  │  │
│  │  └──────────────────────────┘  │  │
│  └────────────────────────────────┘  │
└──────────────────────────────────────┘
```

- **Content:** Nội dung thực tế (text, hình ảnh...).
- **Padding:** Khoảng đệm giữa content và border.
- **Border:** Viền bao quanh padding.
- **Margin:** Khoảng cách bên ngoài border, tạo khoảng cách với phần tử khác.

---

### 3.2 Width và Height

Thiết lập **chiều rộng** và **chiều cao** cho phần content.

```css
.box {
  width: 300px;
  height: 200px;
}
```

**Các giá trị thường dùng:**

| Giá trị | Mô tả |
|---------|--------|
| `px` | Pixel, giá trị cố định |
| `%` | Phần trăm so với phần tử cha |
| `auto` | Trình duyệt tự tính |
| `max-width` | Chiều rộng tối đa |
| `min-width` | Chiều rộng tối thiểu |
| `100vh` | 100% chiều cao viewport |
| `100vw` | 100% chiều rộng viewport |

```css
.container {
  width: 80%;         /* 80% phần tử cha */
  max-width: 1200px;  /* Không quá 1200px */
  min-height: 500px;  /* Ít nhất 500px cao */
}
```

---

### 3.3 Border và Border-Radius

#### Border (Viền)

```css
.box {
  /* Cú pháp viết gọn: width style color */
  border: 2px solid black;
}
```

**Các kiểu border-style:**
- `solid` – Đường liền
- `dashed` – Đường đứt nét
- `dotted` – Đường chấm
- `double` – Đường đôi
- `none` – Không viền

**Tùy chỉnh từng cạnh:**
```css
.box {
  border-top: 3px solid red;
  border-bottom: 1px dashed blue;
  border-left: 2px dotted green;
  border-right: none;
}
```

#### Border-Radius (Bo góc)

```css
.box {
  border-radius: 10px;          /* Bo đều 4 góc */
}

.circle {
  width: 100px;
  height: 100px;
  border-radius: 50%;           /* Tạo hình tròn */
}

.custom {
  /* top-left | top-right | bottom-right | bottom-left */
  border-radius: 10px 20px 30px 40px;
}
```

---

### 3.4 Padding và Margin

#### Padding (Khoảng đệm bên trong)

```css
.box {
  padding: 20px;                /* Đều 4 phía */
  padding: 10px 20px;           /* trên-dưới | trái-phải */
  padding: 10px 20px 30px;      /* trên | trái-phải | dưới */
  padding: 10px 20px 30px 40px; /* trên | phải | dưới | trái (theo chiều kim đồng hồ) */
}

/* Hoặc từng phía riêng */
.box {
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 30px;
  padding-left: 40px;
}
```

#### Margin (Khoảng cách bên ngoài)

Cú pháp giống padding:

```css
.box {
  margin: 20px;                 /* Đều 4 phía */
  margin: 10px 20px;            /* trên-dưới | trái-phải */
  margin: 0 auto;               /* Căn giữa theo chiều ngang */
}
```

**Trick hay:** `margin: 0 auto;` dùng để **căn giữa** phần tử block theo chiều ngang (phần tử cần có `width` cụ thể).

#### Margin Collapse

Khi hai phần tử block nằm chồng nhau theo chiều dọc, margin của chúng sẽ **gộp lại** (collapse), lấy giá trị lớn hơn thay vì cộng dồn.

```css
.box1 { margin-bottom: 30px; }
.box2 { margin-top: 20px; }
/* Khoảng cách thực tế = 30px (không phải 50px) */
```

---

### 3.5 Thuộc tính Display

Thuộc tính `display` quyết định cách phần tử hiển thị trên trang.

| Giá trị | Mô tả |
|---------|--------|
| `block` | Hiển thị dạng block (chiếm toàn bộ dòng) |
| `inline` | Hiển thị dạng inline (vừa đủ nội dung) |
| `inline-block` | Kết hợp: nằm trên cùng dòng nhưng có thể set width/height |
| `none` | Ẩn phần tử hoàn toàn |

```css
/* Biến span thành block */
span.block {
  display: block;
  width: 200px;
  height: 50px;
  background-color: lightblue;
}

/* Biến div thành inline */
div.inline {
  display: inline;
}

/* inline-block: nằm cùng dòng nhưng có width/height */
.badge {
  display: inline-block;
  width: 100px;
  height: 30px;
  background-color: orange;
  text-align: center;
}

/* Ẩn phần tử */
.hidden {
  display: none;
}
```

**So sánh Block vs Inline vs Inline-block:**

| Đặc điểm | block | inline | inline-block |
|-----------|-------|--------|--------------|
| Xuống dòng mới | ✅ | ❌ | ❌ |
| Set width/height | ✅ | ❌ | ✅ |
| Set margin/padding | ✅ | Chỉ trái-phải | ✅ |
| Chiếm toàn dòng | ✅ | ❌ | ❌ |

---

### 3.6 Đơn vị kích thước trong CSS

#### Đơn vị tuyệt đối (Absolute)

| Đơn vị | Mô tả |
|--------|--------|
| `px` | Pixel - đơn vị phổ biến nhất, kích thước cố định |

#### Đơn vị tương đối (Relative)

| Đơn vị | Mô tả | Ví dụ |
|--------|--------|-------|
| `%` | Phần trăm so với phần tử cha | `width: 50%;` → 50% chiều rộng cha |
| `em` | Tương đối so với font-size của phần tử hiện tại | `padding: 1em;` |
| `rem` | Tương đối so với font-size của `<html>` (root) | `font-size: 1.5rem;` |
| `vw` | 1% chiều rộng viewport | `width: 100vw;` |
| `vh` | 1% chiều cao viewport | `height: 100vh;` |

#### So sánh `em` vs `rem`

```css
html { font-size: 16px; }  /* Mặc định */

.parent {
  font-size: 20px;
}

.child-em {
  font-size: 1.5em;    /* = 1.5 × 20px = 30px (dựa theo parent) */
}

.child-rem {
  font-size: 1.5rem;   /* = 1.5 × 16px = 24px (dựa theo root html) */
}
```

> 💡 **Tip:** Dùng `rem` cho font-size để dễ kiểm soát. Dùng `em` cho padding/margin khi muốn tỷ lệ theo font-size.

#### Box-sizing

Mặc định, `width` và `height` chỉ áp dụng cho **content**. Padding và border được cộng thêm vào.

```css
/* Mặc định: content-box */
.box {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
  /* Tổng chiều rộng thực tế = 300 + 20*2 + 5*2 = 350px */
}

/* border-box: width bao gồm cả padding + border */
.box {
  box-sizing: border-box;
  width: 300px;
  padding: 20px;
  border: 5px solid black;
  /* Tổng chiều rộng thực tế = 300px (content tự co lại) */
}
```

> 💡 **Best Practice:** Luôn dùng `box-sizing: border-box;` cho mọi phần tử:
> ```css
> * { box-sizing: border-box; }
> ```
