# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B2 | DUPLICATE | 1 |
| center | B2 | MISSING | 8 |
| center | B2 | SPURIOUS | 9 |
| center | B2 | STRUCTURE | 2 |
| center | C0 | SPURIOUS | 2 |
| edge | B2 | ATTRIBUTE | 1 |
| edge | B2 | BOX_GEOMETRY | 1 |
| edge | B2 | MISSING | 1 |
| edge | B2 | SPURIOUS | 2 |
| edge | C0 | SPURIOUS | 1 |
| edge | C0 | WRONG_CLASS | 1 |
| mid | B2 | MISSING | 2 |
| mid | B2 | SPURIOUS | 3 |
| mid | C0 | SPURIOUS | 1 |
| unknown | B2 | IGNORE_SCOPE | 1 |

## Top defects
- SPURIOUS: 18 (ví dụ frame adasind_019560.jpg)
- MISSING: 11 (ví dụ frame adasind_062370.jpg)
- STRUCTURE: 2 (ví dụ frame adasind_117120.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: lỗi nổi bật nhất là SPURIOUS và MISSING ở center. Các dòng M_only và LR_noM tập trung trong model_compare của B2-dense, nên nguyên nhân phù hợp nhất là E4_model_domain khi model tách hoặc bỏ sót vật nhỏ trong cụm fisheye. Các dòng R_only và L_only không đủ bằng chứng để quy nguyên nhân, nên giữ E5_unresolved hoặc escalation.
- Cách sửa và ai nhận việc (`owner`): giữ nhãn người khi L và R cùng khớp, giao ai_team kiểm tra model ở center và các vật chồng lấn. QA cần phân xử R7/R8 ở adasind_062370.jpg cùng L1 và L6+M8 ở adasind_117120.jpg. Không rework bản khóa vì không có ca annotator P0/P1 đủ chắc, delta trước/sau giữ nguyên.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): `submission/screenshots/B2-dense-062370.jpg`, `submission/screenshots/B2-dense-117120.jpg`, `submission/r3_diag/model_compare.md`, `submission/r3_diag/local_quality_conflicts.csv`, các dòng r3_diag tương ứng trong `submission/findings.csv`, cùng R01, R03, R04 và R05.
