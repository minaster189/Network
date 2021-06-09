# DHCP (Dynamic Host Configuration)

## DHCP là gi?

Là viết tắt của **Dynamic Host Configuration Protocol**, là giao thức tự động cấp pháp địa chỉ IP đến các thiết bị trong mạng. Các địa chỉ IP được cung cấp từ giao thức DHCP sẽ cho phép chúng ta truy cập vào internet.

![alt](https://wiki.matbao.net/wp-content/uploads/2019/08/ip-la-gi-ip-dong-co-the-duoc-tuy-chinh-boi-may-chu-dhcp.jpg)

## Ưu và nhược điểm của DHCP là gì?

- **Ưu điểm:** tính linh hoạt, dễ cài đặt và dễ quản lý. Số lượng thiết bị kết nối sẽ ít bị giới hạn với IP động. Người quản trị mạng có thể tùy ý thay đổi cấu hình, thông số IP theo nhu cầu sử dụng để nâng cấp hạ tầng.
- **Nhược điểm:** Việc dùng địa chỉ IP động không phù hợp với những thiết bị cố định, có tần suất truy cập cao, liên tục như máy in, file server. DHCP chỉ phù hợp cho các mô hình mạng nhỏ hoặc tại hộ gia đình.

## Chức năng

- Mỗi thiết bị trên mạng cơ sở TCP/IP phải có một địa chỉ IP duy nhất để truy cập mạng và các tài nguyên của nó. Không có DHCP, cấu hình IP phải được thực hiện một cách thủ công cho các máy tính mới, các máy tính di chuyển từ mạng con này sang mạng con khác, và các máy tính được loại bỏ khỏi mạng.

- Bằng việc phát triển DHCP trên mạng, toàn bộ tiến trình này được quản lý tự động và tập trung. DHCP server bảo quản vùng của các địa chỉ IP và giải phóng một địa chỉ với bất cứ DHCP client có thể khi nó có thể ghi lên mạng. Do là cơ chế động nên các IP đã được cấp phát nhưng trong một khoảng thời gian nhất định mà không còn hoạt động sẽ được thu hồi và cấp lại cho máy khác khi tham gia mạng.

## Các thông điệp DHCP

![alt](https://s3-ap-southeast-1.amazonaws.com/kipalog.com/d9wm2f5ult_image.png)

- **DHCP Discover:** Một DHCP Client khi mới tham gia vào hệ thống mạng, nó sẽ yêu cầu thông tin địa chỉ IP từ DHCP Server bằng cách broadcast một gói DHCP Discover. Địa chỉ IP nguồn trong gói là 0.0.0.0 bởi vì client chưa có địa chỉ IP.

- **DHCP Offer:** Khi DHCP server nhận được gói DHCP Discover từ client, nó sẽ gửi lại một gói DHCP Offer chứa địa chỉ IP, Subnet Mask, Gateway,... Có thể nhiều DHCP server gửi lại với gói DHCP Offer nhưng Client sẽ chấp nhận gói DHCP Offer đầu tiên nó nhận được.

- **DHCP Request:** Khi DHCP client nhận được một gói DHCP Offer, nó đáp lại bằng việc broadcast gói DHCP Request để xác nhận hoặc để kiểm tra lại các thông tin mà DHCP server vừa gửi.

- **DHCP Acknowledge:** Server kiểm tra và xác nhận lại sự chấp nhận trên bằng gói tin DHCP Acknowledge, Client có thể tham gia trên mạng TCP/IP và hoàn thành hệ thống khởi động.

- **DHCP Nak:** Nếu một địa chỉ IP đã hết hạn hoặc đã được đặt một máy tính khác, DHCP Server gửi gói DHCP Nak cho Client, như vậy Client phải bắt đầu tiến trình thuê bao lại.

- **DHCP Decline:** Nếu DHCP Client nhận được bản tin trả về không đủ thông tin hoặc hết hạn, nó sẽ gửi gói DHCP Decline đến các Server và Client phải bắt đầu tiến trình thuê bao lại.

- **DHCP Release:** Client gửi bản tin này đến server để ngừng thuê IP. Khi nhận được bản tin này, server sẽ thu hồi lại IP đã cấp cho Client, khi đó client sẽ không được cấu hình IP.

## Cơ chế hoạt động

![alt](https://wiki.matbao.net/wp-content/uploads/2020/02/dhcp-la-gi-8.png)

- **Bước 1:** Khi máy Client khởi động, máy sẽ gửi broadcast gói tin DHCP DISCOVER, yêu cầu một Server phục vụ mình. Gói tin này cũng chứa địa chỉ MAC của client. Nếu client không liên lạc được với DHCP Server thì sau 4 lần truy vấn không thành công nó sẽ tự động phát sinh ra 1 địa chỉ IP riêng cho chính mình nằm trong dãy 169.254.0.0 đến 169.254.255.255 dùng để liên lạc tạm thời. Và client vẫn duy trì việc phát tín hiệu Broad cast sau mỗi 5 phút để xin cấp IP từ DHCP Server.

- **Bước 2:** Các máy Server trên mạng khi nhận được yêu cầu đó. Nếu còn khả năng cung cấp địa chỉ IP, đều gửi lại cho máy Client một gói tin DHCP OFFER, đề nghị cho thuê một địa chỉ IP trong một khoảng thời gian nhất định, kèm theo là một Subnet Mask và địa chỉ của Server. Server sẽ không cấp phát đia chỉ IP vừa đề nghị cho client thuê trông suốt thời gian thương thuyết.

- **Bước 3:** Máy Client sẽ lựa chọn một trong những lời đề nghị ( DHCPOFFER) và gửi broadcast lại gói tin DHCPREQUEST và chấp nhận lời đề nghị đó. Điều này cho phép các lời đề nghị không được chấp nhận sẽ được các Server rút lại và dùng để cấp phát cho các Client khác.

- **Bước 4:** Máy Server được Client chấp nhận sẽ gửi ngược lại một gói tin DHCP ACK như một lời xác nhận, cho biết địa chỉ IP đó, Subnet Mask đó và thời hạn cho sử dụng đó sẽ chính thức được áp dụng. Ngoài ra server còn gửi kèm những thông tin bổ xung như địa chỉ Gateway mặc định, địa chỉ DNS Server.

## Gói tin DHCP

| Tên Field  | Dung lượng  | Mô tả  |
| ---    | :-----:      | ---    |
| Opcode  | 8 bits  | Thể hiện gói tin DHCP. Value 1: các gói tin request, value 2: các gói tin reply.|
| Hardware type  | 8 bits  | Quy định cụ thể loại hardware. Value 1: Ethernet (10mb), value 6: IEEE 802...|
| Hardware length  | 8 bits  | Quy định cụ thể độ dài của địa chỉ hardware.|
| Hop counts  | 8 bits  | Dùng cho relay agents.|
| Transaction Identifier  | 32 bits  | Được tạo bởi client, dùng để liên kết giữa request và replies của client và server.|
| Number of seconds  | 16 bits  | Quy định số giây kể từ client bắt đầu thuê hoặc xin cấp lại IP.|
| Flags  | 16 bits  | Broadcast: 1 bits = 1 đây là một loại dấu hiệu để nhận biết gói tin client có phải là Broadcast (1) hay không. |
| Client IP address  | 32 bits  | Máy khách sẽ đưa IP của nó vào trường này nếu nó hợp lệ hoặc đang trong các trạng thái BOUND, RENEWING, REBINDING; ngược lại giá trị bằng 0. |
| Your IP address  | 32 bits  | Đây là địa chỉ IP mà server gán cho client. |
| Server IP address  | 32 bits  | Địa chỉ của DHCP mà client giao tiếp để thuê IP trong suốt thời gian ở trong mạng này. |
| Gateway IP Address  | 32 bits  | Địa chỉ GW để mạng này ra ngoài mạng khác, internet,... |
| Client hardware address  | 16 bytes  | Địa chỉ MAC của client, dùng để xác định và giao tiếp. |
| Server host Name  | 64 bytes  | Tên của server, có thể là domain của server. |
| Boot filename  | 128 bytes  | Sử dụng bởi client để yêu cầu loại tập tin khởi động cụ thể trong gói tin discover. Sử dụng bởi server để chỉ rõ toàn bộ đường dẫn, tên file của file khởi động trong gói tin offer. |
