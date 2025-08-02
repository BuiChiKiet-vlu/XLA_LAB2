# README

## Mục tiêu của bài
Bộ 4 chương trình xử lý ảnh này được xây dựng nhằm giúp sinh viên làm quen với các kỹ thuật biến đổi ảnh cơ bản và nâng cao trong lĩnh vực xử lý ảnh số. Thông qua việc xây dựng menu lựa chọn thao tác và áp dụng các thuật toán cụ thể, sinh viên có thể:

- Hiểu cách biểu diễn ảnh dưới dạng ma trận số.
- Thao tác với ảnh xám, ảnh màu RGB.
- Áp dụng các phép biến đổi điểm (point processing).
- Làm quen với xử lý ảnh trong miền tần số bằng biến đổi Fourier.
- Làm quen với các bộ lọc tuyến tính (Butterworth, Min/Max).

---

## Cấu trúc thư mục
```
├── exercise/ 
├── Cau 1_lab2.ipynb
├── Cau 2_lab2.ipynb
├── Cau 3_lab2.ipynb
├── Cau 4_Lab2.ipynb
└── README.md
```

---

## Thư viện được sử dụng
- `numpy`
- `math`
- `matplotlib`
- `PIL` 
- `scipy`
- `imageio.v2`

---

## Chi tiết từng bài
### Câu 1: `Image Transform Menu 1`
**Chức năng:** Cho phép người dùng chọn các phép biến đổi điểm cơ bản:
- `I`: **Image Inverse** – Đảo ngược pixel theo công thức: `s = 255 - r`
- `G`: **Gamma Correction** – Điều chỉnh độ sáng bằng công thức: `s = c * r^γ`
- `L`: **Log Transformation** – Làm nổi bật chi tiết tối: `s = c * log(1 + r)`
- `H`: **Histogram Equalization** – Cân bằng histogram để cải thiện độ tương phản
- `C`: **Contrast Stretching** – Giãn mức xám tuyến tính từ [a, b] về [0, 255]

Kết quả được hiển thị và lưu trong thư mục `output_cau1`.

---

### Câu 2: `Image Transform Menu 2`
**Chức năng:** Xử lý ảnh trong miền tần số:
- `F`: **Fast Fourier Transform (FFT)** – Tính phổ biên độ ảnh với công thức:
  - `F(u,v) = Σ Σ f(x,y) * e^(-j2π(ux/M + vy/N))`
- `L`: **Butterworth Lowpass Filter** – Bộ lọc thông thấp mềm:
  - `H(u,v) = 1 / (1 + (D(u,v)/D0)^(2n))`
- `H`: **Butterworth Highpass Filter** – Bộ lọc thông cao:
  - `H(u,v) = 1 / (1 + (D0/D(u,v))^(2n))`

> Trong đó: `D(u,v)` là khoảng cách từ điểm (u,v) đến tâm phổ, `D0` là tần số cắt, `n` là bậc lọc.

Ảnh kết quả được lưu vào `output_cau2`.

---

### Câu 3: `Image Transform Menu 3`
**Chức năng:**
- Ngẫu nhiên đổi thứ tự các kênh RGB (ví dụ BGR, GRB, v.v.)
- Chuyển ảnh thành grayscale
- Áp dụng ngẫu nhiên một phép biến đổi từ **Câu 1**

Kết quả được lưu trong thư mục `output_cau3`.

---

### Câu 4: `Image Transform Menu 4`
**Chức năng:**
- Ngẫu nhiên đổi thứ tự kênh RGB
- Chuyển sang grayscale
- Áp dụng ngẫu nhiên một trong các phép của **Câu 2**
  - Nếu chọn `Lowpass`: tiếp tục áp dụng **Min Filter** (lọc điểm tối nhất trong vùng lân cận)
  - Nếu chọn `Highpass`: tiếp tục áp dụng **Max Filter** (lọc điểm sáng nhất trong vùng lân cận)

Kết quả được lưu trong thư mục `output_cau4`.

---

## Người thực hiện
SVTH: Bùi Chí Kiệt - 2374802010255

## Giảng Viên Hướng Dẫn
TS. ĐỖ HỮU QUÂN
