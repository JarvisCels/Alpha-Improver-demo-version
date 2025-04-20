# Alpha-Improver-demo-version

Alpha‑Improver (Demo Version)
Một framework minh họa quy trình áp dụng Machine Learning và ONNX để nâng cao hiệu suất giao dịch của Expert Advisor (EA) trên MetaTrader 5.

---

## 🚀 Tổng quan

Alpha‑Improver gồm các bước chính:
1. **Trích xuất dữ liệu**  
   - Lịch sử giao dịch (entry/exit, profit/loss) của EA.  
   - Context thị trường tại thời điểm mở/đóng lệnh (các indicator, biến động giá,…).
2. **Xây dựng features**  
   - Chuyển context thành tập feature đầu vào cho model ML.
3. **Huấn luyện classification model**  
   - Phân loại lệnh thắng/thua bằng CatBoost (có thể thay bằng bất kỳ classifier nào).  
   - Tối ưu hyperparameters với Optuna.
4. **Đóng gói và tích hợp**  
   - Chuyển model sang định dạng ONNX.  
   - Nạp ONNX vào EA trên MetaTrader 5 để chạy real‑time.

---


## Lưu ý:
- _Đây là phiên bản chưa được Features Engineer phù hợp với logic của EA. Các features được sử dụng đang là mặc định của Template._

**Perform của EA ban đầu:**
![image](https://github.com/user-attachments/assets/0d3b3f43-5baf-416a-bc2e-2d0ff8ec4f16)


**Sau khi tích hợp ONNX vào EA:**
![image](https://github.com/user-attachments/assets/9312d7c8-f486-4f93-bbe0-c816fa25fae7)


- Việc tích hợp ONNX vào giúp cải thiện các chỉ số như Profit Ratio và Sharpe Ratio, đánh đổi là số lượng giao dịch, Net Profit và Ret/DD giảm đáng kể.

- Tuy nhiên, cho dù các Features chưa được tối ưu cho Logic của EA, nhưng với các Features cơ bản Model cũng đã có thể cho ra một kết quả tiềm năng.

**Kết quả Model CatBoost sau khi dùng Optuna tối ưu:**

![image](https://github.com/user-attachments/assets/2d0b370c-2336-4165-9a93-8be89161362e)
