# Hướng Dẫn Sử Dụng Thiệp Cưới HTML & Tạo Link Cá Nhân Hoá

Bộ mã nguồn thiệp cưới trực tuyến tĩnh (Static HTML/CSS/JS) với cơ chế hiển thị tên khách mời tự động theo từng người gửi.

---

## 📁 Cấu Trúc Thư Mục
* `index.html`: Giao diện thiệp cưới chính (Gồm bì thư mở đầu, nhạc cưới lãng mạn, cánh hoa rơi, đếm ngược, lịch trình hôn lễ, album ảnh và hộp mừng cưới).
* `generator.html`: Công cụ dành riêng cho Cô dâu / Chú rể để dán danh sách bạn bè và tự động sinh hàng loạt link + tin nhắn mẫu gửi Zalo/Messenger.
* `README.md`: Hướng dẫn sử dụng và triển khai online.

---

## 💡 Cơ Chế Hoạt Động (Giải pháp kỹ thuật)
Không cần cơ sở dữ liệu hay máy chủ backend phức tạp, trang web sử dụng **Tham số URL (Query Parameters)**.

Ví dụ đường dẫn sau khi đưa lên mạng:
* Mặc định (không có tên): `https://your-domain.com/` -> Hiện: **Quý Khách**
* Gửi cho bạn Tuấn Anh: `https://your-domain.com/?to=Tuấn+Anh&prefix=Bạn&plus=1` -> Hiện: **Bạn Tuấn Anh & Người thương**
* Gửi cho Gia đình Bác Hùng: `https://your-domain.com/?to=Bác+Hùng&prefix=Gia+đình` -> Hiện: **Gia đình Bác Hùng**

Khi khách bấm vào link, mã JavaScript trong file `index.html` tự động đọc tham số trên thanh địa chỉ và điền vào đúng vị trí trên thiệp.

---

## 🚀 Cách Đưa Thiệp Lên Mạng Hoàn Toàn Miễn Phí (Deploy)

Bạn có thể chọn 1 trong các cách cực nhanh sau:

### Cách 1: Sử dụng Vercel (Khuyên dùng - Nhanh nhất & Đẹp nhất)
1. Truy cập [vercel.com](https://vercel.com) và đăng ký/đăng nhập.
2. Cài đặt tiện ích Vercel CLI hoặc kéo thả toàn bộ thư mục `thiepcuoi` vào dashboard Vercel.
3. Sau 30 giây, bạn sẽ nhận được một đường link miễn phí dạng: `https://thiep-cuoi-cua-ban.vercel.app`.

### Cách 2: Sử dụng GitHub Pages
1. Tạo một repository mới trên GitHub (ví dụ: `thiepcuoi`).
2. Tải toàn bộ file (`index.html`, `generator.html`) lên repository đó.
3. Vào **Settings** > **Pages** > Chọn Branch `main` và bấm **Save**.
4. Link thiệp cưới của bạn sẽ có dạng: `https://tentaikhoan.github.io/thiepcuoi/`.

### Cách 3: Sử dụng Netlify Drop
1. Vào [app.netlify.com/drop](https://app.netlify.com/drop).
2. Kéo thả trực tiếp cả thư mục `thiepcuoi` vào trình duyệt.
3. Bạn sẽ nhận được link ngay lập tức mà không cần gõ lệnh nào.

---

## 🛠️ Hướng Dẫn Tùy Chỉnh Thông Tin
Mở file `index.html` bằng bất kỳ trình soạn thảo code hoặc Notepad để sửa các thông tin sau:
1. **Tên Cô dâu & Chú rể**: Tìm và đổi `Hoàng Nam` và `Thảo Linh` thành tên của bạn.
2. **Ngày cưới**: 
   - Tìm đoạn `CHỦ NHẬT, 20 . 12 . 2026` để sửa ngày hiển thị.
   - Tìm đoạn JavaScript `weddingDate = new Date("2026-12-20T09:00:00")` để đồng hồ đếm ngược chạy đúng ngày giờ của bạn.
3. **Địa điểm & Link Google Maps**: Thay địa chỉ nhà trai, nhà gái, trung tâm tiệc cưới và đường link Google Maps chỉ đường.
4. **Ảnh & Nhạc**:
   - Thay các link ảnh trong thẻ `<img>` bằng ảnh cưới thật của hai bạn.
   - Thay link bài hát trong thẻ `<audio id="wedding-audio">` nếu muốn đổi bài hát yêu thích.
5. **Số tài khoản & Mã QR mừng cưới**: Thay đổi số tài khoản ngân hàng và link mã QR tương ứng của hai bạn.
