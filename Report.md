# Bài tập Tết học phần Kiến trúc phần mềm INT3105 1
## 1. Docker và Docker-compose
### 1.1. Công nghệ ảo hóa (virtualization) và container hóa (containerization)

### 1.2. Giới thiệu về Docker
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

  
