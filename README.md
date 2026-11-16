# BÀI TẬP: CHUẨN HÓA DỮ LIỆU SINH VIÊN BẰNG CREATE

## 1. Prompt theo CREATE

```text
C (Context): Bạn là chuyên viên quản lý dữ liệu sinh viên của phòng đào tạo.

R (Role): Đóng vai trò chuyên gia chuẩn hóa và xử lý dữ liệu.

E (Expectation): Đọc dữ liệu, chuẩn hóa họ tên, email và trạng thái sinh viên, sau đó chuyển thành JSON.

A (Action):
- Tách dữ liệu thành 3 trường: fullName, email, status.
- Status chỉ được nhận: "đang học", "bảo lưu", "nghỉ học".
- Nếu không xác định được, sử dụng "UNKNOWN".
- Không tự ý bổ sung thông tin hoặc làm mất bản ghi.
- Kiểm tra số lượng bản ghi trước khi xuất kết quả.

T (Tone): Chính xác, rõ ràng, nghiêm túc.

E (End Result): Chỉ xuất JSON hợp lệ, không Markdown, không giải thích bên ngoài JSON.

Dữ liệu đầu vào:
Nguyễn Văn An - an.nguyen@gmail.com - đang học
Trần Thị Bình - binhtt@gmail.com - bảo lưu
Lê Hoàng Nam - nam.le@gmail.com - đang học
Phạm Minh Đức - duc.pham@gmail.com - nghỉ học

Cấu trúc đầu ra:
{
  "students": [
    {
      "fullName": "Tên sinh viên",
      "email": "Email",
      "status": "Trạng thái"
    }
  ],
  "totalRecords": 4
}
```

## 2. Kết quả JSON (Markdown)

```json
{
  "students": [
    {
      "fullName": "Nguyễn Văn An",
      "email": "an.nguyen@gmail.com",
      "status": "đang học"
    },
    {
      "fullName": "Trần Thị Bình",
      "email": "binhtt@gmail.com",
      "status": "bảo lưu"
    },
    {
      "fullName": "Lê Hoàng Nam",
      "email": "nam.le@gmail.com",
      "status": "đang học"
    },
    {
      "fullName": "Phạm Minh Đức",
      "email": "duc.pham@gmail.com",
      "status": "nghỉ học"
    }
  ],
  "totalRecords": 4
}
```
