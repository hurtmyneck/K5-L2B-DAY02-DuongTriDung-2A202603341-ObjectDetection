# Báo cáo cá nhân — Ngày 2 Object Detection

Đổi tên file theo `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md`. Điền kết quả thật, xóa dòng hướng dẫn khi nộp. Xem [quy định nộp](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên: Dương Trí Dũng
- MSSV: 2A202603341
- Email: duongdung04bg@gmail.com
- Lớp: L2B
- Link repo bài làm:https://github.com/hurtmyneck/K5-L2B-DAY02-DuongTriDung-2A202603341-ObjectDetection/tree/main
- Link Colab đã chạy:https://colab.research.google.com/drive/1CruaHU7ff_fj1VhghdT1lDMNFoLzaWRO#scrollTo=c368f24ecc8b859a

## 2. Schema và mini guideline

Dẫn tới [GUIDELINE_MINI.md](../../GUIDELINE_MINI.md). Tóm tắt ba ca mơ hồ đã quyết định, cách áp dụng schema và phần cần giảng viên làm rõ.

## 3. Annotation và self-QC

- Số file nhãn train: 50
- Kết quả checker và lỗi đã xử lý: 4
- Danh sách ít nhất 10 ảnh đã rà bằng mắt: drive_001.jpg, drive_002.jpg, drive_003.jpg, drive_004.jpg, drive_005.jpg, drive_006.jpg, drive_007.jpg, drive_008.jpg, drive_009.jpg, drive_010.jpg
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa:
- Commit khóa nhãn ban đầu:10/11/2026

## 4. Gold QC và rework

| Chỉ số              | Trước sửa | Sau sửa nếu có |
| ------------------- | --------: | -------------: |
| TP                  |       500 |                |
| FP                  |       335 |                |
| FN                  |       153 |                |
| Precision           |    0.5988 |                |
| Recall              |    0.7657 |                |
| F1                  |     0.672 |                |
| mean_iou_of_matches |    0.8559 |                |
| passed              |     false |                |

Dẫn tới `outputs/annotation_evaluation.json` trong repo. Nếu rework, ghi ảnh, lỗi đã kiểm, quyết định sửa/giữ và lý do. Không suy nguyên nhân chỉ từ FP/FN. Không có rework thì ghi rõ.

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch:
- Các tham số thay đổi so với notebook nếu có và lý do:
- Đường dẫn best checkpoint trong phiên chạy:

| Chỉ số trên 10 ảnh eval | Giá trị |
| ----------------------- | ------: |
| Precision               |   0.679 |
| Recall                  |   0.532 |
| mAP50                   |   0.436 |
| mAP50–95                |   0.288 |

Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa?
		Lớp truck có recall thấp nhất, bằng 0.000, tức là mô hình không phát hiện đúng được đối tượng truck nào trong tập eval theo tiêu chí đánh giá
2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box?
		Khi mAP50 cao nhưng mAP50-95 thấp, mô hình có thể đã xác định đúng vị trí tương đối của đối tượng nhưng bounding box chưa đủ chính xác
3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét?
		Kết quả đánh giá cho thấy mô hình có khả năng gặp khó khăn trong việc phân biệt các loại phương tiện, đặc biệt là truck và bus
4. Vì sao không dùng 10 ảnh eval để train? Vai trò validation của chúng trong notebook là gì?
		Không sử dụng 10 ảnh eval để train nhằm tránh data leakage và bảo đảm tính khách quan của quá trình đánh giá

## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
| | | | |

## 7. Tự đánh giá theo rubric

Đối chiếu [RUBRIC.md](../../RUBRIC.md): phần nào đã có kết quả, phần nào còn thiếu hoặc chưa kiểm được. Không tự nhận hoàn thành bước chưa chạy.

## 8. Công cụ AI và tài liệu tham khảo

Ghi công cụ đã dùng, dùng ở bước nào và phần đã tự kiểm tra; không dùng thì ghi rõ. Liệt kê nguồn ngoài repo được sử dụng. Không ghi mật khẩu/token hoặc đính kèm gold train.

Công cụ sử dụng: CVAT tại bước gán nhãn
