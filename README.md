# PHÂN TÍCH RỦI RO – LỢI NHUẬN VÀ XÂY DỰNG DANH MỤC ĐẦU TƯ HNX30

**Dự án cá nhân | Python | Data Analysis | Financial Analytics**

## 1. Giới thiệu dự án

Dự án tập trung phân tích mối quan hệ giữa rủi ro và lợi nhuận của 30 cổ phiếu thuộc nhóm HNX30 trong giai đoạn 2020–2024.

Thông qua việc ứng dụng Python và các phương pháp phân tích định lượng, dự án thực hiện thu thập, xử lý dữ liệu, phân tích thống kê, dự báo lợi suất và xây dựng danh mục đầu tư dựa trên hệ số Beta.

**Mục tiêu chính:**
- Thu thập và xử lý dữ liệu lịch sử giá của 30 cổ phiếu HNX30.
- Phân tích lợi suất và mức độ biến động của các cổ phiếu.
- Ứng dụng mô hình ARIMA để dự báo lợi suất cổ phiếu CEO.
- Ước lượng hệ số Beta bằng mô hình CAPM.
- Xây dựng và đánh giá hai danh mục đầu tư theo mức độ nhạy cảm với thị trường.

## 2. Công nghệ sử dụng

| Công nghệ | Mục đích |
|---|---|
| Python | Ngôn ngữ lập trình chính |
| Pandas, NumPy | Xử lý và phân tích dữ liệu |
| Requests | Thu thập dữ liệu từ API |
| Statsmodels | Phân tích thống kê, ARIMA và hồi quy OLS |
| Matplotlib, Seaborn | Trực quan hóa dữ liệu |
| Jupyter Notebook | Môi trường thực hiện và trình bày kết quả |

## 3. Nguồn dữ liệu

Dự án sử dụng dữ liệu lịch sử từ hai nguồn:

- **CaféF:** Dữ liệu giao dịch của 30 cổ phiếu HNX30.
- **Investing.com:** Dữ liệu lịch sử chỉ số HNX-Index.

**Giai đoạn nghiên cứu:** 01/01/2020 – 31/12/2024.

Dữ liệu được chuẩn hóa theo các trường: Ticker, Date, Open, High, Low, Close và Volume.

## 4. Quy trình thực hiện

### Bước 1: Thu thập và tiền xử lý dữ liệu

- Thu thập dữ liệu giá cổ phiếu bằng Python.
- Chuẩn hóa định dạng ngày tháng và giá trị số.
- Xử lý dữ liệu thiếu và các phiên không có giao dịch.
- Đồng bộ dữ liệu cổ phiếu với chỉ số HNX-Index.
- Tính toán lợi suất phục vụ phân tích.

### Bước 2: Phân tích khám phá dữ liệu (EDA)

- Thực hiện thống kê mô tả lợi suất.
- Phân tích phân phối và mức độ biến động.
- Xây dựng ma trận tương quan giữa các cổ phiếu và thị trường.
- Trực quan hóa dữ liệu thông qua biểu đồ phân phối và heatmap.

### Bước 3: Dự báo lợi suất bằng ARIMA

Lựa chọn cổ phiếu CEO để thực hiện dự báo lợi suất tháng.

Quy trình bao gồm:

1. Kiểm định tính dừng bằng ADF Test.
2. Lựa chọn tham số ARIMA theo tiêu chí AIC.
3. Ước lượng mô hình ARIMA.
4. Kiểm định phần dư bằng Ljung-Box.
5. Dự báo lợi suất tháng tiếp theo.

**Kết quả:** Mô hình được lựa chọn là ARIMA(0,0,1), với lợi suất dự báo tháng 01/2025 của cổ phiếu CEO khoảng 2,97%.

### Bước 4: Ước lượng hệ số Beta

Sử dụng mô hình CAPM và hồi quy OLS để đánh giá mức độ nhạy cảm của lợi suất từng cổ phiếu với chỉ số HNX-Index.

Hệ số Beta được sử dụng để phân loại cổ phiếu theo mức độ rủi ro hệ thống.

### Bước 5: Xây dựng danh mục đầu tư

Xây dựng hai danh mục dựa trên hệ số Beta:

**Danh mục Low Beta:**
- DVM
- DHT
- CAP
- PVI
- VGP

**Danh mục High Beta:**
- L14
- MBS
- HUT
- SHS
- CEO

### Bước 6: Đánh giá hiệu quả danh mục

So sánh hai danh mục và chỉ số HNX-Index thông qua:

- Lợi suất trung bình.
- Độ biến động (Volatility).
- Sharpe Ratio.
- Tổng lợi nhuận tích lũy.
- Maximum Drawdown.

## 5. Kết quả phân tích

Kết quả thực nghiệm trong giai đoạn nghiên cứu:

| Chỉ tiêu | Low Beta | High Beta | HNX-Index |
|---|---:|---:|---:|
| Lợi suất trung bình | 2,64% | 4,63% | 1,80% |
| Độ biến động | 5,95% | 18,71% | 9,59% |
| Sharpe Ratio | 0,443 | 0,248 | 0,188 |
| Maximum Drawdown | -13,43% | -69,90% | -57,30% |

**Nhận xét:**

- Danh mục High Beta ghi nhận lợi suất trung bình cao hơn nhưng đồng thời có mức biến động và sụt giảm tối đa lớn.
- Danh mục Low Beta có mức biến động thấp hơn và Sharpe Ratio cao hơn trong giai đoạn nghiên cứu.
- Kết quả cho thấy tầm quan trọng của việc xem xét đồng thời lợi suất và rủi ro khi đánh giá danh mục đầu tư.

## 6. Kỹ năng thể hiện qua dự án

- Lập trình và phân tích dữ liệu bằng Python.
- Thu thập dữ liệu từ API.
- Làm sạch và chuẩn hóa dữ liệu.
- Phân tích dữ liệu khám phá (EDA).
- Phân tích thống kê và mô hình chuỗi thời gian.
- Xây dựng và đánh giá danh mục đầu tư.
- Trực quan hóa dữ liệu và trình bày kết quả.

## 7. Mã nguồn và dữ liệu

Mã nguồn được cung cấp dưới dạng Jupyter Notebook (`.ipynb`).

**Lưu ý:** Bộ dữ liệu gốc không được công khai trong repository. Người dùng cần chuẩn bị dữ liệu đầu vào tương ứng để chạy lại toàn bộ chương trình.

---

*Dự án được thực hiện phục vụ mục đích học tập và nghiên cứu. Các kết quả phân tích không phải khuyến nghị đầu tư.*
