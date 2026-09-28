# Sensor context

- Rig: ảnh ADASIND là camera fisheye gắn trên phương tiện hai bánh hoặc cụm tay lái phía trước, nhìn theo hướng di chuyển. Đây là mô tả từ ảnh, không phải thông số rig được xác nhận.
- `ego_body` nhìn thấy ở mép dưới và góc trái, gồm tay lái, tay/người lái và phần thân phương tiện. Vùng thấy rõ thay đổi theo frame nên phải vẽ theo phần thực sự xuất hiện.
- Vòng kính là một vòng tròn lớn gần giữa ảnh, viền đen ở các góc. Theo `frames.csv`, tâm và bán kính xấp xỉ 441,911,823 ở `adasind_062370.jpg`, 578,975,801 ở `adasind_069450.jpg`, và 595,991,831 ở `adasind_117120.jpg`, chiếm gần toàn bộ khung hình.
