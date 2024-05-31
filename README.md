

CHƯƠNG I. TỔNG QUAN VỀ RPC
1.1	 Giới thiệu
    
Remote Procedure Call (RPC) là thuật ngữ đã không còn xa lạ trong lĩnh vực lập trình. Đây là phương pháp được sử dụng nhiều trong việc giải quyết các vấn đề liên quan đến quá trình truyền tin trong những tiến trình riêng biệt. 
1.2	 RPC là gì?

 

Remote Procedure Call (RPC) được biết đến như một mô hình kỹ thuật mạng, là phương thức giao tiếp phần mềm mà chương trình nào đó dùng để yêu cầu dịch vụ từ chương trình khác trong máy tính. Nói một cách dễ hiểu hơn thì RPC chính là cơ chế giao tiếp phát sinh giữa hai tiến trình khác nhau. Nó áp dụng một mô hình chính là máy khách và máy chủ. Trong đó, máy chủ là chương trình cung cấp dịch vụ còn máy khách là chương trình được yêu cầu.
Mô hình kỹ thuật mạng RPC là một quá trình mang tính đồng bộ, theo đó chương trình yêu cầu bị tạm dừng đến thời điểm trả như mong muốn. Nhiều RPC được quyền hoạt động cùng lúc. Ngoài ra, ngôn ngữ PDL là loại ngôn ngữ dùng để mô tả giao diện lập trình API, dùng với phần mềm gọi thủ tục từ xa. IDL làm nhiệm vụ cung cấp cầu nối giữa máy chủ hai đầu là hệ điều hành (OS) và ngôn ngữ máy tính khác nhau.
1.3	 Cách thức hoạt động của RPC

Khi có một lệnh yêu cầu thủ tục từ xa xuất hiện, tham số thủ tục sẽ chuyển qua mạng đến môi trường thực thi. Sau khi hoàn thành thủ tục, kết quả nhận được chuyển trở lại môi trường yêu cầu. Trong RPC, các các bước được tiến hành như sau:
•	Máy khách gọi đến bộ phận Stub theo dạng cuộc gọi thủ tục cục bộ. Các tham số theo cách thông thường sẽ đẩy lên.
•	Máy khách tiến hành đóng gói các tham số thủ tục (marshalling) thành thông báo. Một cuộc gọi hệ thống sau đó được thực hiện để gửi đi thông báo. và thực hiện một cuộc gọi hệ thống để gửi thông báo.
•	Hệ điều hành cục bộ trên máy khách tiến hành gửi đi thông báo từ máy khách đến máy chủ từ xa.
•	Máy chủ bắt đầu giải nén tham số.
•	Máy chủ kết thúc thủ tục sẽ quay lại với gốc máy chủ. Bộ phận Stub chuyển đi thông điệp đến các lớp truyền tải trong máy tính.
•	Lớp truyền tải sau đó đưa thông báo kết quả tới lớp truyền tải khách và báo lại với gốc máy khách.
•	Máy khách có nhiệm vụ khai thác các tham số rồi trả về cho trình gọi.

1.4	 Phân loại RPC

Remote Procedure Call (RPC) gồm nhiều loại khác nhau. Mỗi loại sẽ mang chức năng, ý nghĩa riêng với cấu hình cụ thể như sau:
•	Máy khách thực hiện cuộc gọi và chỉ khi máy chủ trả lời thì mới được tiếp tục cuộc gọi.
•	Máy khách thực hiện cuộc gọi khi máy chủ không trả lời và bắt đầu quá trình xử lý mới.
•	Máy khách Remote Procedure Call (RPC) phát sóng, gửi được tin nhắn đến máy chủ và nhận lại các phản hồi.
•	Máy khách tiến hành cuộc gọi với máy chủ không chặn hoặc máy khách khác sau đó báo hiệu cuộc gọi hoàn tất bằng việc gọi thủ tục liên kết với máy khách.
•	Remote Procedure Call (RPC) cung cấp lớp truyền tải và lớp ứng dụng qua mô hình kết nối hệ thống mở gọi tắt là OSI. Sau đó, RPC phát triển một ứng dụng với nhiều chương trình trong cùng mạng một cách dễ dàng.
1.5	 Ưu và nhược điểm của RPC 

