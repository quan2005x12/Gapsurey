# Tổng quan về trích xuất hình ảnh dựa trên nội dung với ngữ nghĩa cấp cao
**Nguồn:** Liu, Y., Zhang, D., Lu, G., & Ma, W.-Y. (2007). A survey of content-based image retrieval with high-level semantics. Pattern Recognition, 40(2), 262–282.

### 1. Giới thiệu chung về Hệ thống trích xuất hình ảnh (Image Retrieval Systems)

Với sự phát triển của Internet và sự phổ biến của các thiết bị chụp ảnh kỹ thuật số, quy mô các bộ sưu tập hình ảnh kỹ thuật số ngày càng tăng nhanh chóng. Nhu cầu về các công cụ tìm kiếm, duyệt và trích xuất hình ảnh hiệu quả là rất lớn trong nhiều lĩnh vực như viễn thám, thời trang, phòng chống tội phạm, xuất bản, y học, kiến trúc, v.v. Có hai khung chính cho hệ thống trích xuất hình ảnh: **dựa trên văn bản** và **dựa trên nội dung**.

- **Trích xuất dựa trên văn bản**:
- Có từ những năm 1970.
- Hình ảnh được chú thích thủ công bằng các mô tả văn bản, sau đó được sử dụng bởi hệ thống quản lý cơ sở dữ liệu (DBMS).
    - **Nhược điểm**:"một lượng lớn sức lao động của con người là cần thiết để chú thích thủ công."
- "sự không chính xác của chú thích do tính chủ quan của nhận thức con người."
- **Trích xuất hình ảnh dựa trên nội dung (CBIR - Content-Based Image Retrieval)**:
-Được giới thiệu vào đầu những năm 1980 để khắc phục nhược điểm của phương pháp dựa trên văn bản.
-Hình ảnh được lập chỉ mục bằng nội dung thị giác của chúng, chẳng hạn như màu sắc, kết cấu và hình dạng.
-Các hệ thống tiên phong bao gồm QBIC, Photobook, Virage, VisualSEEK, Netra, SIMPLIcity.

### 2. Khoảng cách ngữ nghĩa (The Semantic Gap)

Sự khác biệt cơ bản giữa CBIR và các hệ thống dựa trên văn bản là "tương tác của con người là một phần không thể thiếu của hệ thống sau này". Con người có xu hướng sử dụng các tính năng cấp cao (khái niệm) để diễn giải hình ảnh và đo lường sự tương đồng, trong khi các tính năng được tự động trích xuất bằng kỹ thuật thị giác máy tính chủ yếu là các tính năng cấp thấp (màu sắc, kết cấu, hình dạng, bố cục không gian).
- **Định nghĩa khoảng cách ngữ nghĩa:** "Sự khác biệt giữa sức mạnh mô tả hạn chế của các tính năng hình ảnh cấp thấp và sự phong phú của ngữ nghĩa người dùng, được gọi là 'khoảng cách ngữ nghĩa'."
    - **Các cấp độ truy vấn trong CBIR (theo Eakins):Cấp 1**: Trích xuất bằng các tính năng nguyên thủy như màu sắc, kết cấu, hình dạng hoặc vị trí không gian của các yếu tố hình ảnh (ví dụ: "tìm ảnh giống như ảnh này").
    - **Cấp 2**: Trích xuất các đối tượng của loại nhất định được xác định bằng các tính năng dẫn xuất, với một mức độ suy luận logic (ví dụ: "tìm ảnh một bông hoa").
    - **Cấp 3**: Trích xuất bằng các thuộc tính trừu tượng, liên quan đến một lượng lớn suy luận cấp cao về mục đích của các đối tượng hoặc cảnh được mô tả (ví dụ: "tìm ảnh một đám đông vui vẻ").
