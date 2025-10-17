📊 Phân Tích Phân Khúc Khách Hàng Bằng Mô Hình RFM và K-Means
Dự án này thực hiện phân tích dữ liệu giao dịch của một công ty bán lẻ trực tuyến để phân khúc khách hàng. Mục tiêu là để hiểu rõ hơn về hành vi của khách hàng và từ đó đưa ra các chiến lược kinh doanh và marketing phù hợp cho từng nhóm.

---------------------------------------------------------------------------------------------------------------------------------

📝 Mô tả dự án
Dự án sử dụng mô hình RFM (Recency, Frequency, Monetary) để đánh giá giá trị của khách hàng dựa trên:

Recency (R): Lần cuối cùng khách hàng mua hàng là khi nào?

Frequency (F): Tần suất mua hàng của khách hàng là bao nhiêu?

Monetary (M): Khách hàng đã chi bao nhiêu tiền?

Sau đó, thuật toán K-Means Clustering được áp dụng trên các đặc trưng RFM để tự động phân nhóm các khách hàng có hành vi tương tự nhau.

---------------------------------------------------------------------------------------------------------------------------------

📚 Tập dữ liệu
Dự án sử dụng tập dữ liệu "Online Retail II" từ UCI Machine Learning Repository. Dữ liệu này chứa các giao dịch diễn ra từ ngày 01/12/2009 đến 09/12/2010 của một công ty bán lẻ trực tuyến có trụ sở tại Vương quốc Anh.

Invoice: Mã số hóa đơn.

StockCode: Mã sản phẩm.

Description: Mô tả sản phẩm.

Quantity: Số lượng.

InvoiceDate: Ngày lập hóa đơn.

Price: Đơn giá.

Customer ID: Mã khách hàng.

Country: Quốc gia.

---------------------------------------------------------------------------------------------------------------------------------

🛠️ Phương pháp thực hiện
Tiền xử lý và Làm sạch dữ liệu:

Loại bỏ các giá trị bị thiếu, đặc biệt là Customer ID.

Xử lý các giao dịch trả hàng (có Quantity âm).

Loại bỏ các dòng dữ liệu không hợp lệ (hóa đơn, mã sản phẩm bất thường).

Lọc bỏ các giao dịch có đơn giá bằng 0.

Phân tích RFM:

Tính toán các giá trị Recency, Frequency, và Monetary cho mỗi khách hàng.

Gán điểm RFM (từ 1 đến 5) cho từng chỉ số.

Phân khách hàng vào các nhóm như: Champions, Loyal Customers, Potential Loyalist, New Customers, Promising, Needing Attention, About to Sleep, At Risk, Can't Lose Them, Hibernating.

Phân cụm bằng K-Means:

Chuẩn hóa dữ liệu RFM.

Sử dụng phương pháp "khuỷu tay" (Elbow Method) và chỉ số Silhouette để tìm ra số cụm (cluster) tối ưu.

Áp dụng thuật toán K-Means để phân khách hàng vào các cụm.

Trực quan hóa các cụm khách hàng để phân tích đặc điểm của từng nhóm.

---------------------------------------------------------------------------------------------------------------------------------

🔧 Yêu cầu cài đặt
Để chạy dự án này, bạn cần cài đặt các thư viện Python sau:

Bash

pip install pandas numpy matplotlib seaborn scikit-learn

--------------------------------------------------------------------------------------------------------------------------------

🚀 Cách sử dụng
Clone repository này về máy của bạn.

Đảm bảo bạn đã cài đặt các thư viện cần thiết được liệt kê ở trên.

Mở tệp Jupyter Notebook DA2.ipynb bằng Jupyter Notebook hoặc Jupyter Lab.

Chạy các cell trong notebook để thực hiện lại quá trình phân tích.

--------------------------------------------------------------------------------------------------------------------------------

📈 Kết quả
Dự án đã xác định được các phân khúc khách hàng khác nhau với những đặc điểm riêng biệt về hành vi mua sắm. Biểu đồ dưới đây cho thấy số lượng khách hàng trong mỗi cụm và giá trị trung bình của các chỉ số RFM:

(Đây là hình ảnh minh họa, bạn có thể thay thế bằng biểu đồ thực tế từ notebook của mình)

Các thông tin này có thể được sử dụng để:

Phát triển các chiến dịch marketing cá nhân hóa.

Cải thiện dịch vụ chăm sóc khách hàng.

Tối ưu hóa chiến lược giữ chân khách hàng.