Remote Procedure Call (RPC) không phải lúc nào cũng hoàn hảo. Bên cạnh những ưu điểm nổi trội, mô hình này vẫn còn tồn đọng nhiều khuyết điểm chưa thể khắc phục được. Về mặt lợi, RPC cung cấp mang đến cho các nhà quản lý ứng dụng, các nhà phát triển:
•	Khả năng giao tiếp giữa khách hàng với máy chủ qua các cuộc gọi bằng ngôn ngữ cấp cao.
•	RCP dùng được trong môi trường phân tán và môi trường cục bộ.
•	Nó hỗ trợ các mô hình ẩn đi cơ chế truyền thông báo nội bộ.
•	RCP mang bản chất truyền đi thông điệp giao tiếp mạng đã bị ẩn khỏi người dùng.
•	Mô hình bỏ bớt các lớp giao thức để có thể cải thiện được hiệu suất.
Bên cạnh ưu điểm, bạn cũng cần phải nắm được các nhược điểm dưới đây:
•	Máy khách và máy chủ dùng môi trường thực thi khác nhau, việc sử dụng tài nguyên khá phức tạp. Hệ thống RPC không phù hợp để truyền dữ liệu trong mọi trường hợp.
•	RPC khi liên quan đến hệ thống liên lạc sẽ rất dễ bị hỏng.
•	Sẽ không có một tiêu chuẩn cố định nào dành cho RPC, nó được thực hiện theo nhiều cách khác nhau.
•	RPC được thực thi dựa trên các tương tác nên không mang đến sự linh hoạt nào cho cấu trúc phần cứng.
 
CHƯƠNG II . TỔNG QUAN VỀ NGÔN NGỮ NODEJS

2.1 NodeJS là gì?

NodeIS là một môi trường runtime chạy JavaScript đa nền tảng và có mã nguồn mở, được sử dụng để chạy các ứng dụng web bên ngoài trình duyệt của client. Nền tảng này được phát triển bởi Ryan Dahl vào năm 2009, được xem là một giải pháp hoàn hảo cho các ứng dụng sử dụng nhiều dữ liệu nhờ vào mô hình hướng sự kiện (event-driven) không đồng bộ.

2.2 Ưu và nhược điểm của Node.JS

Dưới đây là một số ưu và nhược điểm của Nodejs version bạn cần biết:
Ưu điểm:
•	IO hướng sự kiện không đồng bộ, cho phép xử lý nhiều yêu cầu đồng thời.
•	Sử dụng JavaScript – một ngôn ngữ lập trình dễ học.
•	Chia sẻ cùng code ở cả phía client và server.
•	NPM(Node Package Manager) và module Node đang ngày càng phát triển mạnh mẽ.
•	Cộng đồng hỗ trợ tích cực.
•	Cho phép stream các file có kích thước lớn.
Nhược điểm:
•	Không có khả năng mở rộng, vì vậy không thể tận dụng lợi thế mô hình đa lõi trong các phần cứng cấp server hiện nay.
•	Khó thao tác với cơ sử dữ liệu quan hệ.
•	Mỗi callback sẽ đi kèm với rất nhiều callback lồng nhau khác.
•	Cần có kiến thức tốt về JavaScript.
•	Không phù hợp với các tác vụ đòi hỏi nhiều CPU.


2.3 Những ứng dụng nên viết bằng Node.JS

