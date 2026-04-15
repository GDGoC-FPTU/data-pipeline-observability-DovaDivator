[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574094&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** dvttvdthanhan@gmail.con
**Name:** Đồng Văn Thịnh

---

## Mo ta

(Mo ta ngan gon bai lab va nhung gi ban da lam)
Bài lab thực hiện xây dựng một quy trình ETL (Extract - Transform - Load) cơ bản bằng Python. Trong đó: `Extract` dữ liệu từ file JSON (có xử lý lỗi thiếu file); `Validate` để lọc bỏ các bản ghi có giá âm hoặc thiếu danh mục; `Transform` dữ liệu bằng Pandas để tính giá chiết khấu, chuẩn hóa văn bản và thêm timestamp; cuối cùng là `Load` dữ liệu sạch ra file CSV. Hệ thống đảm bảo tính ổn định thông qua việc thông báo chi tiết số lượng bản ghi hợp lệ và bị loại bỏ.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)

> Chủ yếu test trên `raw_data.json`
```bash
python solution.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Có 3 dữ liệu pass, 2 dữ liệu fail
```
Extracting data from raw_data.json...
Validation complete. Valid: 3, Errors: 2
Data saved to processed_data.csv
```
- Test lệnh: ```pytest tests```

```
============= test session starts ==============
platform win32 -- Python 3.10.0, pytest-9.0.3, pluggy-1.6.0
rootdir: D:\Work files\ai-vin\data-pipeline-observability-DovaDivator
collected 9 items                               

tests\test_autograder.py .........        [100%]

============== 9 passed in 2.08s ===============
```


