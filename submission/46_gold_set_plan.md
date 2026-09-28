# Đề xuất gold set theo camera — tình huống giả lập

**Đầu bài:** 50.000 frame từ bốn camera SVM, ngân sách chọn 200 frame để review/gold. Đây là tình huống trên slide,
**không phải** 50.000 frame có trong repo. Phân bổ đúng 200 ở `45_sampling_plan.csv` cho bốn camera, mỗi camera có
normal và hard slice. “Gold set” ở đây là **kế hoạch tạo** reference sau kiểm chứng, không phải teaching reference
ADASIND hoặc nhãn bạn vừa vẽ. Nếu cần, dùng `notebooks/day11-svm360-colab.ipynb` để thử tổng phân bổ; notebook
không làm thay phần lý do.

| camera_id | Hard case cần chọn | Vì sao dễ sai | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|
| front | Vật cắt ở vòng kính, xe máy gần xe camera và seam góc trước | Méo rìa làm sai geometry, rider dễ bị tách sai | Calibration vòng kính, `ego_body`, `lens_border`, H=40 và timestamp | Hai annotator độc lập, sau đó adjudicator kiểm ảnh gốc và overlay BEV nếu có |
| rear | Xe lùi, đèn chói, vật ra khỏi FOV | Occlusion và Outside dễ bị nhầm với missing | Calibration rear, trạng thái Outside, `truncated`, `occluded` | Review mù theo frame rồi kiểm chuỗi thời gian trước khi gọi là gold |
| left | Cụm xe đỗ sát curb và người đi bộ cạnh xe | Cụm gần nhau dễ tạo box trùng hoặc sai class | Curb/ignore policy, H=40, `crowd_or_group` và boundary camera | QA thứ hai kiểm từng object, adjudicator ký quyết định khó |
| right | Bike/ThreeWheeler sát mép và vùng seam | Vật nhỏ bị cắt, Rider/Bike và class ba bánh dễ nhầm | Calibration right, vòng kính, `ego_body`, `lens_border` và seam policy | Soát ảnh gốc, đối chiếu calibration, chỉ hợp nhất sau khi có policy |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): refresh khi đổi vị trí camera, calibration, lens mask, taxonomy, ngưỡng H hoặc policy seam, và khi drift làm xuất hiện hard case mới.
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: cùng vật xuất hiện ở góc front-left và left-front với timestamp đồng bộ, calibration đã kiểm, ảnh overlap đủ rõ và policy output quy định giữ hai box hay hợp nhất.
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: peer agreement chỉ cho biết hai người đồng ý trên mẫu đã xem, còn quality report phụ thuộc camera, zone, calibration và mẫu. Nó không kiểm chứng coverage, seam hoặc distortion của ba camera còn lại.
