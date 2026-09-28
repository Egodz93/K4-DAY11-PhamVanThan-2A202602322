# QA review · B2-dense

Mã khóa: 7671-7AF3

| frame | object_ref | rule_id | nhận xét |
|---|---|---|---|
| adasind_062370.jpg | L2 | R05 | Bike ở mép phải bị cắt bởi biên ảnh/vòng kính, `truncated=true` và `occluded=false` phù hợp với phần nhìn thấy trên ảnh. Giữ nhãn và thuộc tính. |
| adasind_069450.jpg | L1 | R02 | ThreeWheeler ở mép trái được khoanh theo phần nhìn thấy trên ảnh fisheye gốc, không nối sang phần ngoài khung. Hình học phù hợp. Giữ nhãn. |
| adasind_117120.jpg | L1 | R04 | Người ở phía phải là một Pedestrian riêng, không thấy xe hai bánh gắn với người này nên không gộp thành Bike. Giữ class Pedestrian. |
| adasind_117120.jpg | L8 | R03 | Vật ở phía phải là ThreeWheeler. Box bám phương tiện nhìn thấy và không cần đổi sang Car. Giữ class hiện tại. |
| adasind_062370.jpg | ego_body | R07 | Polygon `ego_body` chỉ bao phần thân/người của xe camera ở mép dưới, tách khỏi các box giao thông. Phạm vi ignore phù hợp. Giữ. |

Ghi finding r2_qa: cell=L_only, rule_id có giá trị, why để trống.