NodeJS được sử dụng để xây dựng rất nhiều loại ứng dụng khác nhau, trong đó phổ biến nhất gồm có:
•	Ứng dụng trò chuyện trong thời gian thực: Nhờ vào cấu trúc không đồng bộ đơn luồng, Node.JS rất thích hợp cho mục đích xử lý giao tiếp trong thời gian thực. Nền tảng này có thể dễ dàng mở rộng quy mô và thường dùng để tạo ra các chatbot. Bên cạnh đó, các tính năng liên quan đến ứng dụng trò chuyện như: chat nhiều người, thông báo đẩy,… cũng có thể dễ dàng được bổ sung nhờ NodeJS.
•	Internet of Things (IoT): Các ứng dụng IoT thường bao gồm nhiều bộ cảm biến phức tạp để gửi những phần dữ liệu nhỏ. Node.JS là một lựa chọn lý tưởng để xử lý các yêu cầu đồng thời này với tốc độ cực nhanh.
•	Truyền dữ liệu: Netflix là một trong số những công ty lớn trên thế giới chuyên sử dụng Node.JS cho mục đích truyền dữ liệu. Sở dĩ vì đây là một nền tảng nhẹ và cực nhanh, đồng thời còn cung cấp một API chuyên dùng để stream.
•	Các SPA (Single-page application) phức tạp: Trong SPA, toàn bộ ứng dụng được load vào trong một trang duy nhất, do đó sẽ có một số request được thực hiện trong nền. Vòng lặp sự kiện (event loop) của Node.JS cho phép xử lý các request theo hướng non-blocking.
•	Các ứng dụng REST dựa trên API: JavaScript được sử dụng trong cả frontend lẫn backend của trang. Do đó một server có thể dễ dàng giao tiếp với frontend qua REST API bằng Node.js. Bên cạnh đó, Node.JS còn cung cấp nhiều package như Express.js hay Koa để việc xây dựng ứng dụng web trở nên dễ dàng hơn bao giờ hết.
 
CHƯƠNG III . TỔNG QUAN VỀ SOCKET.IO

3.1 Socket.IO là gì?

 
Socket.io là một module trong Node.js được phát triển vào năm 2010. Nó được phát triển để sử dụng các kết nối mở để tạo điều kiện giao tiếp thời gian thực, trả về giá trị thực ở tại thời điểm đó. Socket.io cho phép giao tiếp hai chiều giữa máy khách và máy chủ. Giao tiếp hai chiều được bật khi máy khách có Socket.io trong trình duyệt và máy chủ cũng đã tích hợp gói Socket.io.
Nó được sử dụng trong việc xây dựng các ứng dụng web real-time cần tốc độ phản hồi ngay lập tức như: chat, trực tiếp bóng đá,…. Socket.io xây dựng dựa trên Engine.IO, đầu tiên nó sẽ thiết lập một kết nối long-polling, sau đó cố gắng nâng cấp lên các kết nối khác tốt hơn giống như WebSocket.

3.2 Socket.IO hoạt động như thế nào?

 

Socket.IO sử dụng tính năng giao tiếp hai chiều để phát triển các ứng dụng trò chuyện. Các tin nhắn gửi về máy chủ sẽ được gửi trực tiếp cho máy khách mà không cần bất cứ yêu cầu trung gian nào.
3.3 Sử dụng Socket.IO để trò chuyện

Máy chủ
Đầu tiên hãy cài đặt node.js, sau đó sử dụng express để đơn giản hoá thiết lập ứng dụng.
Tạo folder mới với đoạn code sau:
{{EJS0}}
Thiết lập máy chủ và nhập các gói require sau:
{{EJS1}}
Thiết lập một file index.html mà máy chủ gửi về:
{{EJS2}}
Thiết lập một connection điều khiển chức năng của Socket.IO:
{{EJS3}}
Thiết lập cổng 3000 trên máy chủ:
{{EJS4}}
Khởi động ứng dụng.nodeindex.js và mở trang trên trình duyệt
Máy khách
Thiết lập kết nối socket. IO bằng các lệnh:
{{EJS5}}
3.4 Cách nhận tin nhắn qua lại
Máy chủ
Sử dụng hàm io.emit() để gửi tin nhắn từ máy chủ đến máy khách:
{{EJS6}}
Sử dụng socket.broadcast.emit() để gửi tin nhắn cho tất cả mọi người trừ những người đang ở trong trạng thái kết nối.

