# CLAUDE.md – Sổ nợ và Done Nha

Chủ dự án: Nguyên Khang (UI/UX designer). Giao tiếp bằng tiếng Việt, ngắn gọn, hành động trước; việc nhiều lựa chọn thì dùng bảng so sánh có đánh đổi. Việc nặng cỡ Opus thì báo cho anh biết.

## Dự án trong repo này: Sổ nợ
- PWA ghi nợ cá nhân, chạy trên GitHub Pages (`khang14052004-dev/so-no`). Repo chỉ có giao diện.
- Backend là Apps Script + Google Sheet. `Code.gs` KHÔNG được đưa lên repo công khai này.
- Tính năng: ghi nợ nhanh, nợ mình nợ người và người nợ mình, trả từng phần, báo cáo Zalo kèm VietQR, chia bill, nhập từ ảnh (OCR), thống kê, quét chi tiêu thẻ.

## Quy tắc làm việc (bắt buộc)
- KHÔNG ghi vào repo, tài liệu hay trí nhớ: token, link cài đặt riêng, mật khẩu, số tài khoản, số thẻ. Anh đã dặn "đừng chia sẻ".
- Nhánh làm việc: `claude/v3-ghi-no-nhieu-nguoi`. PR đã merge thì phải tạo PR mới cho phần việc tiếp theo.
- Mỗi lần sửa file giao diện phải tăng `CACHE` trong `sw.js` (hiện `so-no-v23`), nếu không điện thoại giữ bản cũ.
- Chỉ sửa đúng phần được yêu cầu; không viết lại cả file.
- Số tiền là số nguyên đồng. Không dùng số thực cho tiền.

## Dự án mới: Done Nha (app quỹ nhóm và chia tiền chuyến đi)
Tài liệu gốc (đọc trước khi làm):
- Định hướng sản phẩm: https://claude.ai/code/artifact/be6b0138-86ef-4cd1-bbf6-4a8a10dca24a
- Kế hoạch chuyến đi: https://claude.ai/code/artifact/1b8c88d0-e732-4508-a9e9-9040b27314f2

Đã chốt (13/10/2026):
- Tên app: **Done Nha**. Nhà phát triển: **Nguyên Khang**. Slogan: "Hùn chung đi chơi, tính tiền khỏi cãi."
- Giọng văn Nam bộ, Sài Gòn: nha, nè, lẹ, khỏi. "Tui, hông, dzô" chỉ ở chỗ vui. Nút chính "Done nha ✓". Tránh chữ "kèo" và "hụi".
- Chuyến đầu tiên: Đà Lạt, tối 2/1 đến chiều 5/1/2027, 7–9 người, chỉ anh dùng Android, còn lại iPhone. Thủ quỹ: Kiệt (đổi được). Góp quỹ bằng chuyển khoản và tiền mặt, dự kiến 2 triệu/người (chưa chốt). App phải xong trước 28/12/2026.
- Lõi là sổ cái (ledger); quỹ chung là "thành viên ảo". Số dư luôn tính từ sổ, không lưu riêng. Cân đối tối thiểu số lần chuyển, VietQR điền sẵn cho từng người.
- Chỉ thủ quỹ (hoặc người thủ quỹ ủy quyền) được ghi khoản chi từ quỹ; thành viên vẫn tự ghi khoản mình trả.
- App KHÔNG bao giờ giữ tiền (tránh bị coi là trung gian thanh toán, Nghị định 52/2024). Quỹ chỉ là con số; tiền thật nằm ở thủ quỹ.
- Kiến trúc: ghi trên điện thoại trước, đồng bộ sau; Supabase (đăng nhập khách/Google/Apple, Postgres có Row Level Security, kho ảnh hóa đơn nén, realtime). Sổ cái chỉ ghi thêm, ID dòng do máy khách sinh để gửi lại không bị trùng, ảnh nén còn khoảng 200 KB.
- Phát hành: PWA trước (iPhone cần thêm vào màn hình chính bằng Safari, Chrome hoặc Edge). CH Play (25 USD một lần, tài khoản cá nhân cần thử kín ít nhất 12 người trong 14 ngày), App Store sau.
- Chụp bill (chốt 14/10/2026): bill giấy chỉ để ghi nhớ ăn ở đâu, bao nhiêu; đọc tổng tiền là chính, chấp nhận sai, mặc định chia đều. Chỉ ảnh đơn đặt nhóm (Grab, ShopeeFood, đặt nước ở công ty) mới cần chính xác từng món, từng người. Đọc ảnh trên máy, miễn phí; không dùng AI trả phí, không đi xin ảnh mẫu từng ngân hàng.
- Kiếm tiền: phần lõi miễn phí; gói chuyến đi hoặc gói nhẹ trả phí; hoa hồng giới thiệu và quảng cáo để sau. Không chặn số khoản chi như Splitwise.

Còn mở: mức góp quỹ, màu chủ đạo và biểu tượng, tên gói trả phí, tra App Store / tên miền / nhãn hiệu cho "Done Nha", ảnh mẫu thông báo ngân hàng (Vietcombank, ACB, MB, Techcombank, MoMo, che số dư), việc Zalo Mini App có cho cá nhân đăng ký không.

## Lỗi đã gặp, đừng lặp lại
- Đừng nói chỉ Safari mới thêm được vào màn hình chính trên iPhone; Chrome và Edge cũng được.
- Giá gói của MoVi Group trên App Store Việt Nam là đồng (119.000 / 409.000 / 549.000), không phải USD.
- Sửa nguyên bảng trong tài liệu dễ mất định dạng; sửa từng ô hoặc từng dòng.
- Đặt mốc "app sẵn sàng" theo ngày đi trừ thời gian thử, không phải theo ngày đi.
- Số liệu pháp lý và giá Supabase chưa kiểm trên nguồn chính thức; kiểm lại trước khi dựa vào.