- Khoảng cách giữa Cấp 1 và Cấp 2 được gọi là "khoảng cách ngữ nghĩa". Trích xuất ở Cấp 3 "khó khăn và ít phổ biến hơn". Các hệ thống hiện tại chủ yếu thực hiện trích xuất ở Cấp 2.
- Để hỗ trợ truy vấn bằng các khái niệm cấp cao, hệ thống CBIR phải "cung cấp hỗ trợ đầy đủ trong việc thu hẹp 'khoảng cách ngữ nghĩa' giữa các tính năng hình ảnh số và sự phong phú của ngữ nghĩa con người."
### 3. Các kỹ thuật giảm 'khoảng cách ngữ nghĩa'
Các kỹ thuật tiên tiến để giảm 'khoảng cách ngữ nghĩa' được phân loại thành năm loại chính:
- **Sử dụng bản thể luận đối tượng (Object Ontology) để định nghĩa các khái niệm cấp cao**:
    - Trong một số trường hợp, ngữ nghĩa có thể dễ dàng được suy ra từ ngôn ngữ hàng ngày (ví dụ: bầu trời có thể được mô tả là 'vùng trên cùng, đồng nhất và màu xanh').
    - Các mô tả này tạo thành một "từ vựng đơn giản, cái gọi là 'bản thể luận đối tượng' cung cấp một định nghĩa định tính về các khái niệm truy vấn cấp cao."
    - Ví dụ: định nghĩa 'bầu trời' là vùng 'màu xanh nhạt' (màu sắc), 'đồng nhất' (kết cấu), và 'trên cùng' (vị trí không gian).
    - "Lượng tử hóa màu sắc và tính năng kết cấu là chìa khóa trong các hệ thống như vậy." Mô hình đặt tên màu (ví dụ: CNS của Berk, Brownston và Kaufman) được sử dụng để liên hệ không gian màu số với tên màu ngữ nghĩa.
    -Hệ thống đặt tên kết cấu khó hơn và chưa có hệ thống chuẩn hóa nào.
- **Sử dụng phương pháp học máy (Machine Learning) để liên kết các tính năng cấp thấp với các khái niệm truy vấn**:
        - **Học có giám sát (Supervised Learning)**:Mục tiêu là dự đoán giá trị của một biện pháp kết quả (ví dụ: nhãn danh mục ngữ nghĩa) dựa trên một tập hợp các biện pháp đầu vào.
        - Các kỹ thuật phổ biến: **Máy vector hỗ trợ (SVM), Bộ phân loại Bayes, Mạng nơ-ron, Cây quyết định (Decision Tree)**.
        - **SVM**: Được thiết kế cho phân loại nhị phân, tìm một siêu mặt phẳng tối ưu để tách dữ liệu. Có hiệu suất tổng quát hóa cao và hoạt động tốt với tập huấn luyện nhỏ.
        - **Bayes**: Sử dụng bộ phân loại Bayes nhị phân để nắm bắt các khái niệm cấp cao của cảnh tự nhiên từ các tính năng hình ảnh cấp thấp.
    - **Cây quyết định**: Đơn giản về mặt khái niệm, mạnh mẽ đối với các tính năng đầu vào không đầy đủ và nhiễu. Có thể dễ dàng chuyển thành các tập luật.
        - **Học không giám sát** (Unsupervised Learning):Mục tiêu là tìm ra cách các tính năng đầu vào được tổ chức hoặc phân cụm.
        - Kỹ thuật phổ biến: **Phân cụm hình ảnh (Image Clustering), bao gồm k-means clustering và Normalized Cut (NCut)**.
    - NCut được chứng minh là thành công trong phân cụm dữ liệu manifold nhưng không thể tạo ra một hàm ánh xạ rõ ràng cho dữ liệu mới. Phương pháp Locality Preserving Clustering (LPC) được đề xuất để khắc phục.
    - **Kỹ thuật nhận dạng đối tượng**: Sử dụng các thuật toán nhận dạng đối tượng để trích xuất ngữ nghĩa, mô hình đối tượng như các chòm sao linh hoạt của các bộ phận.
