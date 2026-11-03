# PicoCTF
### 1. Irish-Name-Repo 1
- Khi mở chall lên, ta được giao diện như thế này và thử thách yêu cầu chúng ta phải đăng nhập được vào trang web để lấy được flag
<img width="1917" height="1090" alt="image" src="https://github.com/user-attachments/assets/479dbed0-652d-4186-ba26-e90174f3ed1a" />

- Khi vào trang đăng nhập ta được giao diện như thế này: <img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/b0670eda-2804-4004-9827-aab395dc14bf" />

- Sau khi kiếm tra source code của trang web và sử dụng devtools, ta không có được thêm bất cứ dữ liệu nào. Khi thử đăng nhập thì trang web trả lại cho tôi giao diện như thế này:<img width="1917" height="750" alt="image" src="https://github.com/user-attachments/assets/d4cf91d3-3f06-4aa4-8d3c-fa290526c00f" />

- Sau khi thử những cách cơ bản, tôi sẽ dùng burpsuite để kiểm tra xem sau khi đăng nhập thất bại, tôi có được thông tin gì hữu ích không và tôi đã xem được request mà mình đã gửi có thêm `debug=0` như thế này: <img width="1487" height="592" alt="image" src="https://github.com/user-attachments/assets/54c18238-19fe-4bf3-9f2c-e8b723551c8d" />

- Đây là tính năng hiển thị thông tin gỡ lỗi (debug mode) được lập trình sẵn trong mã nguồn, khi `debug=0` có vẻ như trang web đã ẩn đi các thông tin bên dưới và chỉ trả lại `login failed`
- Tôi nghĩ đây là điểm mà tôi có thể khai thác được. Bây giờ tôi sẽ dùng Repeater để sửa lại `debug` và sau khi làm xong, tôi nhận được response từ sever: <img width="751" height="443" alt="image" src="https://github.com/user-attachments/assets/254c21c1-25ad-4233-88bb-1e71314f8b6c" />
- Tôi đoán rằng đây là SQL INJECTION. Vì thế tôi sử dụng một vài payload cơ bản. Và sau một và payload, tôi đã tìm được flag qua payload `'OR'1'='1`: <img width="1492" height="812" alt="image" src="https://github.com/user-attachments/assets/f54d9262-30dc-4f54-b4a9-992633042a61" />


