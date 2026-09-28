# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật không tự động là `DUPLICATE`. Cần rule cross-camera riêng để quyết định giữ hai box theo từng camera hay hợp nhất ở tầng output. Quyết định phải dựa trên timestamp, calibration, vùng overlap và policy sản phẩm.
2. Trên cùng camera, giữ cùng track ID khi identity và chuyển động liên tục, hình học thay đổi phù hợp và vật vẫn quan sát được. Thêm keyframe khi hình dạng hoặc vị trí thay đổi đáng kể, dùng Outside khi vật rời FOV. Trước khi nối qua hai camera cần timestamp đồng bộ, calibration, bằng chứng vùng seam và policy output đã được duyệt.
3. Ở `adasind_117120.jpg` `L1`, ảnh cho thấy một Pedestrian có thể là người riêng nhưng reference không có box tương ứng. Mình không tự sửa bản khóa, ghi `E5_unresolved` và escalate để QA phân xử. Nếu làm lại, mình sẽ kiểm các vật nhỏ và box chồng lấn trên ảnh gốc trước khi khóa, đồng thời ghi rõ bằng chứng cho từng quyết định.