Hoặc để thêm người nhận cho tin nhắn, sử dụng lệnh sau. Người nhận mới sẽ nhận được những tin nhắn từ lúc bắt đầu được thêm vào:
{{EJS7}}
Máy khách
Sử dụng tệp index.html để hiển thị đầu vào và vùng chứa của tin nhắn:
{{EJS10}}
Tiếp theo hãy bổ sung một số logic vào <script>:
{{EJS11}}
Các hàm socket.on có hai chức năng event và callback. Nếu máy chủ phát hiện ra các event phù hợp, ngay lập tức lệnh callback sẽ được khởi động bằng cách hiển thị trên màn hình máy chủ.
	
 
CHƯƠNG IV . THIẾT KẾ ỨNG DỤNG

4.1 Cơ sở dữ liệu
•	Mô hình ERD

 ![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/c7f4593a-dad1-4df5-9144-62a5d1331fc6)

•	Diagram

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/7bb2c5c6-bf00-4284-8b65-267b9f290a1e)

 
•	Bảng từ điển
+ members (username, enable)
	

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/cf607f82-167b-4523-a6dc-e13327adcd85)
		

+ rooms(name, password, isLock)
![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/3170709b-4dc8-46e8-ba82-119036a2e256)


+ room_member (name_room, username_member)
![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/3fb8faae-96fd-4da8-b46a-2c65b1204a87)

+ activitys (id, name)
![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/438db2e6-a411-48cf-b7c9-4329bdb531a8)


+ logs (id, username_member, name_room, activity, time, data)
![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/e9a8e70b-67d5-4d5b-a3c8-6e4627a35223)


 
4.2 Xây dựng các chức năng
	Giao diện tạo, đăng nhập của người dùng

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/d2703537-9941-47a4-9d22-322f10ca0a80)

Hình 4.1 Đăng nhập tham gia nhóm chat



Bằng cách điền username vào ô, ứng dụng sẽ kiểm tra xem người dùng với username này đã tồn tại chưa, nếu đã tồn tại, sẽ đăng nhập vào với tài khoản đó, nếu chưa tồn tại, sẽ tạo một tài khoản user mới và đăng nhập vào tài khoản đó
	Giao diện chat

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/826f9ce2-f784-4fee-b80b-16d09d332e2f)
Hình 4.2 Nhập mật khẩu để tham gia nhóm chat
 

•	Điền mật khẩu để tham gia nhóm chat (nếu nhóm chat có mật khẩu)

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/3807aad4-74f0-4ab1-bba4-63e8a4c14bde)


•	Người dùng có thể chat, gửi thông tin trong nhóm và có thể rời nhóm chat

	Giao diện admin
![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/ab61f81f-9ed3-4cba-acd4-c4f5e33d1a81)

Hình 4.4 Giao diện admin
![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/2005cd28-3f67-43f7-af4e-1fb95ae25b6d)


Hình 4.5 Admin xem danh sách phòng chat
•	Admin có thể xem danh sách các phòng chat và thực hiện các chức năng khóa phòng, gửi thông báo và mở khóa phòng chat (nếu phòng chat bị khóa)

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/9fb09d78-414c-4be9-82db-a0a3461b47ee)
 
Hình 4.6 Admin khóa phòng

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/27052e23-0be3-4678-87b9-7ea4f5211aa4)
   
Hình 4.7 Admin mở khóa phòng

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/4344c562-6123-44af-aae6-feccc53a1de5)

