# Báo cáo cá nhân — Ngày 11
Họ tên: Lê Duy Bảo               Mã học viên:  2A202603257
Phiên bản CVAT (Help → About):  2.81.0
Guideline: Road v1.0    Lần nộp (`revision` trong manifest): 1  
Thời điểm export (ngày giờ trên CVAT): 22/11/2026 10:59:20 UTC (thời điểm tạo manifest)    Số lần nộp lại sau Rework: 0  

## 1. Kiểm project
| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Có | lane polyline; road_curb polyline; crosswalk polygon; drivable polygon; traffic_light và traffic_sign rectangle. |
| Thuộc tính và giá trị | Có | Thuộc tính và giá trị lấy theo cấu hình Road v1.0 trong `configs/road_v1_labels.json`. |
| 4 tag ảnh | Có | camera, timeofday, weather và source; mỗi ảnh có đủ 4 tag. |
Cách kết thúc polyline trên bản CVAT này: Dừng ở điểm xa nhất còn thấy vạch; không kéo polyline tới chân trời.
Cách đặt tag ảnh trên bản CVAT này: Gắn từng label camera, timeofday, weather và source trực tiếp cho cả ảnh bằng một tag, không vẽ hình.

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 30 | 5 | 4 | 25 | 28 | 24 |
| front-extra (đã làm 4 / 4) | 4 | 13 | 0 | 4 | 10 | 11 | 14 |
| fisheye | 8 | 7 | 4 | 10 | 10 | 5 | 6 |
| fisheye-extra (đã làm 4 / 4) | 4 | 0 | 3 | 4 | 3 | 0 | 0 |

## 3. Bảng ca khó
| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| Không ghi nhận ca mơ hồ trong manifest hoặc file export. |  |  |  |  |

## 4. Phiếu QC 1 nhận được
Bạn kiểm lô của tôi:  Quyết định nhận được:  
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| Bao-front.zip | Có | 9 / 9 | 5 / 5 | Có |
| Bao-fisheye.zip | Có | 4 / 4 | 5 / 5 | Có |

## 6. Ảnh chụp màn hình
1. Tab Labels của project.
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển).
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong.
4. Một đoạn XML có <polyline label="lane">.

(Chưa có ảnh chụp màn hình trong workspace; mục này cần chèn khi hoàn tất biên tập.)

## 7. Tự đánh giá
Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20:  
Nhãn của bạn đi vào model ở đâu? Chọn một lỗi đã sửa và nói nó làm model học sai thế nào:  

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor
| y | 720 | 680 | 640 | 600 | 560 |
| --- | ---: | ---: | ---: | ---: | ---: |
| x của chúng tôi |  |  |  |  |  |
| x của bạn kia |  |  |  |  |  |

Trả lời 3 câu:

1. Năm số x đó chính là đích mà một model row-anchor học cho vạch này. Nếu bạn dừng polyline sớm 40 px, hàng nào đổi thành "không có làn"?
2. So với bạn được kiểm (cùng ảnh): ở hàng 720 và hàng 560, hai bạn lệch nhau bao nhiêu pixel? Lệch ở hàng nào ảnh hưởng LKA nhiều hơn (slide 25)?
3. Nếu polyline vẽ từ xa về gần (ngược quy tắc 2), cách tính trên có đổi không? Script nào sẽ gặp khó?
