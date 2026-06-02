# ĐÁP ÁN PHỎNG VẤN - BÀI 2 (Dành cho giáo viên)

> File này chứa **đề + đáp án mong đợi** cho từng câu, dùng để chấm/đối chiếu khi phỏng vấn.
> 📄 Bản chỉ có câu hỏi (đưa cho học sinh): [`cau-hoi-phong-van.md`](./cau-hoi-phong-van.md)

---

## PHẦN 1: HTML — Block, Inline, Thẻ tiện dụng, Semantic

**Q1.** Sự khác biệt giữa phần tử Block và Inline là gì? Cho ví dụ mỗi loại 3 thẻ.

> **Đáp án mong đợi:** Block chiếm toàn bộ chiều ngang, tự xuống dòng mới (div, p, h1). Inline chỉ chiếm vừa đủ nội dung, không tự xuống dòng (span, a, strong).

---

**Q2.** `<div>` và `<span>` khác nhau như thế nào? Khi nào dùng thẻ nào?

> **Đáp án:** `<div>` là block, dùng để nhóm nhiều phần tử. `<span>` là inline, dùng để đánh dấu một phần nhỏ trong dòng text.

---

**Q3.** Giải thích sự khác biệt giữa `<hr>` và `<br>`. Mỗi thẻ dùng trong tình huống nào?

> **Đáp án:** `<hr>` tạo đường kẻ ngang phân tách nội dung. `<br>` tạo ngắt dòng trong văn bản. `<hr>` để phân chia phần/mục, `<br>` để xuống dòng trong cùng một đoạn.

---

**Q4.** Viết HTML hiển thị công thức "H₂SO₄" và "x²+y²=z²" bằng thẻ phù hợp.

> **Đáp án:**
> ```html
> <p>H<sub>2</sub>SO<sub>4</sub></p>
> <p>x<sup>2</sup>+y<sup>2</sup>=z<sup>2</sup></p>
> ```

---

**Q5.** Semantic HTML là gì? Tại sao nên dùng `<header>`, `<nav>`, `<main>` thay vì chỉ dùng `<div>`?

> **Đáp án:** Semantic HTML là dùng thẻ có ý nghĩa rõ ràng. Lợi ích: SEO tốt hơn, accessibility cho screen reader, code dễ đọc/bảo trì hơn.

---

**Q6.** Hãy kể tên 5 thẻ semantic HTML và giải thích vai trò của từng thẻ.

> **Đáp án:** `<header>` (đầu trang), `<nav>` (điều hướng), `<main>` (nội dung chính), `<article>` (bài viết độc lập), `<footer>` (chân trang).

---

**Q7.** Cho đoạn code sau, kết quả hiển thị sẽ như thế nào? Hai `<span>` nằm cùng dòng hay khác dòng?

```html
<span>Xin chào</span>
<span>Việt Nam</span>
```

> **Đáp án:** Hai span nằm **cùng một dòng** vì span là inline.

---

**Q8.** Cho đoạn code sau, hai đoạn text nằm cùng dòng hay khác dòng?

```html
<div>Phần 1</div>
<div>Phần 2</div>
```

> **Đáp án:** Hai div nằm **khác dòng** vì div là block, tự xuống dòng.

---

## PHẦN 2: CSS CƠ BẢN & SELECTOR

**Q9.** CSS là viết tắt của gì? Vai trò chính của CSS là gì?

> **Đáp án:** Cascading Style Sheets. Vai trò: mô tả cách trình bày/hiển thị của HTML, tách biệt nội dung và giao diện.

---

**Q10.** Cú pháp cơ bản của CSS gồm những phần nào? Viết ví dụ.

> **Đáp án:** `selector { property: value; }`. Ví dụ: `h1 { color: blue; font-size: 24px; }`

---

**Q11.** So sánh Inline CSS và Internal CSS. Ưu nhược điểm của mỗi loại?

> **Đáp án:**
> - Inline: viết trong thuộc tính style của thẻ, ưu tiên cao nhất, khó bảo trì.
> - Internal: viết trong thẻ `<style>` trong `<head>`, tách biệt hơn, tái sử dụng selector được.

---

**Q12.** Universal Selector (`*`) dùng để làm gì? Cho ví dụ thực tế.

> **Đáp án:** Chọn tất cả phần tử trên trang. Thường dùng để reset CSS: `* { margin: 0; padding: 0; box-sizing: border-box; }`

---

**Q13.** ID Selector khác Element Selector như thế nào? Cái nào có độ ưu tiên cao hơn?

> **Đáp án:** ID Selector dùng `#` chọn phần tử theo id (duy nhất). Element Selector chọn tất cả phần tử cùng tên thẻ. ID Selector có độ ưu tiên cao hơn.

---

**Q14.** Có mấy cách viết màu trong CSS? Kể tên và cho ví dụ.

> **Đáp án:** 4 cách: tên màu (`red`), hex (`#FF0000`), RGB (`rgb(255,0,0)`), RGBA (`rgba(255,0,0,0.5)`).

---

**Q15.** Đoạn code sau, thẻ `<h1>` sẽ có màu gì? Giải thích tại sao.