- **Giới thiệu phản hồi liên quan (Relevance Feedback - RF) vào vòng lặp trích xuất để liên tục học ý định của người dùng**:
    - RF là một công cụ mạnh mẽ "được sử dụng theo truyền thống trong các hệ thống trích xuất thông tin dựa trên văn bản".
    - Được giới thiệu vào CBIR vào giữa những năm 1990 để "đưa người dùng vào vòng lặp trích xuất để giảm 'khoảng cách ngữ nghĩa' giữa những gì truy vấn đại diện (tính năng cấp thấp) và những gì người dùng nghĩ."
        - **Quy trình điển hình**: Hệ thống cung cấp kết quả trích xuất ban đầu.
        - Người dùng đánh giá kết quả là liên quan (ví dụ tích cực)/không liên quan (ví dụ tiêu cực).
    - Thuật toán học máy được áp dụng để học phản hồi của người dùng, sau đó quay lại bước 2 cho đến khi người dùng hài lòng.
        - *8Các phương pháp phổ biến trong RF:Tái trọng số (Re-weighting)*8: Điều chỉnh trọng số của các tính năng cấp thấp để phù hợp với nhu cầu của người dùng.
        - **Di chuyển điểm truy vấn (Query-point-movement - QPM)**: Cải thiện ước tính điểm truy vấn bằng cách di chuyển nó về phía các ví dụ tích cực và ra xa các ví dụ tiêu cực (thường dùng công thức Rocchio).
    - Sử dụng các kỹ thuật học máy như SVM và Cây quyết định trong vòng lặp RF để phân loại hình ảnh.
    - Hầu hết các hệ thống RF hiện tại chỉ sử dụng các tính năng hình ảnh cấp thấp. Một số hệ thống (ví dụ: 'iFind') thực hiện RF trên cả tính năng cấp thấp và nội dung ngữ nghĩa (từ khóa) của hình ảnh.
- **Tạo mẫu ngữ nghĩa (Semantic Template - ST) để hỗ trợ trích xuất hình ảnh cấp cao**:
    - ST là "một bản đồ giữa khái niệm cấp cao và các tính năng hình ảnh cấp thấp."
    -Thường được định nghĩa là "tính năng 'đại diện' của một khái niệm được tính toán từ một bộ sưu tập hình ảnh mẫu."
    - **Ưu điểm**: Có thể tự động tạo ra trong quá trình RF, người dùng không cần hiểu sâu về các tính năng hình ảnh.
    - Ví dụ: hệ thống trong [70] tạo ST tự động dựa trên centroid tính năng của các hình ảnh liên quan sau vài lần lặp RF. WordNet được sử dụng để xây dựng mạng lưới ST.
    - Một ví dụ khác sử dụng khuôn mẫu vùng tổng hợp (Composite Region Templates - CRTs) để giải mã ngữ nghĩa hình ảnh bằng cách xác định các sắp xếp không gian nguyên mẫu của các vùng trong hình ảnh.
- **Kết hợp bằng chứng từ văn bản HTML và nội dung thị giác của hình ảnh cho trích xuất hình ảnh trên WWW (Web Image Retrieval)**:
    - Một lợi thế trong trích xuất hình ảnh Web là có sẵn "một số thông tin bổ sung trên Web để tạo điều kiện cho trích xuất hình ảnh dựa trên ngữ nghĩa." Ví dụ: URL, tiêu đề hình ảnh, thẻ ALT, văn bản mô tả xung quanh hình ảnh, siêu liên kết.
    - Các công cụ tìm kiếm hình ảnh Web hiện có (ví dụ: Google, AltaVista) chỉ tìm kiếm dựa trên bằng chứng văn bản, dẫn đến độ chính xác trích xuất kém.
    - Các nhà nghiên cứu đang nỗ lực "kết hợp các bằng chứng từ thông tin văn bản và nội dung hình ảnh thị giác."
    - Các phương pháp bao gồm khung đào tạo cùng bootstrapping (co-training) để tự động chú thích hình ảnh Web và các hệ thống phân cụm kết quả tìm kiếm hình ảnh Web bằng cách sử dụng phân tích liên kết cấp khối (block-level link analysis) cùng với các tính năng thị giác và văn bản.
### 4. Tính năng hình ảnh cấp thấp

