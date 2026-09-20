# Problem backlog

Những chỗ gặp trong lúc gán nhãn mà **guideline chưa trả lời được**, cộng các pain point về công cụ.

Ghi ngay khi gặp, kể cả lúc chưa biết xử lý thế nào. Một edge case không được ghi lại thì
mỗi người sẽ tự xử lý theo một kiểu — và đó là nguồn lớn nhất của nhãn không nhất quán.

> Các mục bên dưới là **ví dụ**, tên và link CVAT đều giả. Mẫu trống để copy nằm cuối file.

## Danh sách

| Mã | Tóm tắt | Loại | Mục guideline | Trạng thái | Kết quả |
|---|---|---|---|---|---|
| [P-001](#p-001) | Xe lạ: xe có 3 đèn đỏ ở phía sau và thân dài bất thường , thành viên không biết đó là xe như thế nào và vẽ box sai | Guideline chưa nói tới | Tình huống không có trong guideline | ✅ Đã chốt | [QĐ-001](so-quyet-dinh.md#qđ-001) |
| [P-002](#p-002) | Xe bị che khuất hơn một nửa xe, nhưng nửa bị che cắt thấy được 45% | Guideline chưa nói tới | §3 | ↗️ Hỏi BTC | — |
| [P-003](#p-003) | Phải vẽ lại box y hệt qua nhiều frame liên tiếp | Pain point công cụ | — | 🗣️ Đang bàn | — |
| [P-004](#p-004) | Một số biển chưa thể xác định là biển báo hay biển quảng cáo do quá mờ | Guideline chưa nói tới | §3 | ↗️ Hỏi BTC | — |
| [P-005](#p-005) | Đèn giao thông ở ngã tư, có những đèn mình không thấy được tín hiệu do đèn đó dành cho xe đi đường khác: liệu vẽ hay bỏ qua | Guideline chưa nói tới | §3 | ↗️ Hỏi BTC | — |
| [P-006](#p-006) | Dải phân cách: Giải phân cách rất thấp, đủ để ô tô có thể đi lên thì có tính là đường phụ không | Guideline mơ hồ | §4.1 | ↗️ Hỏi BTC | — |

---

## P-001

**Xe lạ: xe có 3 đèn đỏ ở phía sau và thân dài bất thường**

- **Loại:** Guideline chưa nói tới
- **Mục guideline:** Tình huống không có trong guideline 
- **Người phát hiện:** Nguyễn Công Thành · 16/09/2026
- **Link CVAT:**
  - https://cvat.note.transformerlabs.ai/tasks/169/jobs/1524?frame=37
- **Mô tả:** xe có 3 đèn và thân dài bất thường.
- **Các cách hiểu:**
  1. Theo câu chữ: xa lạ đối với một số người.
  2. Theo hình minh hoạ: box không vẽ được toàn bộ xe vì không xác định được.
- **Xử lý tạm trong lúc chờ:** vẽ box riêng và gắn tag `can_xem_lai` để dễ lọc ra sửa.
- **Kết quả:** ✅ [QĐ-001](so-quyet-dinh.md#qđ-001)

## P-002

**Xe bị che khuất hơn một nửa xe, nhưng nửa bị che cắt thấy được 45%**

- **Loại:** Guideline chưa nói tới
- **Mục guideline:** §3
- **Người phát hiện:** Nguyễn Công Thành · 16/09/2026
- **Link CVAT:**
  - 
- **Mô tả:** Xe bị vật thể khác che khuất phần lớn, phần còn lại lộ ra khoảng 45%. Guideline chưa quy định rõ ngưỡng % bị che khuất tối đa để bỏ qua, và nếu vẽ thì box nên ôm sát phần nhìn thấy hay ước lượng toàn bộ xe.
- **Các cách hiểu:**
  1. Bỏ qua không gán nhãn nếu phần lộ ra dưới 50%.
  2. Luôn gán nhãn, box chỉ ôm sát phần xe nhìn thấy được.
  3. Gắn nhãn phần nhìn thấy, thêm tag che_khuat_nhieu để dễ đối chiếu sau.
- **Xử lý tạm trong lúc chờ:** đợi lead hỏi BTC.
- **Kết quả:** ↗️ Đã hỏi BTC ngày 17/09/2026, chờ trả lời.

## P-003

**Phải vẽ lại box y hệt qua nhiều frame liên tiếp**

- **Loại:** Pain point công cụ
- **Mục guideline:** —
- **Người phát hiện:** Nguyễn Công Thành · 16/09/2026
- **Link CVAT:** 
- **Mô tả:** Ảnh chụp liên tiếp từ camera cố định. Xe đỗ bên đường xuất hiện y nguyên ở hàng chục
  frame, annotator phải vẽ lại ở từng frame. Ước tính chiếm ~40% thời gian job 105.
- **Hướng đang cân nhắc:**
  1. Dùng chế độ *Track* sẵn có của CVAT — cần thử xem có hợp với dữ liệu dạng ảnh rời không.
  2. Viết script đọc file export của CVAT, nhân box sang các frame kế tiếp, rồi import lại.
- **Kết quả:** 🗣️ Đang bàn. Nếu chọn hướng 2 thì đổi trạng thái sang 🛠️ và làm trong
  [`source-tool/`](source-tool/).

## P-004

**Biển báo và biển quảng cáo bị mờ**

- **Loại:** Guideline chưa nói tới
- **Mục guideline:** §3
- **Người phát hiện:** Nguyễn Công Thành · 16/09/2026
- **Link CVAT:** 
- **Mô tả:** Một số biển báo ở khoảng cách xa hoặc chất lượng ảnh kém dẫn đến quá mờ, không thể phân biệt chắc chắn đó là biển báo giao thông hay biển quảng cáo thông thường.
- **Hướng đang cân nhắc:**
  1. Gán nhãn toàn bộ các biển có hình dáng (shape) giống biển báo giao thông.
  2. Chỉ gán nhãn những biển có thể nhìn rõ và chắc chắn là biển báo.
- **Xử lý tạm trong lúc chờ:** đợi lead hỏi BTC.
- **Kết quả:** ↗️ Đã hỏi BTC ngày 17/09/2026, chờ trả lời.

## P-005

**Đèn giao thông dành cho hướng khác ở ngã tư**

- **Loại:** Guideline chưa nói tới
- **Mục guideline:** —
- **Người phát hiện:** Nguyễn Công Thành · 16/09/2026
- **Link CVAT:** 
- **Mô tả:** Tại các ngã tư, xuất hiện những cụm đèn giao thông điều hướng cho luồng xe khác. Camera không nhìn thấy màu đèn/tín hiệu của các cụm đèn này.
- **Hướng đang cân nhắc:**
  1. Gán nhãn tất cả các cụm đèn giao thông xuất hiện trong ảnh, bất kể hướng.
  2. Chỉ gán nhãn cụm đèn giao thông đang điều hướng trực tiếp cho luồng xe của camera.
- **Xử lý tạm trong lúc chờ:** Tạm thời vẽ box cho tất cả đèn thấy được và gắn tag den_khac_huong.
- **Kết quả:** ↗️ Đã hỏi BTC ngày 17/09/2026, chờ trả lời.

## P-006

**Dải phân cách thấp có tính là đường phụ không**

- **Loại:** Guideline mơ hồ
- **Mục guideline:** —
- **Người phát hiện:** Nguyễn Công Thành · 16/09/2026
- **Link CVAT:** 
- **Mô tả:** Xuất hiện các dải phân cách được xây rất thấp, các phương tiện (ô tô) hoàn toàn có thể di chuyển đè lên được. Guideline chưa làm rõ khu vực này tính là dải phân cách cứng hay đường phụ.
- **Hướng đang cân nhắc:**
  1. Tính là đường phụ vì phương tiện có thể đi lên được.
  2. Không gán nhãn vì bản chất thiết kế vẫn là dải phân cách.
- **Xử lý tạm trong lúc chờ:** đợi lead hỏi BTC.
- **Kết quả:** ↗️ Đã hỏi BTC ngày 17/09/2026, chờ trả lời.

---