Hình 4.8 Khóa tài khoản người dùng

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/16d271fc-4403-4121-b1b4-4448e3a72993)

 
Hình 4.9 Mở khóa tài khoản người dùng
![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/fe55f967-9d49-46c9-969c-05472019aeb9)
 
Hình 4.10 Gửi thông báo đến tài khoản người dùng
CHƯƠNG V . NỘI DUNG CÁ NHÂN

5.1 Chức năng khóa phòng chat


![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/96d8b0bd-baad-416c-94c9-3e0bc480b76a)
 

lockRoom Function:
•	Input: Nhận vào tên của phòng cần khóa (nameRoom).
•	Output: Trả về một Promise, giải quyết với kết quả từ cơ sở dữ liệu sau khi phòng đã được khóa hoặc bị từ chối nếu có lỗi.
Sử dụng một truy vấn SQL để cập nhật bảng "rooms". Trong trường hợp này, truy vấn đặt giá trị cột "isLock" thành 1 cho phòng có tên tương ứng với nameRoom. Điều này có thể được sử dụng để kiểm soát quyền truy cập vào phòng, ví dụ như không cho phép người dùng mới tham gia sau khi phòng đã bị khóa.
Sau khi thực hiện truy vấn, kết nối cơ sở dữ liệu được đóng bằng cách sử dụng mssql.close().
Tóm lại, hàm này thực hiện công việc cụ thể là khóa một phòng trong cơ sở dữ liệu và sử dụng Promise để xử lý kết quả hoặc lỗi trong quá trình thực hiện.
5.2 Chức năng mở khóa phòng chat (Nếu phòng đã bị khóa)


 ![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/3893069e-0caa-41de-be27-346a5c9a371b)


unlockRoom Function:
•	Input: Nhận vào tên của phòng cần mở khóa (nameRoom).
•	Output: Trả về một Promise, giải quyết với kết quả từ cơ sở dữ liệu sau khi phòng đã được mở khóa hoặc bị từ chối nếu có lỗi.
Sử dụng một truy vấn SQL để cập nhật bảng "rooms". Trong trường hợp này, truy vấn đặt giá trị của cột "isLock" thành 0 để mở khóa phòng có tên tương ứng với nameRoom. Điều này có thể được sử dụng để cho phép người dùng mới tham gia vào phòng sau khi phòng đã được mở khóa.
Sau khi thực hiện truy vấn, kết nối cơ sở dữ liệu được đóng bằng cách sử dụng mssql.close().
Tóm lại, hàm trên thực hiện chức năng khóa phòng chat trong cơ sở dữ liệu, giúp kiểm soát quyền truy cập và bảo vệ tính riêng tư của phòng đó trong ứng dụng chat.

5.3 Chức năng khóa tài khoản người dùng

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/3412c46c-c793-41e3-adeb-3cc01564ea7a)

 

lockMember Function:
•	Input: Nhận vào tên thành viên cần khóa (nameMember).
•	Output: Trả về một Promise, giải quyết với kết quả từ cơ sở dữ liệu sau khi tài khoản đã được khóa hoặc bị từ chối nếu có lỗi.
Sử dụng một truy vấn SQL để cập nhật bảng "members". Trong trường hợp này, truy vấn đặt giá trị của cột "enable" thành 0 để khóa tài khoản của thành viên có tên tương ứng với nameMember.
Sau khi thực hiện truy vấn, kết nối cơ sở dữ liệu được đóng bằng cách sử dụng mssql.close().
Tóm lại, hàm lockMember này thực hiện chức năng khóa tài khoản của một thành viên trong cơ sở dữ liệu, ngăn chặn họ khỏi việc truy cập vào ứng dụng.



5.4 Chức năng mở khóa tài khoản người dùng

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/e6f9d09b-be8b-4492-9b8a-eaccd5f1a4f0)

 