Trích xuất tính năng hình ảnh cấp thấp là cơ sở của các hệ thống CBIR. Hầu hết các hệ thống CBIR hiện tại đều dựa trên vùng (region-based), vì "người dùng thường quan tâm đến các vùng cụ thể hơn là toàn bộ hình ảnh".
- **Phân đoạn hình ảnh (Image Segmentation)**:
    - Bước đầu tiên trong RBIR.
    - Các kỹ thuật đa dạng: curve evolution, energy diffusion, graph partitioning.
    - "JSEG" và "Blobworld" là các thuật toán phân đoạn được sử dụng rộng rãi nhất, tạo ra các vùng đồng nhất về màu sắc và kết cấu.
    - Một số hệ thống thiết kế các phân đoạn riêng của họ (ví dụ: dựa trên k-means clustering với ràng buộc kết nối - KMCC).
- **Các tính năng hình ảnh cấp thấp**:
        - **Tính năng màu sắc (Color Feature)**:Một trong những tính năng được sử dụng rộng rãi nhất.
        - Không gian màu phổ biến: RGB, LAB, LUV, HSV (HSL), YCrCb, HMMD.
        - Mô tả màu phổ biến: ma trận hiệp phương sai màu, biểu đồ màu, mômen màu, vector kết hợp màu.
    - Để liên kết màu sắc vùng với tên màu ngữ nghĩa cấp cao, một số hệ thống sử dụng màu trung bình hoặc màu chủ đạo (dominant color) của một vùng.
        - **Tính năng kết cấu (Texture Feature)**:Cung cấp thông tin quan trọng trong phân loại hình ảnh (ví dụ: da trái cây, mây, cây cối).
        - Các tính năng phổ biến: tính năng quang phổ (Gabor filtering, wavelet transform), tính năng thống kê (Tamura texture features: coarseness, directionality, regularity, contrast, line-likeness, roughness), wold features (periodicity, randomness, directionality).
        - Gabor và Wavelet features được sử dụng rộng rãi và phù hợp với nghiên cứu thị giác con người.
        - Việc trích xuất tính năng kết cấu từ các vùng hình dạng tùy ý là một thách thức.
    - Mô tả biểu đồ cạnh (Edge Histogram Descriptor - EHD) cũng hiệu quả cho hình ảnh tự nhiên.
        - **Hình dạng (Shape)**:Quan trọng đối với các hình ảnh cụ thể theo miền (ví dụ: các đối tượng nhân tạo).
        - Các tính năng phổ biến: tỷ lệ khung hình, độ tròn, bộ mô tả Fourier, bất biến mômen.
    - Bộ mô tả không gian tỷ lệ đường cong (Curvature Scale Space - CSS) bất biến với dịch chuyển, tỷ lệ và xoay nhưng nhạy cảm với biến dạng chung.
        - **Vị trí không gian (Spatial Location)**:Hữu ích trong phân loại vùng (ví dụ: bầu trời thường ở trên cùng, biển ở dưới cùng).
        - Có thể được định nghĩa đơn giản là 'trên, dưới, trên cùng' hoặc sử dụng centroid vùng và hình chữ nhật bao quanh tối thiểu.
    - **Mối quan hệ không gian** tương đối quan trọng hơn vị trí không gian tuyệt đối trong việc suy ra các tính năng ngữ nghĩa (ví dụ: 2D-string, mô hình ngữ cảnh không gian xem xét 6 mối quan hệ giữa các cặp vùng).
### 5. Đo lường sự tương đồng (Similarity Measure)

Đo lường sự tương đồng được thực hiện ở hai cấp độ: cấp độ vùng và cấp độ hình ảnh.
- Cấp độ vùng:
    - Hầu hết các nhà nghiên cứu sử dụng **metric kiểu Minkowski** để định nghĩa khoảng cách vùng (Euclidean distance, Manhattan distance, weighted Minkowski distance).
    - Các khoảng cách khác: Canberra distance, angular distance, Czekanowski coefficient, inner product, dice coefficient, cosine coefficient, Jaccard coefficient.
    - "mặc dù metric Minkowski được sử dụng rộng rãi trong các hệ thống hiện tại để đo khoảng cách vùng, các thí nghiệm chuyên sâu cho thấy nó không hiệu quả lắm trong việc mô hình hóa sự tương đồng nhận thức."
    - Đã có một số nỗ lực để giải quyết vấn đề này, ví dụ: **hàm khoảng cách một phần động (Dynamic Partial Distance Function - DPF)**.
