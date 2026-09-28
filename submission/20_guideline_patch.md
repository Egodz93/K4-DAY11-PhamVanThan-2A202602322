# Guideline patch

- **Rule mới đề xuất:** Khi hai box cùng class chồng lấn mạnh, chỉ giữ hai vật nếu ảnh gốc cho thấy hai đường viền hoặc hai bộ phận riêng biệt. Nếu không thể tách vật, dùng một box cho cụm và ghi `occluded` hoặc `ignore_region` theo bằng chứng nhìn thấy.
- **Áp dụng cho:** `ThreeWheeler`, `Pedestrian`, `Car`, vùng `center` và các ca box lồng nhau hoặc bị che.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** R01, R04 và R05 nói về ngưỡng, class và che khuất nhưng chưa có tiêu chí quyết định khi một box reference nằm trong box khác hoặc khi hai người rất gần nhau.
- **`rules_version` mới:** v1.1.0
- **Hiệu lực từ:** P4 review trở đi, sau khi QA xác nhận ví dụ trên ảnh gốc.
