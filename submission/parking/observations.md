# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ (mô tả vị trí trong ảnh): chọn hai vạch trắng chia ô rõ nhất ở tiền cảnh: một vạch chéo từ khoảng (407,652) xuống mép dưới tại (528,720), và một vạch ở bên phải từ khoảng (698,623) tới mép phải tại (960,684). Cả hai là mép ngăn giữa các ô đỗ, không phải vạch dẫn lối.
- Một vạch/dấu sơn hoặc biên **không** vẽ, và vì sao: không gán nhãn dải sáng mảnh chạy ngang ở khu vực xa phía trên lối xe (xấp xỉ y=480–500), nó giống mép/dải dẫn lối hơn là đoạn sơn tạo ranh giới một ô riêng, nên không đủ chắc để gọi là `parking_line`.
- Polygon `free_space` dừng ở đâu, có phần bị che nào không: polygon bao dải mặt đường trống ở giữa ảnh, nằm giữa hàng vạch phía xa và các vạch ô đỗ tiền cảnh, dừng ở ranh hàng vạch gần, ranh phía xa và hai mép ảnh, không đi qua xe đỏ hoặc vật cản. Không có phần bị che được nối đoán qua.
- Ca chưa chắc cần hỏi người soát (nếu không có, ghi “không có”): Không có.