- Cấp độ hình ảnh:
    - **Ghép một-một (One-One match)**: Mỗi vùng trong hình ảnh truy vấn chỉ được ghép với một vùng trong hình ảnh đích.
    - **Ghép nhiều-nhiều (Many-Many match)**: Mỗi vùng trong hình ảnh truy vấn có thể ghép với nhiều vùng trong hình ảnh đích. Khoảng cách dịch chuyển Trái đất (Earth Mover’ Distance - EMD) là một phương pháp được sử dụng rộng rãi.
    - **Sơ đồ ghép nối vùng tích hợp (Integrated Region Matching - IRM)** cho phép ghép một vùng của một hình ảnh với nhiều vùng của hình ảnh khác.
    - Các phương pháp khác bao gồm khoảng cách manifold đa phân giải (Multiresolution Manifold Distance - MRMD) và khung ra quyết định đa cấp (multilevel decision making process) sử dụng logic mờ để kết hợp các loại tính năng.
### 6. Cơ sở dữ liệu hình ảnh và đánh giá hiệu suất

Hiện tại "chưa có dữ liệu thử nghiệm và mô hình đánh giá hiệu suất tiêu chuẩn" cho các hệ thống CBIR.
- Cơ sở dữ liệu hình ảnh:
    - Hơn một nửa số hệ thống được khảo sát sử dụng một tập con của bộ dữ liệu hình ảnh Corel.
    - **Corel**: Lớn, nội dung đa dạng, có chú thích thủ công. Tuy nhiên, một số nhà nghiên cứu cho rằng nó "không phù hợp để đánh giá hiệu suất CBIR vì ground truth (nhãn danh mục) thường quá cấp cao để hữu ích trong phân tích hiệu suất".
    - Các hình ảnh cảnh tự nhiên thường được sử dụng làm cơ sở thử nghiệm để trích xuất ngữ nghĩa vì chúng dễ phân tích hơn (các loại đối tượng hạn chế, tính năng hình dạng ít quan trọng hơn).
    - **TREC video retrieval evaluation (TRECVID)** cung cấp dữ liệu thử nghiệm tiêu chuẩn cho trích xuất video.
- **Từ vựng (Vocabulary)**:
    -Tìm một từ vựng "lý tưởng" đại diện cho ngữ nghĩa phong phú của hình ảnh là một nhiệm vụ khó khăn.
    - Các nghiên cứu đã cố gắng xác định các danh mục ngữ nghĩa quan trọng (ví dụ: chân dung, đám đông, cảnh thành phố) và các tính năng cấp thấp mô tả chúng.
    - "WordNet" là một hệ thống tham chiếu từ vựng trực tuyến tổ chức các từ tiếng Anh thành các tập hợp từ đồng nghĩa.
    - Từ vựng được sử dụng phụ thuộc vào bộ dữ liệu hình ảnh. Đối với hình ảnh cảnh tự nhiên, thường có khoảng 10-20 danh mục (nước, bầu trời, cây cối...).
    - Đối với trích xuất cơ sở dữ liệu hình ảnh trong thế giới thực, "từ vựng nhỏ như vậy là không đủ". Con người có thể nhận ra khoảng 5000–30.000 danh mục đối tượng.
- **Đánh giá hiệu suất**:
- Thường sử dụng **Độ chính xác (Precision - Pr) và Độ thu hồi (Recall - Re).**
        - Re = Nr/Nt (Nr: số hình ảnh liên quan được trích xuất; Nt: tổng số hình ảnh liên quan có sẵn).
    - Pr = Nr/K (K: tổng số hình ảnh được trích xuất).
    - Đường cong Pr(Re) thường được sử dụng.
    - **Đường cong precision-scope (Pr(Sc))** cũng được sử dụng, trong đó Sc là số hình ảnh được trả về. Pr(Sc) = Nr/Sc.
    - *8Đo lường thứ hạng (Rank - Ra)** là thứ hạng trung bình của các hình ảnh được trích xuất. Thứ hạng càng nhỏ, hiệu suất càng tốt.
    - Việc so sánh khách quan hiệu suất của các hệ thống CBIR là khó khăn nếu không nêu rõ hình ảnh thử nghiệm, truy vấn và các tham số đánh giá.
