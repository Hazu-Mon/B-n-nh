TAM GIÁC VÀNG — GIAO DIỆN THAM KHẢO FIGMA

1. XEM NHANH
Giải nén toàn bộ ZIP, mở index.html bằng Chrome/Edge. Hoặc mở thư mục bằng VS Code và dùng Live Server nếu đã cài extension đó.
Các trang dùng hash (#products, #rental, #print, #cart) và chạy trong trình duyệt.

2. GẮN VÀO DJANGO HIỆN CÓ
Sao lưu dự án trước. Chép templates/home.html vào thư mục templates của dự án, chép nội dung static vào static. Nếu đã có file trùng tên, đổi tên hoặc hợp nhất, không ghi đè mù quáng.
Trong settings.py, cập nhật TEMPLATES[0]["DIRS"] = [BASE_DIR / "templates"].
Đặt STATIC_URL = "static/" và STATICFILES_DIRS = [BASE_DIR / "static"].
Trong urls.py dự án, import: from django.views.generic import TemplateView
Thêm vào urlpatterns nếu chưa có đường dẫn rỗng:
path("", TemplateView.as_view(template_name="home.html"), name="home"),
Giữ nguyên các đường dẫn khác. Chạy python manage.py runserver từ thư mục có manage.py bằng môi trường đã cài Django.

3. PHẠM VI
Đây là bộ giao diện, không phải backend hoàn chỉnh. Có điều hướng, tìm kiếm, lọc, giỏ hàng localStorage và biểu mẫu demo. Không đăng nhập, thanh toán, kiểm tra lịch trống hoặc lưu đơn thật. Form không gửi ảnh/thông tin lên máy chủ.
Chưa có mã nguồn dự án của nhóm nên chưa tích hợp models/views/URLs nghiệp vụ.
Tên, mô tả và giá sản phẩm là dữ liệu minh họa, không được xác minh. Không có nội dung đăng nhập Messenger của ảnh tham chiếu.

4. HÌNH ẢNH
Ảnh minh họa được trích từ ảnh tổng thể Figma người dùng gửi, có độ phân giải thấp. Để rõ nét, xuất riêng ảnh gốc từ Figma và thay trong static/images (giữ tên hoặc cập nhật đường dẫn).
Bố cục được dựng theo ảnh tham chiếu; không phải bản sao chính xác từng pixel. Chữ quá nhỏ được thay bằng nội dung mẫu.
Chỉnh sản phẩm trong static/js/app.js; màu sắc trong static/css/style.css.
