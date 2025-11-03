# 📊 Phân Tích Phân Khúc Khách Hàng Bằng Mô Hình RFM và K-Means

Dự án này thực hiện **phân tích dữ liệu giao dịch** của một công ty bán lẻ trực tuyến để **phân khúc khách hàng** dựa trên hành vi mua sắm.  
Mục tiêu là **hiểu rõ hơn hành vi khách hàng**, từ đó đưa ra **chiến lược marketing và chăm sóc phù hợp** cho từng nhóm.

---

## 🧩 Tổng quan dự án

Phân khúc khách hàng là bước quan trọng giúp doanh nghiệp:
- Hiểu rõ từng nhóm khách hàng.
- Đưa ra chương trình khuyến mãi và chiến dịch marketing đúng đối tượng.
- Gia tăng doanh thu và mức độ trung thành của khách hàng.

Dự án sử dụng mô hình **RFM (Recency - Frequency - Monetary)** kết hợp với thuật toán **K-Means Clustering** để **tự động nhóm khách hàng có hành vi tương đồng**.

---

## 🧠 Mô hình RFM là gì?

| Thành phần | Ý nghĩa | Giải thích |
|-------------|----------|------------|
| **R - Recency** | Gần nhất | Thời gian kể từ lần mua hàng gần nhất của khách hàng. |
| **F - Frequency** | Tần suất | Số lần khách hàng mua hàng trong giai đoạn phân tích. |
| **M - Monetary** | Giá trị | Tổng số tiền khách hàng đã chi tiêu. |

Ba chỉ số này giúp đo lường **mức độ trung thành và giá trị** của từng khách hàng đối với doanh nghiệp.

Sau khi tính toán R, F, M cho mỗi khách hàng, dữ liệu được đưa vào **thuật toán K-Means** để tự động phân nhóm.

---

## 📚 Tập dữ liệu

Dự án sử dụng tập dữ liệu **[Online Retail II Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail+ii)**  
từ **UCI Machine Learning Repository**, gồm các giao dịch từ **01/12/2009 đến 09/12/2010** của một công ty bán lẻ tại Vương quốc Anh.

**Cấu trúc dữ liệu:**

| Cột | Mô tả |
|-----|--------|
| Invoice | Mã số hóa đơn |
| StockCode | Mã sản phẩm |
| Description | Mô tả sản phẩm |
| Quantity | Số lượng bán |
| InvoiceDate | Ngày lập hóa đơn |
| Price | Đơn giá |
| Customer ID | Mã khách hàng |
| Country | Quốc gia của khách hàng |

---

## 🛠️ Phương pháp thực hiện

### 1️⃣ Tiền xử lý & Làm sạch dữ liệu
- Loại bỏ các giá trị thiếu, đặc biệt là **Customer ID**.  
- Loại bỏ các **giao dịch trả hàng** (Quantity âm).  
- Loại bỏ các **mã hóa đơn hoặc sản phẩm không hợp lệ**.  
- Lọc dữ liệu chỉ giữ lại **các giao dịch hợp lệ**.

---

### 2️⃣ Tính toán chỉ số RFM
- Tính **Recency** = ngày hiện tại – ngày mua hàng gần nhất.  
- Tính **Frequency** = số lượng hóa đơn của mỗi khách hàng.  
- Tính **Monetary** = tổng tiền chi tiêu.  

---

### 3️⃣ Chuẩn hóa dữ liệu & Áp dụng K-Means
- Dữ liệu RFM được chuẩn hóa bằng **MinMaxScaler và StandardScaler**.  
- Áp dụng thuật toán **K-Means Clustering** để phân chia khách hàng thành các nhóm.  
- Xác định số cụm **k tối ưu** bằng phương pháp **Elbow Method**.

---

### 4️⃣ Phân tích & trực quan hóa kết quả
- Trực quan hóa cụm khách hàng bằng **biểu đồ 3D RFM** và **biểu đồ thanh so sánh**.  
- Phân tích đặc trưng từng cụm: nhóm khách hàng trung thành, tiềm năng, mới, rời bỏ,...

---

## 🚀 Cách sử dụng

1️⃣ **Clone repository này về máy:**
```
git clone https://github.com/lowtech1/Customer_Segmentation.git
cd Customer_Segmentation
```
2️⃣ **Cài đặt môi trường & thư viện cần thiết**

Trước tiên, hãy đảm bảo rằng bạn đã cài đặt **Python 3.8+** và **pip** trên hệ thống.  
Sau đó, chạy các lệnh dưới đây để thiết lập môi trường làm việc.

```bash
# Tạo môi trường ảo (khuyến nghị)
python -m venv venv

# Kích hoạt môi trường
# Trên Windows:
venv\Scripts\activate
# Trên macOS/Linux:
source venv/bin/activate
```
## 3️⃣ Chạy Notebook Phân Tích

Sau khi đã cài đặt môi trường và chuẩn bị dữ liệu, bạn có thể bắt đầu chạy notebook để thực hiện phân tích và phân cụm khách hàng.

### 🔹 Cách chạy notebook:
Mở terminal (hoặc command prompt) và thực thi lệnh:

```bash
jupyter notebook notebooks/DA2.ipynb
# Cài đặt các thư viện cần thiết
pip install -r requirements.txt
```
## 📁 Cấu trúc thư mục
```bash
RFM-KMeans-CustomerSegmentation/
├── data/
│   ├── online_retail_II.csv        # Dữ liệu gốc (raw data)
│   └── processed_rfm.csv           # Dữ liệu sau khi tính RFM
│
├── notebooks/
│   └── DA2.ipynb                   # Notebook chính để phân tích
│
├── src/
│   ├── rfm_analysis.py             # Xử lý và tính toán chỉ số RFM
│   ├── clustering.py               # Thuật toán K-Means
│   ├── visualization.py            # Vẽ biểu đồ trực quan
│   └── utils.py                    # Các hàm tiện ích dùng chung
│
├── requirements.txt                # Danh sách thư viện cần cài đặt
├── .gitignore                      # Loại trừ file không cần thiết
└── README.md                       # Tài liệu mô tả dự án

---
```
## 👨‍💻 Tác Giả

**👤 Tên:** Phạm Hữu Nhân  
**💼 Vai trò:** Sinh viên nghiên cứu & phát triển mô hình phân tích dữ liệu  
**🏫 Trường:** Đại học Kỹ thuật - Công nghệ Cần Thơ (CTUT)  
**📧 Email:** [phnhan.bluesky@gmail.com](mailto:phnhan.bluesky@gmail.com)  
**🌐 GitHub:** [https://github.com/lowtech1](https://github.com/lowtech1)  
**💬 Liên hệ:** Nếu bạn quan tâm đến phân tích dữ liệu, machine learning hoặc muốn hợp tác, hãy liên hệ với mình nhé!  

---

