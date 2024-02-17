# Bài tập Tết học phần Kiến trúc phần mềm INT3105 1
## 1. Docker và Docker-compose
### 1.1. Công nghệ ảo hóa (virtualization) và container hóa (containerization)
**Virtualization** là công nghệ ảo hóa, cho phép chúng ta có thể cài nhiều môi trường ảo với các hệ điều hành khác nhau trên cùng một máy vật lý. Công nghệ ảo hóa dựa vào một **hypervisor**, một lớp phần mềm giúp các hệ điều hành có thể song song tồn tại và chia sẻ cùng một nguồn tài nguyên.
Tuy công nghệ ảo hóa có nhiều ưu điểm so với việc phải sử dụng máy chủ vật lý như giá thành thấp, độc lập với phần cứng, có thể chạy nhiều môi trường khác nhau cùng lúc. Tuy vậy, công nghệ ảo hóa truyền thống sẽ làm tăng chí phí vận hành phát sinh do phải có thêm một lớp nữa xen giữa tầng vật lý và tầng phần mềm.
![So sánh giữa môi trường truyền thống và môi trường ảo hóa](https://github.com/revoluzionario/software-architecture-docker/assets/94961228/eb5d4b25-421a-4e11-ac11-19e09e4ca434)

Để khắc phục tình trạng này, một công nghệ khác là **container hóa** hay **containerization** đã ra đời. Công nghệ này cho phép chúng ta có thể chạy nhiều instance, được cọi là container, trên cùng một máy chủ vật lý mà không cần hypervisor, mà thay vào đó, các container này sẽ cùng chia sẻ chung nhân hệ điều hành, và qua đó hiệu suất tốt hơn so với ảo hóa truyền thống. 
![So sánh giữa Containerization và Virtualization](https://github.com/revoluzionario/software-architecture-docker/assets/94961228/f6c3520a-f758-45c9-b054-cf7934642b8d)

Công nghệ ảo hóa và container hóa được sử dụng để tạo ra một môi trường biệt lập chuyên dùng cho phát triển phần mềm, giúp các dự án phát triển phần mềm có thể dễ dàng quản lý và kiểm soát về tài nguyên cũng như quy mô phần mềm.

### 1.2. Giới thiệu về Docker
**Docker** là nền tảng phần mềm cho phép dựng, kiểm thử và triển khai ứng dụng một cách nhanh chóng. Docker đóng gói phần mềm vào các đơn vị tiêu chuẩn hóa được gọi là container có mọi thứ mà phần mềm cần để chạy, trong đó có thư viện, công cụ hệ thống, mã và thời gian chạy. Bằng cách sử dụng Docker, ta có thể nhanh chóng triển khai và thay đổi quy mô ứng dụng vào bất kỳ môi trường nào và biết chắc rằng code sẽ chạy được.

**docker-compose** là công cụ dùng để định nghĩa và chạy các multi-container cho Docker application. Với compose chúng ta sử dụng file YAML để tùy chỉnh các services cho phần mềm, sau đó dùng command để tạo và khởi chạy từ những config đó, thông qua ba bước như sau:

1. Khai báo môi trường trong Dockerfile.
2. Khai báo các services cần thiết để chạy phần mềm trong file docker-compose.yml.
3. Chạy docker-compose để khởi chạy.

## 2. Linux, Unix, BSD, *nix
**Unix** là một tập hợp gồm nhiều hệ điều hành máy tính **đa nhiệm**, **nhiều người dùng** bắt nguồn từ hệ điều hành Unix gốc của tập đoàn AT&T. Việc phát triển Unix được bắt đầu từ 1969 tại phòng thí nghiệm Bell bởi các tác giả Ken Thompson, Dennis Ritchie,... (cũng là các tác giả tạo ra ngôn ngữ lập trình C).
Sau khi AT&T cấp phép sử dụng công khai đối với hệ điều hành Unix, đã có rất nhiều hệ điều hành dựa trên Unix được phát triển, bao gồm BSD (Berkeley Software Distribution), Microsoft Xenix,... dẫn đến việc Tiêu chuẩn UNIX đơn nhất (Single UNIX Specification - SUS) và tiêu chuẩn POSIX ra đời để thống nhất quy chuẩn.
Các hệ điều hành Unix được thiết kế dựa trên **"triết lý Unix"**, trong đó, hệ điều hành sẽ được phân chia thành những mô-đun nhỏ hơn có chức năng cụ thể. Những đặc điểm chung khác của các hệ điều hành Unix này đó là một hệ thống file dựa trên **inode**, các **pipeline** cho phép giao tiếp liên tiến trình, đều có một ngôn ngữ shell dùng để tương tác với hệ điều hành.

**\*nix**, hay Unix-like, là tập hợp các hệ điều hành giống Unix, nhưng không nhất thiết phải tuân theo tiêu chuẩn SUS. Tuy không có một quy tắc cụ thể nào về thế nào là một hệ điều hành Unix-like, nhưng chúng đều có chung đặc điểm là tuân theo "triết lý Unix". Eric S. Raymond và Rob Landley đã phân loại các hệ điều hành Unix-like làm ba loại:
* UNIX cơ bản: Các hệ điều hành này có liên hệ trực tiếp với mã nguồn gốc của AT&T. BSD là hệ điều hành loại này.
* UNIX thương mại: Những hệ điều hành này, thường là sản phẩm thương mại, được chứng nhận tiêu chuẩn SUS bởi Open Group (tổ chức quản lý tiêu chuẩn Unix).
* UNIX về mặt chức năng: Những hệ điều hành này tuy không đạt tiêu chuẩn SUS nhưng vận hành gần như theo triết lý Unix. Linux là một hệ điều hành thuộc loại này. 

**BSD**, hay Berkeley Software Distribution là một hệ điều hành đã ngừng phát triển được dựa trên Unix, do Đại học California, Berkeley phát triển. Sau này, BSD được dùng để chỉ một họ các hệ điều hành mã nguồn mở (như FreeBSD, OpenBSD,...) dựa trên hệ điều hành BSD. BSD được gọi là một hệ điều hành "giống Unix" (Unix-like) do trực tiếp xuất thân từ hệ điều hành gốc của AT&T nhưng không được công nhận theo tiêu chuẩn SUS. Ngoài ra, BSD đã vướng phải rắc rối pháp lý về mặt bản quyền với AT&T, dẫn đến việc các hệ điều hành khác như Linux, một hệ điều hành hoàn toàn không dính dáng đến hệ điều hành gốc của AT&T trở nên phát triển.

**Linux** là một hệ điều hành mã nguồn mở do Linus Torvald phát triển dựa trên bộ công cụ mã nguồn mở GNU (nên đôi khi hệ điều hành này được gọi là GNU/Linux). Điểm đặc biệt của Linux là hoàn toàn không dựa trên mã nguồn của các phần mềm thương mại, kể cả Unix, mà chỉ dựa vào các công cụ mã nguồn mở (tiêu biểu là GNU). Ngoài ra, dù được tạo điều kiện, nhưng Linux không hề tham gia vào tiêu chuẩn POSIX hay tiêu chuẩn SUS. Chính vì vậy, Linux được xếp loại vào hệ điều hành Unix-like. Ngày nay, Linux được phát hành thông qua các **bản phân phối (distro)** khác nhau do các bên thứ ba phát triển. Một điểm đặc biệt của Linux đó chính là tính mã nguồn mở của nó, giúp cho lập trình viên trên khắp thế giới có thể tự do đề xuất sửa đổi, sao chép, tham khảo tự do.

## 3. Alpine và Ubuntu
Alpine và Ubuntu là hai distro khác nhau của Linux. Ubuntu Linux là distro mã nguồn mở do Canonical phát triển, dựa trên một distro khác là Debian Linux. Alpine Linux là một distro mã nguồn mở khác, có đặc tính là nhỏ gọn, an toàn, thời gian khởi động nhanh, không dùng bộ công cụ phổ biến hơn của GNU (Nó dùng musl, BusyBox, và OpenRC thay vì glibc, GNU Core Utilities, và systemd). Chính nhờ những đặc điểm này nên Alpine hay được sử dụng cho các container hay hệ điều hành nhúng.

## 4. VNC
VNC - hay Virtual Network Computing (Hệ thống điện toán ảo qua mạng) là một hệ thống chia sẻ màn hình đồ họa sử dụng giao thức RFB (Remote Frame Buffer - Bộ đệm khung từ xa) để điều khiển từ xa một máy tính khác. Nó truyền đầu vào bàn phím và chuột từ máy tính này sang máy tính khác, chuyển tiếp những thay đổi đồ họa qua mạng.

VNC không phụ thuộc vào các nền tảng – ​​có máy khách và máy chủ cho nhiều hệ điều hành dựa trên GUI và cho Java. Nhiều máy khách có thể kết nối với máy chủ VNC cùng một lúc.

  
