# 📖*A Survey Of Content-Based Image Retrieval with high-level semantics*

## Thông tin bài báo
- **Tựa đề**: Một khảo sát về tra cứu ảnh dựa trên nội dung với ngữ nghĩa mức cao
- **Tác giả**: Ying Liu, Dengsheng Zhang, Guojun Lu, Wei-Ying Ma
- **Tạp chí**: Pattern Recognition, Volume 40, Issue 1, 2007, Pages 262–282
- **DOI**: [10.1016/j.patcog.2006.04.045](10.1016/j.patcog.2006.04.045)
- **Giấy phép**: © 2006 Pattern Recognition Society. Published by Elsevier Ltd
  
## Tóm tắt(Abtract)
  Để cải thiện độ chính xác tìm kiếm của các hệ thống tìm kiếm hình ảnh dựa trên nội dung, trọng tâm nghiên cứu đã chuyển từ việc thiết kế các thuật toán trích xuất đặc trưng cấp thấp tinh vi sang việc giảm ‘khoảng cách ngữ nghĩa’ giữa các đặc trưng hình ảnh và sự phong phú của ngữ nghĩa con người. Bài báo này cố gắng cung cấp một khảo sát toàn diện về những thành tựu kỹ thuật gần đây trong tìm kiếm hình ảnh dựa trên ngữ nghĩa cấp cao. Các ấn phẩm lớn gần đây được đưa vào khảo sát này, bao gồm các khía cạnh khác nhau của nghiên cứu trong lĩnh vực này, bao gồm trích xuất đặc trưng hình ảnh cấp thấp, đo lường độ tương đồng và suy ra các đặc trưng ngữ nghĩa cấp cao. Chúng tôi xác định năm loại kỹ thuật chính hiện đại trong việc thu hẹp ‘khoảng cách ngữ nghĩa’:
1. Sử dụng bản thể học đối tượng để định nghĩa các khái niệm cấp cao
2. Sử dụng các phường pháp học máy để liên kết các đặc trưng cấp thấp với các khái niệm truy vấn
3. Sử dụng phản hồi liên quan đẻ học ý định của người dùng
4. Tạo mẫu ngữ nghĩa đẻ hỗ trợ tìm kiếm hình ảnh cấp cao
5. Kết hợp các bằng chứng từ văn bản HTML và nội dung hình ảnh trên WWW

Cuối cùng, dựa trên công nghệ hiện có và nhu cầu từ các ứng dụng thực tế, một vài hướng nghiên cứu đầy hứa hẹn trong tương lai được đề xuất.

## 1. Giới thiệu
  Với sự phát triển của Internet và sự sẵn có của các thiết bị chụp ảnh như máy ảnh kỹ thuật số, máy quét hình ảnh, kích thước của bộ sưu tập hình ảnh kỹ thuật số đang tăng lên nhanh chóng. Các công cụ tìm kiếm, duyệt và truy xuất hình ảnh hiệu quả được yêu cầu bởi người dùng từ nhiều lĩnh vực khác nhau, bao gồm viễn thám, thời trang, phòng chống tội phạm, xuất bản, y học, kiến trúc, v.v. Với mục đích này, nhiều hệ thống tìm kiếm hình ảnh đa năng đã được phát triển. Có hai khuôn khổ: dựa trên văn bản và dựa trên nội dung. Phương pháp dựa trên văn bản có thể được truy ngược lại những năm 1970. Trong các hệ thống như vậy, hình ảnh được chú thích thủ công bằng các mô tả văn bản, sau đó được hệ thống quản lý cơ sở dữ liệu sử dụng để thực hiện tìm kiếm hình ảnh. Có hai nhược điểm với phương pháp này. Thứ nhất là cần một lượng đáng kể lao động của con người để chú thích thủ công. Thứ hai là sự không chính xác của chú thích do tính chủ quan của nhận thức con người. Để khắc phục những nhược điểm trên trong hệ thống tìm kiếm dựa trên văn bản, tìm kiếm hình ảnh dựa trên nội dung (CBIR) đã được giới thiệu vào đầu những năm 1980. Trong CBIR, hình ảnh được lập chỉ mục bằng nội dung hình ảnh của chúng, chẳng hạn như màu sắc, kết cấu, hình dạng. Một công trình tiên phong được xuất bản bởi Chang vào năm 1984, trong đó tác giả trình bày một phương pháp lập chỉ mục và trừu tượng hóa hình ảnh cho tìm kiếm cơ sở dữ liệu hình ảnh. Cơ sở dữ liệu hình ảnh bao gồm các đối tượng hình ảnh và các mối quan hệ hình ảnh. Để xây dựng chỉ mục hình ảnh, các thao tác trừu tượng hóa được thiết lập để thực hiện phân cụm và phân loại đối tượng hình ảnh. Trong thập kỷ qua, một vài sản phẩm thương mại và hệ thống nguyên mẫu thử nghiệm đã được phát triển, như QBIC, Photobook, Virage, VisualSEEK, Netra, SIMPLIcity. Các khảo sát toàn diện về CBIR có thể tìm thấy trong tài liệu tham khảo.

