# Escalation ticket

## Ticket 1

- **Frame:** `adasind_062370.jpg`, các box reference `R7` và `R8`
- **Ảnh chụp:** `submission/screenshots/B2-dense-062370.jpg`
- **Expected impact:** Nếu không phân xử, hai ca reference-only có thể làm sai số missing/spurious ở vùng center và làm lẫn lỗi reference với lỗi annotator.
- **Owner:** `qa`
- **Recommendation:** Soát ảnh gốc cùng `qa_overlay.html`, quyết định R7 có phải vật riêng hay box lồng của R5, đồng thời xác nhận R8 có đủ bằng chứng cho Truck bị che. Cập nhật reference hoặc guideline, không sửa âm thầm bản khóa.

## Ticket 2

- **Frame:** `adasind_117120.jpg`, `L1` và `L6+M8`
- **Ảnh chụp:** `submission/screenshots/B2-dense-117120.jpg`
- **Expected impact:** Một người đi bộ và một Car nhìn thấy ở L nhưng không có box tương ứng ở R, có thể làm sai kết luận về recall của reference.
- **Owner:** `qa`
- **Recommendation:** Đối chiếu trực tiếp ảnh gốc với reference, xác nhận L1 là người riêng và L6 là Car riêng. Nếu đúng, sửa reference sau quy trình phê duyệt.
