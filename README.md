PHẦN 1: PHÂN TÍCH LỖI & TEST CASES (README.md)

1. Nguyên nhân lỗi kỹ thuật
   Lỗi 1 (startsWith("MED-")): Chuỗi cleanAppointmentCode chứa chữ thường "med-nhi-1024". Hàm .startsWith() phân biệt hoa/thường nên kiểm tra với "MED-" bị trả về false.

   Lỗi 2 (slice(4, 7)): Lấy dữ liệu khi chưa viết hoa làm chuyên khoa bị in thường (nhi thay vì NHI).

   Lỗi 3 (slice(8, 12)): Kiểm tra trạng thái và cắt chuỗi khi chưa chuẩn hóa đồng bộ gây sai lệch kết quả đầu ra.

2. Danh sách Test Cases
   TC01 - Mã tiêu chuẩn:

Đầu vào: rawAppointmentCode = " med-nhi-1024 ", cleanPatientName = " nguyễn văn an "

Kết quả sai: Trạng thái hợp lệ = false, Chuyên khoa = nhi

Kết quả đúng: Bệnh nhân = NGUYỄN VĂN AN, Chuyên khoa = NHI, STT = 1024, Hợp lệ = true

TC02 - Chuyên khoa khác:

Đầu vào: rawAppointmentCode = " med-san-2025 ", cleanPatientName = " trần thị bình "

Kết quả sai: Trạng thái hợp lệ = false, Chuyên khoa = san

Kết quả đúng: Bệnh nhân = TRẦN THỊ BÌNH, Chuyên khoa = SAN, STT = 2025, Hợp lệ = true

TC03 - Mã sai tiền tố:

Đầu vào: rawAppointmentCode = " hos-nhi-1024 ", cleanPatientName = " lê văn c "

Kết quả sai: Xử lý trạng thái không nhất quán

Kết quả đúng: Bệnh nhân = LÊ VĂN C, Chuyên khoa = NHI, STT = 1024, Hợp lệ = false