### 1.1. Khoảng cách ngữ nghĩa
Sự khác biệt cơ bản giữa các hệ thống tìm kiếm dựa trên nội dung và dựa trên văn bản là sự tương tác của con người là một phần không thể thiếu của hệ thống sau. Con người có xu hướng sử dụng các đặc trưng cấp cao (khái niệm), chẳng hạn như từ khóa, mô tả văn bản, để giải thích hình ảnh và đo lường độ tương đồng của chúng. Trong khi các đặc trưng được trích xuất tự động bằng kỹ thuật thị giác máy tính chủ yếu là các đặc trưng cấp thấp (màu sắc, kết cấu, hình dạng, bố cục không gian, v.v.). Nhìn chung, không có liên kết trực tiếp giữa các khái niệm cấp cao và các đặc trưng cấp thấp.
Mặc dù nhiều thuật toán tinh vi đã được thiết kế để mô tả các đặc trưng màu sắc, hình dạng và kết cấu, nhưng các thuật toán này không thể mô hình hóa đầy đủ ngữ nghĩa hình ảnh và có nhiều hạn chế khi xử lý các cơ sở dữ liệu hình ảnh có nội dung rộng. Các thử nghiệm sâu rộng trên các hệ thống CBIR cho thấy nội dung cấp thấp thường không thể mô tả các khái niệm ngữ nghĩa cấp cao trong tâm trí người dùng. Do đó, hiệu suất của CBIR vẫn còn cách xa kỳ vọng của người dùng. Trong tài liệu, Eakins đã đề cập đến ba cấp độ truy vấn trong CBIR.
- **Cấp độ 1**: Tìm kiếm theo các đặc trưng nguyên thủy như màu sắc, kết cấu, hình dạng hoặc vị  trí không gian của các yếu tố hình ảnh. Truy vấn điển hình là truy vấn theo ví dụ, ‘tìm những -bức ảnh giống như thế này’. 
- **Cấp độ 2**: Tìm kiếm các đối tượng thuộc loại nhất định được xác định bởi các đặc trưng dẫn xuất, với một mức độ suy luận logic. Ví dụ, ‘tìm một bức ảnh về một bông hoa’. 
- **Cấp độ 3**: Tìm kiếm theo các thuộc tính trừu tượng, liên quan đến một lượng lớn suy luận cấp cao về mục đích của các đối tượng hoặc cảnh được mô tả. Điều này bao gồm tìm kiếm các sự kiện có tên, các bức ảnh có ý nghĩa cảm xúc hoặc tôn giáo, v.v. Ví dụ truy vấn, ‘tìm những bức ảnh về một đám đông vui vẻ’.

Cấp độ 2 và 3 cùng nhau được gọi là tìm kiếm hình ảnh ngữ nghĩa, và khoảng cách giữa Cấp độ 1 và 2 được gọi là khoảng cách ngữ nghĩa. Cụ thể hơn, sự khác biệt giữa khả năng mô tả hạn chế của các đặc trưng hình ảnh cấp thấp và sự phong phú của ngữ nghĩa người dùng, được gọi là ‘khoảng cách ngữ nghĩa’. Người dùng trong tìm kiếm Cấp độ 1 thường được yêu cầu gửi một hình ảnh ví dụ hoặc bản phác thảo làm truy vấn. Nhưng nếu người dùng không có một hình ảnh ví dụ trong tay thì sao? Tìm kiếm hình ảnh ngữ nghĩa thuận tiện hơn cho người dùng vì nó hỗ trợ truy vấn bằng từ khóa hoặc bằng kết cấu.
Do đó, để hỗ trợ truy vấn bằng các khái niệm cấp cao, một hệ thống CBIR nên cung cấp sự hỗ trợ đầy đủ trong việc kết nối ‘khoảng cách ngữ nghĩa’ giữa các đặc trưng hình ảnh số và sự phong phú của ngữ nghĩa con người. 

