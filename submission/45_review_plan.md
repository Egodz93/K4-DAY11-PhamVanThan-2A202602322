# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| `B2-dense / adasind_062370.jpg` | R7/R8 reference-only, LR_noM và M_only ở center | Cụm xe chồng lấn và vùng center có nhiều khác biệt nhất, cần phân biệt thiếu nhãn với lỗi reference/model | Ảnh gốc, `qa_overlay.html`, `local_quality_conflicts.csv`, rule R01/R03/R05 |
| `B2-dense / adasind_117120.jpg` | L1 L_only và L6+M8 LM_noR, cùng các ca M_only | Có Pedestrian/Car gần nhau và reference không khớp với L, cần xác nhận bằng mắt trước khi rework | Ảnh gốc, `model_compare.md`, `local_quality_conflicts.csv`, rule R01/R04 |

Giới hạn của kết luận từ ba frame ADASIND: đây là lát cắt một camera và ba thời điểm, không đại diện cho các cảnh, thời tiết, calibration hoặc camera khác.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: Kế hoạch lấy mẫu theo camera và cặp normal/hard, giãn các frame liền nhau trong cùng cảnh, rồi review trên ảnh gốc cùng calibration và vùng ignore. Kế hoạch chỉ tạo danh sách ca cần soi, không đo tỷ lệ lỗi vì không biết mẫu 200 frame đại diện thế nào cho 50.000 frame.
