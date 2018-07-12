## API
Xây dựng API chỉ thực chất đang xây dựng một bộ URLs, phản hồi kết quả chỉ gồm data.Thông thường, có thể thực hiện những request kiểu này bằng trình duyệt, vì quá trình chuyển giao HTTP được thực hiện dưới dạng text, nên trình duyệt sẽ luôn tìm mọi cách để hiển thị phản hồi.
## Nguyên lý REST và cấu trúc dữ liệu RESTful
### REST (Representational State Transfer)
REST là một loạt hướng dẫn và dạng cấu trúc dùng cho việc chuyển đổi dữ liệu.

- Hệ thống hoạt động theo mô hình client-server, trong đó server là tập hợp các service nhỏ lắng nghe các request từ client. Với từng request khác nhau thì có thể một hoặc nhiều service xử lý.
Stateless (phi trạng thái). Đơn giản server và client không lưu trạng thái của nhau -> mỗi request lên server thì client phải đóng gói thông tin đầy đủ để thằng server hiểu được. Điều này giúp hệ thống của bạn dễ phát triển,bảo trì, mở rộng vì không cần tốn công CRUD trạng thái của client . Hệ thống phát triển theo hướng này có ưu điểm nhưng cũng có khuyết điểm là gia tăng lượng thông tin cần truyền tải giữa client và server.
- Khả năng caching : Các response có thể lấy ra từ cache. Bằng cách cache các response , server giảm tải việc xử lý request, còn client cũng nhận được thông tin nhanh hơn. Ở đây ta đặt 1 thằng cache vào giữa : client- cache- server.
- Chuẩn hóa các interface : Đây là một trong những đặc tính quan trọng của hệ thống REST. Bằng cách tạo ra các quy ước chuẩn để giao tiếp giữa các thành phần trong hệ thống, bạn đã đơn giản hóa việc client có thể tương tác với server. Các quy ước này áp dụng cho toàn bộ các service giúp cho người sử dụng hệ thống của bạn dễ dụng hơn. Dễ hiểu hơn trên hệ thống bạn đặt ra 1 chuẩn API để người dùng dù là mobile, web đều có thể kết nối vào được. Hệ thống REST có yếu điểm ở đây vì khi chuẩn hóa rồi ta không thế tối ưu từng kết nối.-
- Phân lớp hệ thống : trong hệ thống REST bạn chia tách các thành phần hệ thống theo từng lớp, mỗi lớp chỉ sử dụng lớp ở dưới nó và giao tiếp với lớp ở ngay trên nó mà thôi. Điều này giúp bạn giảm độ phức tạp của hệ thống,giúp các thành phần tách biệt nhau từ đó dễ dàng mở rộng từng thành phần 

Resources (Tài nguyên)

Hệ thống REST trước hệt phải tuân thủ các ràng buộc ở trên. Đi vào chi tiết, hệ thống REST tập trung vào việc xử lý các tài nguyên. Resource là bất cứ cái gì mà bạn có thể gọi tên được ( một video, ảnh, trang web, báo cáo thời tiết .v.v). Các tài nguyên này giúp ta định nghĩa được các services trong hệ thống, kiểu thông tin mà nó trả về, và hành vi xử lý thông tin của nó.

Các đặc tính mô tả một tài nguyên :

- Nhiều cách thức hiển thị : dữ liệu bạn nhận được có thể ở nhiều dạng ( binary, JSON, XML .v.v) dữ liệu này đại diện cho 1 tài nguyên xác định.
- Nhận diện rõ ràng : Mỗi URL tại một thời điểm chỉ trả về 1 tài nguyên xác định.
- Dữ liệu mô tả (metadata) : Kiểu nội dung( Content-type), lần cập nhâp mới .v.v
- Dữ liệu điều khiển : Is-modifiable-since, cache-control.

Thông thương nhắc đến REST là nhắc đến HTTP vì hệ thống REST thường sử dụng giao thức HTTP. 