### 1.2. Tìm kiếm hình ảnh dựa trên ngữ nghĩa cấp cao
Làm thế nào để chúng ta liên hệ các đặc trưng hình ảnh cấp thấp với ngữ nghĩa cấp cao? Khảo sát của chúng tôi cho thấy các kỹ thuật tiên tiến trong việc giảm ‘khoảng cách ngữ nghĩa’ chủ yếu bao gồm năm loại: (1) sử dụng bản thể học đối tượng để định nghĩa các khái niệm cấp cao, (2) sử dụng các công cụ học máy để liên kết các đặc trưng cấp thấp với các khái niệm truy vấn, (3) giới thiệu phản hồi liên quan (RF) vào vòng lặp tìm kiếm để liên tục học ý định của người dùng, (4) tạo mẫu ngữ nghĩa (ST) để hỗ trợ tìm kiếm hình ảnh cấp cao, (5) sử dụng cả nội dung hình ảnh trực quan và thông tin văn bản thu được từ Web để tìm kiếm hình ảnh trên WWW (Web).

Tìm kiếm ở Cấp độ 3 khó và ít phổ biến hơn. Tìm kiếm Cấp độ 3 có thể được tìm thấy trong các lĩnh vực cụ thể như bảo tàng nghệ thuật hoặc thư viện báo chí. Các hệ thống hiện tại chủ yếu thực hiện tìm kiếm ở Cấp độ 2. Có ba thành phần cơ bản trong các hệ thống này: 
1. trích xuất đặc trưng hình ảnh cấp thấp
2. đo lường độ tương đồng 
3. giảm ‘khoảng cách ngữ nghĩa’

Các khảo sát xuất sắc về trích xuất đặc trưng hình ảnh cấp thấp trong hệ thống CBIR có thể tìm thấy trong tài liệu. Trong bài báo này, chúng tôi tập trung vào CBIR với ngữ nghĩa cấp cao. Phần còn lại của bài báo được tổ chức như sau. Trong Phần 2, chúng tôi xem xét ngắn gọn các đặc trưng hình ảnh cấp thấp khác nhau được sử dụng trong các hệ thống CBIR dựa trên ngữ nghĩa cấp cao. Đo lường độ tương đồng hình ảnh cũng được thảo luận trong Phần 2. Phần 3 tập trung vào các phương pháp khác nhau trong việc thu hẹp ‘khoảng cách ngữ nghĩa’. Trong Phần 4, tập dữ liệu kiểm tra hình ảnh và đánh giá hiệu suất (PE) được thảo luận. Phần 5 bao gồm một vài vấn đề khác liên quan đến hệ thống CBIR được đề xuất là các hướng nghiên cứu đầy hứa hẹn. Cuối cùng, Phần 6 kết luận bài báo này.

## 2. Đặc trưng hình ảnh cấp thấp
Trích xuất đặc trưng hình ảnh cấp thấp là nền tảng của hệ thống CBIR. Để thực hiện CBIR, các đặc trưng hình ảnh có thể được trích xuất từ toàn bộ hình ảnh hoặc từ các vùng. Vì đã phát hiện ra rằng người dùng thường quan tâm đến các vùng cụ thể hơn là toàn bộ hình ảnh, hầu hết các hệ thống CBIR hiện tại đều dựa trên vùng. Tìm kiếm dựa trên đặc trưng toàn cục tương đối đơn giản hơn. Biểu diễn hình ảnh ở cấp độ vùng được chứng minh là gần hơn với hệ thống nhận thức của con người. Trong bài báo này, chúng tôi tập trung vào tìm kiếm hình ảnh dựa trên vùng (RBIR).

Để thực hiện RBIR, bước đầu tiên là thực hiện phân đoạn hình ảnh. Sau đó, các đặc trưng cấp thấp như màu sắc, kết cấu, hình dạng hoặc vị trí không gian có thể được trích xuất từ các vùng đã được phân đoạn. Độ tương đồng giữa hai hình ảnh được định nghĩa dựa trên các đặc trưng vùng. Phần này bao gồm mô tả ngắn gọn về ba phần này, tập trung vào những gì được sử dụng trong hệ thống RBIR với ngữ nghĩa cấp cao.

### 2.1. Phân đoạn hình ảnh
 Phân đoạn hình ảnh tự động là một nhiệm vụ khó khăn. Nhiều kỹ thuật đã được đề xuất trong quá khứ, chẳng hạn như tiến hóa đường cong, khuếch tán năng lượng và phân vùng đồ thị. Nhiều kỹ thuật phân đoạn hiện có hoạt động tốt cho

