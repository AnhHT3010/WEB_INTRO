# CÂU HỎI PHỎNG VẤN - BÀI 3

> Bộ câu hỏi kiểm tra mức độ hiểu bài của học sinh sau LS3 (CSS Flexbox).
> 📄 **Đáp án dành cho giáo viên** nằm ở file riêng: [`dap-an-phong-van.md`](./dap-an-phong-van.md)

---

## PHẦN 1: KHÁI NIỆM CƠ BẢN

### Câu hỏi lý thuyết

**Q1.** Flexbox là gì? Nó là mô hình layout mấy chiều?

---

**Q2.** Phân biệt Flex Container và Flex Item. Làm thế nào để biến một phần tử thành flex container?

---

**Q3.** Main Axis (trục chính) và Cross Axis (trục phụ) là gì? Hướng của main axis do thuộc tính nào quyết định?

---

**Q4.** Khi đặt `display: flex`, các flex item mặc định xếp ngang hay dọc?

---

**Q5.** Chỉ những phần tử nào trong container trở thành flex item?

---

## PHẦN 2: THUỘC TÍNH CONTAINER

### Câu hỏi lý thuyết

**Q6.** `flex-direction` có những giá trị nào? Mỗi giá trị làm gì?

---

**Q7.** `justify-content` căn theo trục nào? Kể tên ít nhất 4 giá trị.

---

**Q8.** `align-items` căn theo trục nào? Giá trị mặc định là gì?

---

**Q9.** Phân biệt `justify-content: space-between`, `space-around`, và `space-evenly`.

---

**Q10.** `flex-wrap` dùng để làm gì? Giá trị mặc định là gì?

---

**Q11.** Phân biệt `align-items` và `align-content`. Khi nào `align-content` mới có tác dụng?

---

**Q12.** `gap` trong Flexbox dùng để làm gì? Nó thay thế cho cách làm cũ nào?

---

### Câu hỏi tình huống

**Q13.** Viết CSS để căn giữa một phần tử cả theo chiều ngang lẫn chiều dọc bằng Flexbox.

---

**Q14.** Cho `flex-direction: column;`. Lúc này `justify-content: center` sẽ căn giữa theo chiều nào (ngang hay dọc)? Vì sao?

---

## PHẦN 3: THUỘC TÍNH ITEM

### Câu hỏi lý thuyết

**Q15.** `flex-grow` dùng để làm gì? Giá trị mặc định là bao nhiêu?

---

**Q16.** `flex-shrink` dùng để làm gì?

---

**Q17.** `flex-basis` khác `width` như thế nào?

---

**Q18.** `flex: 1;` là viết tắt của những giá trị nào?

---

**Q19.** `order` dùng để làm gì? Giá trị mặc định của mọi item là bao nhiêu?

---

**Q20.** `align-self` khác `align-items` ở điểm nào?

---

### Câu hỏi tình huống

**Q21.** Cho 3 item, item giữa có `flex-grow: 2`, hai item còn lại `flex-grow: 1`. Khoảng trống dư được chia như thế nào?

---

**Q22.** Muốn một sidebar rộng cố định 250px (không co giãn) còn phần nội dung chiếm hết phần còn lại, viết `flex` cho mỗi phần như thế nào?

---

## PHẦN 4: ỨNG DỤNG & TỔNG HỢP

**Q23.** Viết CSS cho một navbar: logo bên trái, menu bên phải, căn giữa theo chiều dọc.

---

**Q24.** Làm thế nào để các thẻ card tự động xuống dòng khi màn hình hẹp? Viết CSS cho container và card.

---

**Q25.** Cho đoạn code sau, ba box hiển thị thế nào (vị trí trên trục chính)?

```css
.container {
  display: flex;
  justify-content: flex-end;
}
```

---

**Q26.** Có gì sai/thiếu trong đoạn code muốn căn giữa theo chiều dọc sau? Vì sao chưa thấy hiệu quả?

```css
.container {
  display: flex;
  align-items: center;
}
```
