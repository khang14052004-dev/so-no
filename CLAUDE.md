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

- Gộp app (chốt 14/10/2026): Sổ nợ và Done Nha gộp thành MỘT app tên **Done Nha**, mô hình "1 app, 2 không gian, 1 sổ cái": Sổ cá nhân (ghi hộ, riêng tư) và Nhóm/Chuyến (thủ quỹ). Màn "Sổ nợ tổng" theo người chỉ để xem; không tự bù trừ, cấn trừ chéo phải bấm tay và người kia xác nhận. Quét thẻ giữ ở Apps Script, làm sau. Màu tạm dùng vàng #FFC925 và xanh #163D89 của Sổ nợ.

Còn mở: mức góp quỹ, màu chủ đạo chính thức và biểu tượng, tên gói trả phí, tra App Store / tên miền / nhãn hiệu cho "Done Nha", ảnh mẫu thông báo ngân hàng (Vietcombank, ACB, MB, Techcombank, MoMo, che số dư), việc Zalo Mini App có cho cá nhân đăng ký không.

## Quyết định thiết kế (14–15/10/2026)
Bảng thiết kế nằm trong artifact Design tên "Done Nha – Thiết kế (gộp Sổ nợ)" (tìm bằng danh sách artifact, không ghi link vào repo). Ảnh mẫu anh đưa chỉ để tham khảo, không làm giống; còn lại theo design system cũ của Sổ nợ. Bình luận "gửi cho Claude" trên artifact thì sửa trong artifact, trả lời trong thread, đóng thread, trong phiên chỉ ghi một dòng.
- Màu tiền: ĐỎ = người ta nợ bạn, XANH DƯƠNG = bạn nợ (cần góp quỹ), XANH LÁ = sạch nợ. Mỗi màn chỉ một nút vàng.
- Thanh menu dưới (5 mục): Sổ nợ, Nhóm, Báo nợ, Thống kê, Tôi. "Báo nợ" nằm ở thanh menu, không nằm trong thẻ Đang cho nợ (thẻ chỉ còn nút Mã QR). Icon Sổ nợ là cuốn sổ có gáy như bảng cũ: đặc khi đang chọn, viền khi không.
- Màn Sổ nợ tổng: thứ tự thẻ Đang cho nợ (đứng đầu, chốt 15/10), Ghi nhanh, danh sách Theo người (tab Tất cả | Nợ bạn | Bạn nợ). Ghi nhanh giữ như bảng Sổ nợ cũ: Ghi nợ | Ghi trả, ngày, chip chọn người có chip "Tất cả" đứng đầu, "+ Người mới", ô số tiền ("35k hoặc 25k+12", chip 12k–50k), ghi chú, nút vàng.
- Ghi trả nợ: thao tác nhanh bằng mũi tên xổ xuống ngay trên dòng người (chip Hết / 200k / 100k / Khác, nút "Ghi Lan trả 200k ✓"). Vào chi tiết chỉ khi cần; chi tiết không có Ảnh CK (đã có tin nhắn riêng hoặc nhóm). Ô số tiền ở chi tiết canh giữa cả ngang và dọc, số cỡ 30px.
- Gửi báo nợ: gửi qua tin nhắn, ứng dụng nào cũng được (Zalo, Messenger, SMS...), không gắn riêng Zalo. Đã bỏ cụm "Vì sao báo qua Zalo". Có: gửi chung 1 tin hoặc từng người, tùy chọn kèm từng ngày / tài khoản nhận tiền / mã QR / link xem sổ, xem trước tin, mã QR từng người. Các chữ "Zalo" trong bảng gộp đã đổi thành "tin nhắn", "nhóm".
- Cấn trừ chéo: ví dụ Minh nợ bạn 300k (Sổ riêng), bạn nợ Minh 120k (cơm trưa) thì còn 180k; chỉ làm khi bấm tay và Minh xác nhận.
- 15/10: đã vẽ tab Thống kê (Nợ | Nhóm, chuyến | Thẻ; bảng "Theo nơi" hai cột Nợ bạn / Bạn nợ) và tab Tôi (nhận tiền, dữ liệu, chi tiêu thẻ để sau, cài đặt, trạng thái đồng bộ). Các màn gộp đã nối link để bấm Play đi thử từ Sổ nợ tổng; bảng "Kiểm tra UX" liệt kê số lần chạm, chỗ rườm rà (R1–R4), chỗ thiếu (T1–T8) và 4 câu hỏi chờ anh chốt (ghi nhiều người mỗi người hay chia đều; chip Tất cả gồm ai; nút ghi chi nhanh cho chuyến; một chuông chung).
- Việc còn treo: bảng cũ Mobile-BaoZalo và Mobile-MaQR còn hiện số tài khoản đầy đủ (MaQR còn tên chủ tài khoản), cần che; bảng cũ Mobile-BaoZalo, Desktop-BaoZalo, Main chưa đổi theo bảng gộp; chưa vẽ Cài đặt nhóm, Lưu trữ nhóm, Sao lưu/xuất CSV, Nhập từ Sổ nợ cũ, Chi tiêu thẻ, danh sách Khoản chi, màn lần đầu và màn trống; Design System chưa cập nhật cho Done Nha.
- Bảng "Done Nha bấm thử" (15/10): một artboard 412×915 có state thật, cuộn trong khung, dùng để thử UX (ghi nợ/ghi trả cập nhật số, Hoàn tác, Nhắc nợ chọn sẵn người, Báo nợ đổi tin theo người chọn, Thêm khoản chi chia đều, Góp quỹ, Cân đối). Các bảng tĩnh chỉ để duyệt giao diện; nút trên bảng tĩnh không có hành vi.
- 15/10 chiều: bảng bấm thử có thêm trang xem sổ qua link (người nợ mở web, bấm "Mình đã chuyển" thì vào Chờ xác nhận), màn lần đầu (vào bằng khách/Google/Apple), tài khoản nhận tiền nhiều TK (vé QR vuốt đổi TK, số TK luôn che), cài đặt chuyến (đổi thủ quỹ có bàn giao, ủy quyền ghi chi quỹ), chi tiết khoản chi (lịch sử, sửa, xóa có Hoàn tác; ai ghi mới sửa, chi quỹ chỉ thủ quỹ/ủy quyền), nhóm không quỹ (Cơm trưa, nhóm mới), tạo nhóm, mời, vào nhóm bằng link/QR, sửa hồ sơ, nhập từ ảnh, chụp bill. Cân đối gộp quỹ vào thủ quỹ (không còn dòng "Quỹ → Kiệt"). "Ai trả" mặc định là thủ quỹ.
- 15/10 tối (theo góp ý anh): khoản chi trước chuyến chỉ là đặt cọc, vé xe, đồ mang theo, dụng cụ (không có ăn uống khi chưa đi). Số dư chuyến: hai ô "Bạn sẽ nhận / Bạn cần trả" kèm tên người, danh sách "Với từng người" mô tả ngắn, khối "Tiền của bạn trong chuyến" (ứng trước, phần của bạn, góp quỹ, phần dùng từ quỹ). Icon cài đặt là bánh răng. Góp quỹ chỉ hiện 1 STK thủ quỹ gửi, không đổi số tiền. Thống kê Nhóm, chuyến liệt kê mọi nhóm, bấm để xem chi tiết; "Tiền chi từ đâu" có chú thích màu. Thanh menu 6 mục: Sổ nợ, Chia bill, Nhóm, Báo nợ, Thống kê, Tôi. Mọi chỗ thêm tên: trùng thì hỏi "có phải người này không", chọn Người khác thì báo trùng để đặt tên khác. Đăng ký có thêm số điện thoại + mã 6 số.
- Bảng tĩnh tổng thể (15/10): 53 bảng `DN-*.dc.html` chụp từ bảng bấm thử bằng tools/snap.py + states.json, xếp 5 hàng dưới cùng canvas; các bảng "Gộp" cũ phía trên đã lỗi thời.
- Script sinh bảng thiết kế (gen_dn.py, gen_dn2.py, shoot2.py, gen_proto.py, proto_logic.js, proto_screens.py, snap.py, states.json) chỉ nằm trong thư mục tạm của phiên, chưa lưu vào repo; mất khi phiên bị thu hồi.

- Quy tắc vẽ danh sách/bảng (anh nhắc 2 lần, 15/10): dòng CUỐI của mọi bảng thông tin, danh sách, khối dòng KHÔNG có đường line phía dưới; chỉ có line ngăn giữa các dòng. Kiểm trước khi đăng.

## Lỗi đã gặp, đừng lặp lại
- Đừng nói chỉ Safari mới thêm được vào màn hình chính trên iPhone; Chrome và Edge cũng được.
- Giá gói của MoVi Group trên App Store Việt Nam là đồng (119.000 / 409.000 / 549.000), không phải USD.
- Sửa nguyên bảng trong tài liệu dễ mất định dạng; sửa từng ô hoặc từng dòng.
- Đặt mốc "app sẵn sàng" theo ngày đi trừ thời gian thử, không phải theo ngày đi.
- Số liệu pháp lý và giá Supabase chưa kiểm trên nguồn chính thức; kiểm lại trước khi dựa vào.