```html
<style>
  h1 { color: blue; }
  #title { color: green; }
</style>
<h1 id="title" style="color: red;">Hello</h1>
```

> **Đáp án:** Màu **đỏ** (red) vì Inline CSS có độ ưu tiên cao nhất > ID Selector > Element Selector.

---

**Q16.** Có lỗi gì trong đoạn code CSS sau?

```html
<style>
  #my title {
    color: blue;
  }
</style>
<h1 id="my title">Hello</h1>
```

> **Đáp án:** ID không được chứa khoảng trắng. `"my title"` là tên ID không hợp lệ. Nên dùng `"my-title"`.

---

## PHẦN 3: BOX MODEL

**Q17.** Box Model gồm những lớp nào? Liệt kê từ trong ra ngoài.

> **Đáp án:** Content → Padding → Border → Margin.

---

**Q18.** Sự khác biệt giữa Padding và Margin là gì?

> **Đáp án:** Padding là khoảng đệm **bên trong** (giữa content và border). Margin là khoảng cách **bên ngoài** (giữa border và phần tử khác).

---

**Q19.** Giải thích `margin: 10px 20px 30px 40px;` — mỗi giá trị tương ứng với cạnh nào?

> **Đáp án:** Theo chiều kim đồng hồ: trên (10px) → phải (20px) → dưới (30px) → trái (40px).

---

**Q20.** Làm thế nào để căn giữa một phần tử block theo chiều ngang bằng CSS?

> **Đáp án:** Dùng `margin: 0 auto;` (phần tử cần có width cụ thể).

---

**Q21.** Margin Collapse là gì? Cho ví dụ.

> **Đáp án:** Khi hai block nằm dọc, margin chúng gộp lại lấy giá trị lớn hơn. Ví dụ: box1 margin-bottom 30px + box2 margin-top 20px = khoảng cách thực 30px (không phải 50px).

---

**Q22.** Giải thích sự khác biệt giữa `display: block`, `display: inline`, và `display: inline-block`.

> **Đáp án:**
> - `block`: chiếm toàn dòng, set width/height được.
> - `inline`: vừa đủ nội dung, KHÔNG set width/height được.
> - `inline-block`: nằm cùng dòng nhưng CÓ THỂ set width/height.

---

**Q23.** `display: none;` khác gì với việc set `width: 0; height: 0;`?

> **Đáp án:** `display: none` ẩn phần tử hoàn toàn, không chiếm không gian. Set width/height = 0 vẫn chiếm padding, border, margin.

---

**Q24.** Cho CSS sau, tổng chiều rộng thực tế của .box là bao nhiêu pixel?

```css
.box {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
  margin: 10px;
}
```

> **Đáp án:** Content(200) + Padding(20×2) + Border(5×2) = 200 + 40 + 10 = **250px** chiều rộng visible. Margin không tính vào kích thước phần tử nhưng tạo khoảng cách 10px mỗi bên.

---

**Q25.** Nếu thêm `box-sizing: border-box;` vào .box ở câu Q24, tổng chiều rộng visible sẽ là bao nhiêu?

> **Đáp án:** **200px**. Vì `border-box` bao gồm padding + border trong width. Content sẽ tự co lại: 200 - 40 - 10 = 150px.

---

**Q26.** Giải thích sự khác nhau giữa `em` và `rem`. Nếu `html { font-size: 16px; }` và `.parent { font-size: 20px; }`, thì `1.5em` và `1.5rem` bên trong `.parent` bằng bao nhiêu px?

> **Đáp án:** `1.5em` = 1.5 × 20px = **30px** (dựa theo parent). `1.5rem` = 1.5 × 16px = **24px** (dựa theo root html).

---

**Q27.** Làm thế nào để tạo một hình tròn bằng CSS?

> **Đáp án:** Set width = height và `border-radius: 50%`. Ví dụ:
> ```css
> .circle { width: 100px; height: 100px; border-radius: 50%; }
> ```

---

## PHẦN 4: CÂU HỎI TỔNG HỢP NÂNG CAO

**Q28.** Nhìn vào đoạn code sau và chỉ ra tất cả các lỗi/vấn đề:

```html
<div>
  <span style="width: 200px; height: 100px; background: red;">
    Tôi rộng 200px
  </span>
</div>
```

> **Đáp án:** `<span>` là inline, không thể set `width` và `height`. Cần thêm `display: inline-block;` hoặc `display: block;` để width/height có hiệu lực.

---

**Q29.** Viết CSS để tạo một thẻ (card) với: chiều rộng 300px, viền 1px xám, bo góc 8px, padding 16px, căn giữa trang.

> **Đáp án:**
> ```css
> .card {
>   width: 300px;
>   border: 1px solid gray;
>   border-radius: 8px;
>   padding: 16px;
>   margin: 0 auto;
> }
> ```

---

**Q30.** Tại sao nên dùng `* { box-sizing: border-box; }` ở đầu file CSS?

> **Đáp án:** Vì mặc định CSS dùng `content-box` (width chỉ tính content, padding + border cộng thêm, gây khó tính toán). `border-box` giúp width bao gồm cả padding + border, dễ kiểm soát kích thước hơn.