### 7. Các vấn đề nghiên cứu trong tương lai
- **Thiết kế ngôn ngữ truy vấn (Query Language Design)**:
    - "ngôn ngữ truy vấn tạo thành một con đường quan trọng cho công việc tiếp theo trong việc phát triển các cơ chế truy vấn CBIR."
    - Ít công trình gần đây giải quyết vấn đề này.
    - Ví dụ: ngôn ngữ truy vấn OQUEL hỗ trợ các truy vấn bằng cụm từ khóa đơn giản hoặc phức tạp.
- **Lập chỉ mục tính năng hình ảnh đa chiều (High-dimensional Indexing of Image Features)**:
    - Tốc độ trích xuất sẽ là một yếu tố quan trọng khi kích thước cơ sở dữ liệu tăng nhanh.
    - Các thuật toán lập chỉ mục truyền thống (k-d-b tree, quad-tree, R-tree) không phù hợp với không gian tính năng hình ảnh đa chiều (thường lên đến hàng chục hoặc hàng trăm chiều) do "lời nguyền về chiều (curse of dimensionality)".
    - Các thuật toán lập chỉ mục đa chiều như X-tree, VA-file, i-Distance đã được giới thiệu nhưng không xem xét các thuộc tính cụ thể của tính năng hình ảnh.
    - Cần nhiều công trình hơn để thiết kế các thuật toán lập chỉ mục hiệu quả cho cơ sở dữ liệu hình ảnh trong thế giới thực.
- **Mở rộng DBMS tiêu chuẩn cho trích xuất hình ảnh (Standard DBMS Extended for Image Retrieval)**:
    - "khi cơ sở dữ liệu hình ảnh lớn xuất hiện, sự kết nối giữa CBIR và hệ thống quản lý cơ sở dữ liệu (DBMS) là không thể tránh khỏi."
    - Việc tích hợp CBIR vào DBMS giúp giải quyết vấn đề toàn vẹn dữ liệu hình ảnh, cho phép cập nhật động và tích hợp tự nhiên với các tính năng từ các nguồn khác.
- **Bộ thử nghiệm hình ảnh tiêu chuẩn và mô hình đánh giá hiệu suất (Standard Image Testbed and Performance Evaluation Model)**:
    - "một cơ sở dữ liệu hình ảnh tiêu chuẩn với một tập truy vấn và mô hình đo lường hiệu suất tương ứng là rất cần thiết cho việc đánh giá hiệu suất khách quan của các hệ thống CBIR."
### 8. Kết luận

- Nghiên cứu CBIR đã chuyển trọng tâm từ xử lý hình ảnh và trích xuất tính năng cấp thấp sang giảm "khoảng cách ngữ nghĩa" giữa các tính năng thị giác cấp thấp và ngữ nghĩa phong phú của con người.
- Năm loại kỹ thuật chính để thu hẹp khoảng cách ngữ nghĩa đã được xác định: bản thể luận đối tượng, học máy, phản hồi liên quan, mẫu ngữ nghĩa và trích xuất hình ảnh Web.
- "Mặc dù đã có một lượng lớn công việc được thực hiện trong lĩnh vực này, cho đến nay vẫn chưa có một cách tiếp cận chung nào cho trích xuất hình ảnh dựa trên ngữ nghĩa cấp cao."
- Các hệ thống hiện tại chủ yếu tập trung vào trích xuất ở Cấp 2, và "vẫn chưa có giải pháp tốt cho trích xuất Cấp 3."
- Việc đo lường sự tương đồng hình ảnh dựa trên metric Minkowski thông thường không thể mô hình hóa hiệu quả nhận thức của con người, cần nghiên cứu thêm về đo lường sự tương đồng nhận thức.
- Một hệ thống CBIR hoàn chỉnh với ngữ nghĩa cấp cao "đòi hỏi sự tích hợp của trích xuất tính năng cấp thấp nổi bật, học ngữ nghĩa cấp cao hiệu quả, giao diện người dùng thân thiện và công cụ lập chỉ mục hiệu quả."
