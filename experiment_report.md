# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600365
**Name:** Đồng Văn Thịnh
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Dữ liệu chuẩn, Agent đưa ra quyết định chính xác. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999 | 1 | Agent bị đánh lừa bởi dữ liệu bị thổi phồng |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trả lời sai vì nó hoạt động dựa trên nguyên tắc tin tưởng hoàn toàn vào dữ liệu đầu vào mà không có khả năng tự kiểm chứng thực tế. Các vấn đề cụ thể bao gồm:

- **Outliers (Giá trị ngoại lai):** Bản ghi "Nuclear Reactor" có giá trị quá lớn, làm lệch hoàn toàn logic lựa chọn "best choice" của Agent.

- **Wrong Data Types & Null values:** Dữ liệu rác thường chứa các trường bị thiếu hoặc sai định dạng, khiến Agent bỏ qua các bản ghi hợp lệ và tập trung vào những dữ liệu gây nhiễu.

- **Duplicate IDs:** Việc trùng lặp ID khiến hệ thống tính toán sai số lượng và trọng số của sản phẩm.

Tóm lại, khi dữ liệu đầu vào bị "nhiễu", mọi logic suy luận của Agent dù thông minh đến đâu cũng sẽ dẫn đến kết quả sai lệch (Garbage In, Garbage Out).

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý

>Dù có viết Prompt hay đến đâu (Quality Prompt) để hướng dẫn Agent tư duy, nhưng nếu dữ liệu cung cấp bị sai sự thật hoặc chứa đầy lỗi (Bad Data), Agent vẫn sẽ đưa ra những quyết định rủi ro và không chính xác. Dữ liệu chất lượng là nền tảng cốt lõi; Prompt chỉ là công cụ để khai thác nền tảng đó.
