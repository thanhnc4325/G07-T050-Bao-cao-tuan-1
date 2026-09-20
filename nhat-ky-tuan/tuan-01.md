# Nhật ký tuần 01 · 15/09 – 21/09/2026

> **File ví dụ** — tên, số liệu và link đều là giả. Tuần mới thì copy
> [`_mau-tuan.md`](_mau-tuan.md) thành `tuan-02.md`.

**Lead tuần này:** Nguyễn Công Thành
**Dữ liệu / task CVAT:** Ảnh giao thông đô thị — [task 12](https://cvat.example.com/tasks/12)

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
| @T050-NGUYỄN CÔNG THÀNH-02219 (Nguyễn Công Thành) | Lead | Chia job, chốt edge case, review job 1522, 1524, 1525, 1527, 1742, 1744, 1745, 1742; gán job 1742 |
| @T050-LƯU QUANG HÙNG-02142 (Lưu Quang Hùng) | Annotator | Job 1525, 1744 |
| @T050-NGUYỄN VĂN TRỌNG-02276 (Nguyễn Văn Trọng) | Annotator | Job 1527, 1745 |
| @T050-NGUYỄN PHƯƠNG THẢO-02047 (Nguyễn Phương Thảo) | Annotator | Job 1524, 1742 |
| @T050-KIM NGUYÊN KHÔI-02116 (Kim Nguyên Khôi) | Reviewer · Annotator | Review job 1742, 1744, 1745, 1742; gán job 1522|

Kim Nguyên Khôi không kịp hoàn thành báo cáo và review nên Nguyễn Công Thành hỗ trợ

## Công việc

| # | Nội dung công việc | Annotator | Reviewer | Hoàn thành | Ghi chú |
|---|---|---|---|---|---|
| 1 | Job 1525 — 25 ảnh, Bbox, polygon, polyline | Lưu Quang Hùng | Nguyễn Công Thành | ✅ 100% | Đã hoàn thành |
| 2 | Job 1527 — 25 ảnh, Bbox, polygon, polyline | Nguyễn Văn Trọng | Nguyễn Công Thành | ✅ 100% | Đã hoàn thành  |
| 3 | Job 1524 — 25 ảnh, Bbox, polygon, polyline | Nguyễn Phương Thảo | Nguyễn Công Thành | 🟡 50% | Chưa hoàn thành polygon, polyline từ 16/09/2026 |
| 4 | Job 1522 — 25 ảnh, Bbox, polygon, polyline | Kim Nguyên Khôi | Nguyễn Công Thành | ✅ 100% | Mới làm dở 1 ảnh, 24 ảnh chưa làm |
| 5 | Đọc lại guideline Bounding Box, Polygon & Polyline, gom các ca chưa rõ | Nguyễn Công Thành | — | ✅ 100% | |
| 8 | Job 1742 - 25 ảnh, Segmentation | Nguyễn Công Thành | Nguyễn Công Thành, Kim Nguyên Khôi | ✅ 100% | Đã hoàn thành |
| 7 | Job 1744 - 25 ảnh, Segmentation | Lưu Quang Hùng | Nguyễn Công Thành, Kim Nguyên Khôi | ✅ 100% | Đã hoàn thành |
| 8 | Job 1745 - 25 ảnh, Segmentation | Nguyễn Văn Trọng | Nguyễn Công Thành, Kim Nguyên Khôi | ✅ 100%  Đã hoàn thành| |
| 9 | Job 17xx - 25 ảnh, Segmentation | Nguyễn Phương Thảo | Nguyễn Công Thành, Kim Nguyên Khôi | ⬜ 0% | Không hợp tác với nhóm, đến ngày cuối mới báo ốm để trốn tránh công việc và nhóm cũng không thể hỗ trợ kịp thời vì đã cận hạn nộp báo cáo |
| 10 | Đọc lại guideline Semantic Segmantation | Nguyễn Công Thành, Kim Nguyên Khôi | — | ✅ 100% | Đã hoàn thành |

## Tổng kết

- Đã gán: 154 / 200 ảnh (77%)
- Qua review lần đầu: 49,4% (trả lại 39 ảnh)
- Edge case mới: P-001, P-002, P-003, P-004, P-005, P-006 — đã chốt P-001 thành [QĐ-001](../so-quyet-dinh.md#qđ-001)

## Vướng mắc

- P-002 (xe bị che khuất) chưa chốt, đang đợi Lead đã gửi câu hỏi lên BTC.
- P-003: vẽ lại box y hệt qua các frame liên tiếp mất ~40% thời gian job 105.
  Đang cân nhắc làm tool trong [`source-tool/`](../source-tool/).
- P-004 (biển không xác định) chưa chốt, đang đợi Lead đã gửi câu hỏi lên BTC.
- P-005 (đèn giao thông không tín hiệu) chưa chốt, đang đợi Lead đã gửi câu hỏi lên BTC.
- P-006 (dải phân cách thấp) chưa chốt, đang đợi Lead đã gửi câu hỏi lên BTC.
- P-007 

## Kế hoạch phần còn tuần 1

- Chốt P-002, P-003, P-004, P-005, P-006.
- Xong các job còn lại.
- Quyết định có làm tool cho P-003 hay dùng chế độ Track sẵn có của CVAT.
