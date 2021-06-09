# Mô hình OSI

## Tổng quan mô hình 7 tầng OSI

### 1. Định nghĩa

#### A. Mô hình OSI là gì?

- Viết tắt của từ **Open Systems Interconnection** - tạm dịch là ***Mô hình tham chiếu kết nối các hệ thống mở***. Là mô hình căn bản về các tiến trình truyền thông, thiết lập các tiêu chuẩn kiến trúc mạng ở mức quốc tế, là cơ sở chung để các hệ thống khác nhau có thể liên kết và truyền thông được với nhau.
- Mô hình OSI gồm 7 tầng:

![alt](https://www.totolink.vn/public/uploads/img_article/mohinhosilagichucnangcuacactanggiaothuctrongmohinhosi.png)

#### B. Ưu điểm của mô hình OSI

- Chia hoạt động của thông tin mạng thành những phần nhỏ và đơn giản hơn.
- Chuẩn hóa các thành phần mạng để dễ dàng phát triển.
- Chuẩn hóa giao diện giữa các tầng.
- Dễ dàng truyền dữ liệu.

#### C. Các nguyên tắc phân tầng mô hình OSI

- Mô hình gồm 7 tầng. OSI là hệ thống mở, có khả năng kết nối với các hệ thống khác nhau, tương thích với các chuẩn OSI.
- Quá trình xử lý các ứng dụng được thực hiện trong các hệ thống mở, đồng thời duy trì các hoạt động kết nối giữa các hệ thống.
- Thiết lập kênh logic nhằm mục đích thực hiện trao đổi thông tin giữa các thực thể.

#### D. Các giao thức trong mô hình OSI

![alt](https://media.geeksforgeeks.org/wp-content/uploads/20190519204240/Untitled-Diagram-217.png)

- **Giao thức hướng liên kết (Connection Oriented)**: Trước khi truyền dữ liệu, các thực thể đồng tầng trong hai hệ thống phải thiết lập một liên kết logic. Chúng thương lượng với nhau về tập các tham số sẽ sử dụng trong giai đoạn truyền dữ liệu, cắt/hợp dữ liệu, liên kết sẽ được hủy bỏ. Thiết lập liên kết logic sẽ nâng cao độ tin cậy và an toàn trong quá trình trao đổi dữ liệu.

![alt](https://media.geeksforgeeks.org/wp-content/uploads/20190519204308/Untitled-Diagram-221.png)

- **Giao thức không liên kết (Connectionless)**: Dữ liệu được truyền độc lập trên các tuyến khác nhau. Với các giao thức không liên kết chỉ có giai đoạn duy nhất truyền dữ liệu.

#### E. Vai trò và chức năng chủ yếu các tầng

![alt](https://www.cloudflare.com/img/learning/ddos/what-is-a-ddos-attack/osi-model-7-layers.svg)

##### - Tầng 7 - Application

![alt](https://www.cloudflare.com/img/learning/ddos/glossary/open-systems-interconnection-model-osi/7-application-layer.svg)

- Cung cấp giao tiếp giữa chương trình ứng dụng cho người sử dụng với hệ thống mạng.
- Trình bày các đặc tả kỹ thuật để giải quyết vấn đề giao tiếp giữa các chương trình ứng dụng với hệ thống mạng.
- Ví dụ: Các ứng dụng HTTP, Telnet, FTP, Mail...

##### - Tầng 6 - Presentation

![alt](https://www.cloudflare.com/img/learning/ddos/glossary/open-systems-interconnection-model-osi/6-presentation-layer.svg)

- Trình bày dữ liệu: mã hóa, giải mã chuyển đổi mã hóa dữ liệu. chuyển dữ liệu người dùng nhập vào thành các chuẩn để các máy tính khác hiểu được trước khi đưa vào đường truyền. Đảm bảo dữ liệu gửi đi thì ứng dụng các máy khác sẽ đọc được.
- Một số chuẩn mã hóa như:
  - **PICT:** định dạng cho ảnh.
  - **TIFF:** định dạng cho tập tin đồ họa các độ phân giải cao.
  - **JPEG:** định dạng chuẩn cho tập tin ảnh.
  - **MIDI:** định dạng nhạc số.
  - **MPEG:** định dạng video cho đĩa CD với bit-rate lên tới 1.5Mbps.
  - **QuickTime:** quản lí các ứng dụng chạy nhạc, video.

##### - Tầng 5 - Sesion

![alt](https://www.cloudflare.com/img/learning/ddos/glossary/open-systems-interconnection-model-osi/5-session-layer.svg)

- Đây là lớp chịu trách nhiệm đóng mở giao tiếp giữa hai thiết bị. Cho phép người dùng trên các máy khác nhau thiết lập, duy trì và đồng bộ phiên truyền thông giữa họ với nhau.
- Tầng phiên thiết lập "các giao dịch" giữa các thực thể đầu cuối. Dịch vụ phiên cung cấp một liên kết giữa hai đầu cuối, sao cho trao đổi dữ liệu một cách đồng bộ và khi kết thúc thì giải phóng liên kết. Nó sẽ sử dụng thẻ (Token) để thực hiện truyền dữ liệu, đồng bộ hóa và hủy bỏ liên kết trong các phương thức truyền đồng thời hay luân phiên. Khi xảy ra sự cố có thể khôi phục hội thoại bắt đầu từ một điểm đồng bộ hóa đã thỏa thuận.
- Ví dụ:
  - ***Network File System (NFS):*** cho phép truy cập ẩn danh vào các tài nguyên ở xa.
  - ***Structured Query Language (SQL):*** cung cấp cho người dùng cách thức đơn giản để xác định thôn tin cần thiết ở cả hệ thống nội bộ và bên ngoài.
  - ***Remote Procedure Call (RPC)***
  - ***AppleTalk Session Protocol (ASP):*** thiết lập và duy trì phiên làm việc giữa các máy khách của Appletalk và máy chủ.

##### - Tầng 4 - Transport

![alt](https://www.cloudflare.com/img/learning/ddos/glossary/open-systems-interconnection-model-osi/4-transport-layer.svg)

- Là tầng chịu trách nhiệm giao tiếp đầu cuối giữa hai thiết bị. Điều này bao gồm việc lấy dữ liệu từ lớp phiên và chia nhỏ nó thành các phần được gọi là phân đoạn trước khi gửi đến lớp 3 - Network. lớp truyền tải trên thiết bị nhận chịu trách nhiệm tập hợp lại các phân đoạn thành dữ liệu mà lớp phiên có thể sử dụng.
- Tầng vận chuyển cũng chịu trách nhiệm kiểm soát luồng và kiểm soát lỗi. Kiển soát luồng xác định tốc độ truyền tối ưu để đảm bảo rằng người gửi có kết nối nhanh không lấn át người nhận có kết nối chậm. Lớp truyển tải thực hiện kiểm soát lỗi ở đầu nhận bằng cách đảm bảo rằng dữ liệu được là hoàn chỉnh và yêu cầu truyền lại nếu không.

##### - Tầng 3 - Network

![alt](https://www.cloudflare.com/img/learning/ddos/glossary/open-systems-interconnection-model-osi/3-network-layer.svg)

- Lớp mạng có nhiệm vụ tạo điều kiện thuận lợi cho việc truyền dữ liệu giữa hai mạng khác nhau. Nếu hai thiết bị giao tiếp trên cùng một mạng, thì lớp mạng là không cần thiết.
- Lớp mạng chia nhỏ các phân đoạn từ lớp truyền tải thành các đơn vị nhỏ hơn, được gọi là gói, trên thiết bị của người gửi và tập hợp lại các gói này trên thiết bị nhận. Lớp mạng cũng tìm ra con đường vật lý tốt nhất để dữ liệu đến đích của nó; điều này được gọi là định tuyến (routing).

##### - Tầng 2 - DataLink

![alt](https://www.cloudflare.com/img/learning/ddos/glossary/open-systems-interconnection-model-osi/2-data-link-layer.svg)

- lớp liên kết dữ liệu rất giống với lớp mạng, ngoại trừ lớp liên kết dữ liệu tạo điều kiện thuận lợi cho việc truyền dữ liệu giữa hai thiết bị trên cùng mạng.
- Lớp liên kết dữ liệu nhận các gói từ lớp mạng và chia chúng thành các phần nhỏ hơn gọi là khung (Frame). Giống như lớp mạng, lớp liên kết dữ liệu cũng chịu trách nhiệm điều khiển luồng và điều khiển lỗi trong giao tiếp nội mạng (lớp vận chuyển chỉ làm nhiệm vụ điều khiển luồng và điều khiển lỗi cho truyền thông giữa các mạng).

##### -Tầng 1 - Physical

![alt](https://www.cloudflare.com/img/learning/ddos/glossary/open-systems-interconnection-model-osi/1-physical-layer.svg)

- Lớp này bao gồm các thiết bị vật lý liên quan đến truyền dữ liệu, chẳng hạn như cáp và thiết bị chuyển mạch.
- Đây cũng là lớp mà dữ liệu được chuyển đổi thành một luồng bit, là một chuỗi gồm các số 1 và 0. Lớp vật lý của cả hai thiết bị cũng phải đồng ý về quy ước tín hiệu để có thể phân biệt số số 1 với số 0 trên cả hai thiết bị.

#### F. Tóm tắt chức năng các tầng giao thức trong OSI

| Tầng    | Nhiệm vụ  | Chức năng  |
| ---    | ---      | ---       |
| **7 - Ứng dụng (application)** | Cung cấp giao diện để người dùng giao tiếp với máy tính và môi trường mạng. | file, print, message, database, appication services |
| **6 - Phiên dịch (Presentation)** | Phiên dịch dữ liệu, xử lí dữ liệu mã hóa, giải mã. | Data encryption, Compression, Transalation services |
| **5 - Phiên (Session)** | Thiết lập, theo dõi và chấm dứt các phiên kết nối. | Dialog control |
| **4 - Giao vận (Transport)** |- Cung cấp việc vận các segment bằng cách nhanh, không an toàn ***(UDP - User Datagram Protocol)*** hay chậm nhưng an toàn ***(TCP - Transmission Control Protocol)***. </br> - Trình sửa lỗi segment trước khi truyền. | End-to-End connection |
| **3 - Mạng (Network)** | - Xác định đường dẫn. </br> - Gán địa chỉ IP logic (Nguồn/Đích) -> dùng cho thiết bị lớp 3 như router. </br> - Gói tin được đóng vào các packet | Routing |
| **2 - Liên kết dữ liệu (Data Link)** | - Đóng gói các packet thành các frame lớn hơn. </br> - Gán địa chỉ **MAC (Media Access Control)** vào các Frame. </br> - Cung cấp chức năng xác định lỗi gói tin - Frame | Framing |
| **1 - Vật lí (Physical)** | Mã hóa và truyền các bit (0, 1) dữ liệu. | Physical Topology |

#### G. Quy trình truyền gói tin trong mô hình mạng OSI:

##### Phía máy gửi

![alt](https://cache.digistar.vn/wp-content/uploads/2016/11/ois-sent-300x202.jpg?x72252)

- Ở tầng **Application (tầng 7)**, người dùng tiến hành đưa thông tin cần gửi vào máy tính. Các thông tin này thường có dạng như: hình ảnh, văn bản,...
- Sau đó thông tin dữ liệu này được chuyển xuống tầng **Presentation (tầng 6)** để chuyển các dữ liệu thành một dạng chung để nã hóa dữ liệu và nén dữ liệu.
- Dữ liệu tiếp tục được chuyển xuống tầng **Session (tầng 5)**. Tầng này là tầng phiên có chức năng bổ sung các thông tin cần thiết cho phiên giao dịch (gửi-nhận) này.
- Sau khi tầng Session thực hiện xong nhiệm vụ, nó sẽ tiếp tục chuyển dữ liệu này xuống tầng **Transport (tầng 4)**. Tại tầng này, dữ liệu được cắt ra thành nhiều Segment và cũng làm nhiệm vụ bổ sung thêm các thông tin về phương thức vận chuyển dữ liệu để đảm bảo tính bảo mật, tin cậy khi truyền trong mô hình mạng.
- Tiếp đó, dữ liệu sẽ được chuyển xuống tầng **Network (tầng 3)**.  Ở tầng này, các segment lại tiếp tục được cắt ra thành nhiều gói Package khác nhau và bổ sung thông tin định tuyến. Tầng Network này chức năng chính của nó là định tuyến đường đi cho gói tin chứa dữ liệu.
- Dữ liệu tiếp tục được chuyển xuống tầng **Data Link (tầng 2)**. Tại tầng này, mỗi Package sẽ được cắt nhỏ ra thành nhiều Frame và bổ sung thêm các thông tin kiểm tra gói tin chứa dữ liệu để kiểm tra ở máy nhận.
- Cuối cùng, các Frame này khi chuyển xuống tầng **Physical (tầng 1)** sẽ được chuyển thành một chuỗi các bit nhị phân ( 0 1 .... ) và được đưa lên cũng như phát tín hiệu trên các phương tiện truyền dẫn (như dây cáp đồng, cáp quang...) để truyền dữ liệu đến máy nhận.
- Mỗi gói tin dữ liệu khi được đưa xuống các tầng thì được gắn các HDR = Header của tầng đó, riêng tầng 2 (Data Link), gói tin được gắn thêm FCS (Frame Check Sequence - Trình tự kiểm tra khung).

#### Phía máy nhận

![alt](https://cache.digistar.vn/wp-content/uploads/2016/11/osi-5-300x237.jpg?x72252)

- Tầng **Physical (tầng 1)** phía máy nhận sẽ kiểm tra quá trình đồng bộ và đưa các chuỗi bit nhị phân nhận được vào vùng đệm. Sau đó gửi thông báo cho tầng Data Link  rằng dữ liệu đã được nhận.
- Tiếp đó tầng **Data Link (tầng 2)** sẽ tiến hành kiểm tra các lỗi trong frame mà bên máy gửi tạo ra bằng cách kiểm tra FCS có trong gói tin được gắn bên phía máy nhận. Nếu có lỗi xảy ra thì frame đó sẽ bị huỷ bỏ. Sau đó kiểm tra địa chỉ lớp Data Link (MAC Address - Media Access Control) xem có trùng với địa chỉ của máy nhận hay không. Nếu trùng thì lớp Data Link sẽ thực hiện gỡ bỏ Header của tầng Data Link để tiếp tục chuyển lên tầng Network.
- Tầng **Network (tầng 3)** sẽ tiến hành kiểm tra xem địa chỉ trong gói tin này có phải là địa chỉ của máy nhận hay không. (Lưu ý: địa chỉ ở tầng này là địa chủ IP). Nếu đúng địa chỉ máy nhận tầng Network sẽ gỡ bỏ Header của nó và tiếp tục chuyển đến tầng Transport để tiếp tục qui trình.
- Ở tầng **Transport (tầng 4)** sẽ hỗ trợ phục hồi lỗi bằng cách gửi các gói tin ACK (Acknowledgement Frame), NAK (Negative Acknowledgement). (Gói tin dùng để phản hồi xem các gói tin chứa dữ liệu đã được gửi đến máy nhận hay chưa?). Sau khi phục hồi sửa lỗi, tầng này sẽ tiếp tục sắp xếp các thứ tự phân đoạn và đưa dữ liệu đến tầng Session.
- Tầng **Session (tầng 5)** làm nhiệm vụ đảm bảo các dữ liệu trong gói tin nhận được toàn vẹn. Sau đó tiến hành gỡ bỏ Header của tầng Session và tiếp tục gửi lên tầng Presentation.
- Tầng **Presentation (tầng 6)** sẽ xử lý gói tin bằng cách chuyển đổi các định dạng dữ liệu cho phù hợp. Sau khi hoàn thành sẽ tiến hành gửi lên tầng Application.
- Cuối cùng, tầng **Application (tầng 7)** tiến hành xử lý và gỡ bỏ Header cuối cùng. Khi đó ở máy nhận sẽ nhận được dữ liệu của gói tin được truyền đi.
