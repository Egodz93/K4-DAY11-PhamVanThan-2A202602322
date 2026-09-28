# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 13 | 2 | 2 | 6 | 7 | MISSING (2) |
| mid | 5 | 0 | 0 | 2 | 3 | — |
| edge | 2 | 0 | 0 | 1 | 2 | — |

## Nhận xét

- Zone gãy nhiều nhất là `center` ở phía model, với 6 ca missing và 7 ca thừa. Phía người cũng có 2 missing và 2 spurious ở center, còn `mid` và `edge` không có lỗi L trong bảng này.
- Giả thuyết: vùng center có nhiều vật nhỏ và các cụm xe/người gần nhau, nên model dễ tách sai hoặc bỏ sót khi vật chồng lấn và ảnh fisheye bị méo. Bằng chứng là các dòng M_only và LR_noM tập trung ở `adasind_062370.jpg` và `adasind_117120.jpg`. Đây chỉ là giả thuyết từ 3 frame của một camera, không suy ra tỷ lệ lỗi cho toàn bộ ADASIND hay bốn camera SVM.
