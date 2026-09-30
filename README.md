# Nhật ký công việc

Trang web một file (`index.html`): nhật ký, việc cần làm (chưa làm / cần sắp xếp / đã hoàn thành),
lọc theo tuần/tháng, đính ảnh. Đăng nhập bằng email, dữ liệu riêng tư và đồng bộ qua Firebase.

## Thiết lập Firebase (miễn phí, khoảng 10 phút)

1. Vào https://console.firebase.google.com, tạo dự án mới (tắt Google Analytics cũng được).
2. **Build → Authentication → Get started → Sign-in method**: bật **Email/Password**.
3. **Authentication → Settings → Authorized domains**: thêm `<tên-tài-khoản>.github.io`.
4. **Build → Firestore Database → Create database** (chọn vùng gần bạn, ví dụ `asia-southeast1`).
5. Trong Firestore, mở tab **Rules**, dán nội dung file `firestore.rules`, bấm **Publish**.
6. **Project settings (⚙) → General → Your apps → Web (</>)**: đăng ký app, sao chép `apiKey`,
   `authDomain`, `projectId`, `appId`.
7. Mở `index.html`, tìm dòng `var CFG={...}` và thay các giá trị `DÁN_...` bằng thông tin vừa sao chép.
8. Tải `index.html`, `README.md`, `firestore.rules` lên repo GitHub, bật **Settings → Pages**
   (Deploy from a branch → `main` → `/ (root)`).
9. Mở trang, bấm **Tạo tài khoản** và đăng ký bằng email của bạn.
10. Khuyên làm: sau khi tạo xong tài khoản, vào **Authentication → Settings → User actions**
    và tắt **Enable create (sign-up)** để không ai khác tạo được tài khoản trong dự án của bạn.

`apiKey` của Firebase không phải bí mật. Việc bảo vệ dữ liệu do quy tắc Firestore ở bước 5 đảm nhiệm.
