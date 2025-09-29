# API Endpoints

## 1. Authentication

### Đăng nhập
**POST** `/api/login`

- Headers:
  - Content-Type: application/json

- Request:
```json
{
  "email": "user@example.com",
  "password": "secret"
}
```

- Response (200 OK):
```json
{
  "token": "jwt_token_here",
  "token_type": "Bearer",
  "expires_in": 3600,
  "user": {
    "id": 1,
    "name": "Nguyễn Văn A",
    "email": "user@example.com"
  }
}
```

- Errors:
  - 401 Unauthorized – Sai email hoặc mật khẩu
  - 422 Validation Error – Thiếu trường bắt buộc

### Đăng xuất
**POST** `/api/logout`

- Headers:
  - Authorization: Bearer <token>

- Response (200 OK):
```json
{
  "message": "Logged out successfully"
}
```

- Errors:
  - 401 Unauthorized – Token không hợp lệ

## 2. Permissions

### Lấy danh sách Permission
**GET** `/api/permissions`

- Headers:
  - Authorization: Bearer <token>

- Response (200 OK):
```json
[
  {
    "id": 1,
    "name": "View Users",
    "slug": "view_users",
    "description": "Cho phép xem danh sách người dùng"
  },
  {
    "id": 2,
    "name": "Edit Users",
    "slug": "edit_users",
    "description": "Cho phép chỉnh sửa người dùng"
  }
]
```

... (truncated for brevity in repo copy)