unlockMember Function:
•	Input: Nhận vào tên thành viên cần mở khóa (nameMember).
•	Output: Trả về một Promise, giải quyết với kết quả từ cơ sở dữ liệu sau khi tài khoản đã được mở khóa hoặc bị từ chối nếu có lỗi.
Sử dụng một truy vấn SQL để cập nhật bảng "members". Trong trường hợp này, truy vấn đặt giá trị của cột "enable" thành 1 để mở khóa tài khoản của thành viên có tên tương ứng với nameMember. Điều này có thể được sử dụng để cho phép người dùng có tên nameMember truy cập lại vào ứng dụng sau khi tài khoản đã được mở khóa.
Sau khi thực hiện truy vấn, kết nối cơ sở dữ liệu được đóng bằng cách sử dụng mssql.close().
Tóm lại, hàm unlockMember này thực hiện chức năng mở khóa tài khoản của một thành viên trong cơ sở dữ liệu, cho phép họ truy cập lại vào ứng dụng.


5.5 Chức năng rời khỏi nhóm chat

![image](https://github.com/Nhung2310/ChatRPC/assets/89560779/94867a6e-7ec1-46d7-9d31-65a253cf71da)

 
 
Hàm ‘LogOutRoom’ Function:
•	Input: Nhận vào tên của phòng chat (nameRoom) và tên của thành viên cần đăng xuất (nameMember).
•	Output: Trả về một Promise, giải quyết với kết quả từ cơ sở dữ liệu sau khi thành viên đã đăng xuất khỏi nhóm chat hoặc bị từ chối nếu có lỗi.
Sử dụng một truy vấn SQL để xóa thông tin thành viên khỏi bảng "room_member". Truy vấn này chỉ xóa hàng trong bảng có nameRoom và nameMember tương ứng. Truy vấn SQL này giúp loại bỏ thông tin thành viên khỏi bảng liên kết giữa phòng chat và thành viên, tác động như một cơ chế đăng xuất. Sau khi thực hiện truy vấn, kết nối cơ sở dữ liệu được đóng bằng cách sử dụng mssql.close().
Tóm lại, hàm LogOutRoom này thực hiện chức năng đăng xuất thành viên khỏi một nhóm chat trong cơ sở dữ liệu, loại bỏ thông tin liên kết giữa thành viên và phòng chat.
 
CHƯƠNG VI . TỔNG KẾT ĐÁNH GIÁ

	Đánh giá:
-	Ưu điểm:
	Đáp ứng được các chức năng và yêu cầu của đề tài.
	Bố cục rõ rang
	Tốc độ xử lý tương đối nhanh
	Giao diện dễ nhìn, dễ hiểu, dễ sử dụng
-	Khuyết điểm:
	Chưa có các chức năng hỗ trợ người dung như: hỗ trợ đa ngôn ngữ, chuyển đổi màu khung chat,…
	Kết luận:
Trong quá trình thực hiện, nhóm đã cố gắng tập trung tìm hiểu và tham khảo các tài liệu liên quan. Tuy nhiên với thời gian và trình độ còn hạn chế, nên chúng em không thể tránh khỏi những thiếu sót. Nhóm em rất mong nhận được các nhận xét và góp ý của thầy để chúng em có thể hoàn thiện hơn các kết quả nghiên cứu.
 
Danh mục tài liệu tham khảo

[1] "Programming Distributed Computing Systems: A Foundational Approach" by Carlos A. Varela
https://mitpress.mit.edu/9780262018982/programming-distributed-computing-systems/
[2] "Distributed Computing: Principles, Algorithms, and Systems" by Ajay D. Kshemkalyani and Mukesh Singhal
https://eclass.uoa.gr/modules/document/file.php/D245/2015/DistrComp.pdf
[3] Socket.IO Real-time Web Application Development
https://www.readings.com.au/product/9781782160786/9781782160786#
[4] Socket.IO - A Real-time Framework for Node.JS
https://socket.io/get-started/chat


