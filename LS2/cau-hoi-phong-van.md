# CÂU HỎI PHỎNG VẤN - BÀI 2

> Bộ câu hỏi kiểm tra mức độ hiểu bài của học sinh sau LS2 (HTML bổ sung, CSS & Selector, Box Model).
> 📄 **Đáp án dành cho giáo viên** nằm ở file riêng: [`dap-an-phong-van.md`](./dap-an-phong-van.md)

---

## PHẦN 1: HTML — Block, Inline, Thẻ tiện dụng, Semantic

### Câu hỏi lý thuyết

**Q1.** Sự khác biệt giữa phần tử Block và Inline là gì? Cho ví dụ mỗi loại 3 thẻ.

---

**Q2.** `<div>` và `<span>` khác nhau như thế nào? Khi nào dùng thẻ nào?

---

**Q3.** Giải thích sự khác biệt giữa `<hr>` và `<br>`. Mỗi thẻ dùng trong tình huống nào?

---

**Q4.** Viết HTML hiển thị công thức "H₂SO₄" và "x²+y²=z²" bằng thẻ phù hợp.

---

**Q5.** Semantic HTML là gì? Tại sao nên dùng `<header>`, `<nav>`, `<main>` thay vì chỉ dùng `<div>`?

---

**Q6.** Hãy kể tên 5 thẻ semantic HTML và giải thích vai trò của từng thẻ.

---

### Câu hỏi tình huống

**Q7.** Cho đoạn code sau, kết quả hiển thị sẽ như thế nào? Hai `<span>` nằm cùng dòng hay khác dòng?

```html
<span>Xin chào</span>
<span>Việt Nam</span>
```

---

**Q8.** Cho đoạn code sau, hai đoạn text nằm cùng dòng hay khác dòng?

```html
<div>Phần 1</div>
<div>Phần 2</div>
```

---

## PHẦN 2: CSS CƠ BẢN & SELECTOR

### Câu hỏi lý thuyết

**Q9.** CSS là viết tắt của gì? Vai trò chính của CSS là gì?

---

**Q10.** Cú pháp cơ bản của CSS gồm những phần nào? Viết ví dụ.

---

**Q11.** So sánh Inline CSS và Internal CSS. Ưu nhược điểm của mỗi loại?

---

**Q12.** Universal Selector (`*`) dùng để làm gì? Cho ví dụ thực tế.

---

**Q13.** ID Selector khác Element Selector như thế nào? Cái nào có độ ưu tiên cao hơn?

---

**Q14.** Có mấy cách viết màu trong CSS? Kể tên và cho ví dụ.

---

### Câu hỏi tình huống

**Q15.** Đoạn code sau, thẻ `<h1>` sẽ có màu gì? Giải thích tại sao.

```html
<style>
  h1 { color: blue; }
  #title { color: green; }
</style>
<h1 id="title" style="color: red;">Hello</h1>
```

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

---

## PHẦN 3: BOX MODEL

### Câu hỏi lý thuyết

**Q17.** Box Model gồm những lớp nào? Liệt kê từ trong ra ngoài.

---

**Q18.** Sự khác biệt giữa Padding và Margin là gì?

---

**Q19.** Giải thích `margin: 10px 20px 30px 40px;` — mỗi giá trị tương ứng với cạnh nào?

---

**Q20.** Làm thế nào để căn giữa một phần tử block theo chiều ngang bằng CSS?

---

**Q21.** Margin Collapse là gì? Cho ví dụ.

---

**Q22.** Giải thích sự khác biệt giữa `display: block`, `display: inline`, và `display: inline-block`.

---

**Q23.** `display: none;` khác gì với việc set `width: 0; height: 0;`?

---

### Câu hỏi tính toán

**Q24.** Cho CSS sau, tổng chiều rộng thực tế của .box là bao nhiêu pixel?

```css
.box {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
  margin: 10px;
}
```

---

**Q25.** Nếu thêm `box-sizing: border-box;` vào .box ở câu Q24, tổng chiều rộng visible sẽ là bao nhiêu?

---

**Q26.** Giải thích sự khác nhau giữa `em` và `rem`. Nếu `html { font-size: 16px; }` và `.parent { font-size: 20px; }`, thì `1.5em` và `1.5rem` bên trong `.parent` bằng bao nhiêu px?

---

**Q27.** Làm thế nào để tạo một hình tròn bằng CSS?

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

---

**Q29.** Viết CSS để tạo một thẻ (card) với: chiều rộng 300px, viền 1px xám, bo góc 8px, padding 16px, căn giữa trang.

---

**Q30.** Tại sao nên dùng `* { box-sizing: border-box; }` ở đầu file CSS?
