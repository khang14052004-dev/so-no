# CLAUDE.md – Sổ nợ và Done Nha

Chủ dự án: Nguyên Khang (UI/UX designer). Giao tiếp bằng tiếng Việt, ngắn gọn, hành động trước; việc nhiều lựa chọn thì dùng bảng so sánh có đánh đổi. Việc nặng cỡ Opus thì báo cho anh biết.

## Index nhanh (đọc mục này trước)
| Cần gì | Xem ở đâu |
|---|---|
| Quyết định sản phẩm và thiết kế, theo ngày | Các mục "Chốt …" trong file này (mới nhất ở dưới cùng, trước "Lỗi đã gặp") |
| Lỗi đã gặp | Mục "Lỗi đã gặp, đừng lặp lại" cuối file |
| Định hướng sản phẩm | https://claude.ai/code/artifact/be6b0138-86ef-4cd1-bbf6-4a8a10dca24a |
| Kế hoạch đến tháng 1/2027 | https://claude.ai/code/artifact/1b8c88d0-e732-4508-a9e9-9040b27314f2 |
| Bảng thiết kế | Artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)": tìm bằng danh sách artifact, không ghi link vào repo |
| Quy tắc tính tiền, schema, test | `CLAUDE.md` và `README.md` của repo riêng tư `khang14052004-dev/done-nha` (nhánh `main`) |
| Script sinh bảng thiết kế | Gói `dn-tools.zip` do anh giữ riêng, không nằm trong repo nào |

## Nơi lưu trữ lịch sử dự án
| Chỗ | Lưu gì | Bền? |
|---|---|---|
| `CLAUDE.md` repo `so-no` (nhánh `claude/v3-ghi-no-nhieu-nguoi`) | Mọi quyết định sản phẩm và thiết kế, theo ngày chốt | Bền, có lịch sử commit |
| `CLAUDE.md` repo `done-nha` (riêng tư, `main`) | Quy tắc tính tiền, việc tiếp theo, ghi chú kỹ thuật | Bền, có lịch sử commit |
| Hai tài liệu claude.ai (Định hướng sản phẩm, Kế hoạch) | Hướng sản phẩm, kế hoạch chuyến đi | Bền |
| Artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)" | Toàn bộ bảng thiết kế (bản 208, 100 bảng) | Bền, có các bản cũ |
| `dn-tools.zip` (anh giữ, kèm README chạy lại) | Script sinh và chụp bảng thiết kế | Bền nếu anh giữ bản này |
| Thư mục tạm của phiên Claude, bản ghi hội thoại `.jsonl` | Script đang làm, ảnh chụp, file `.bak` | KHÔNG bền, mất khi phiên kết thúc |

Quy tắc giữ lịch sử:
- Quyết định chốt xong thì ghi vào `CLAUDE.md` ngay trong phiên, không để dành cuối ngày.
- Mỗi lần xuất bản canvas mới: cập nhật số bản, số bảng và các bảng thêm/sửa ở mục "Chốt" của ngày đó, rồi gửi lại `dn-tools.zip` cho anh chép về máy.
- Không ghi token, link cài đặt riêng, số tài khoản, số thẻ, khóa Supabase vào bất kỳ chỗ nào ở trên.

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

Còn mở: mức góp quỹ (2 triệu/người chỉ là dự kiến, chưa chốt được), màu chủ đạo chính thức và biểu tượng, tên gói trả phí, ảnh mẫu thông báo ngân hàng (Vietcombank, ACB, MB, Techcombank, MoMo, che số dư), việc Zalo Mini App có cho cá nhân đăng ký không.

## Quyết định thiết kế (14–15/10/2026)
Bảng thiết kế nằm trong artifact Design tên "Done Nha – Thiết kế (gộp Sổ nợ)" (tìm bằng danh sách artifact, không ghi link vào repo). Ảnh mẫu anh đưa chỉ để tham khảo, không làm giống; còn lại theo design system cũ của Sổ nợ. Bình luận "gửi cho Claude" trên artifact thì sửa trong artifact, trả lời trong thread, đóng thread, trong phiên chỉ ghi một dòng.
- Màu tiền: ĐỎ = người ta nợ bạn, XANH DƯƠNG = bạn nợ (cần góp quỹ), XANH LÁ = sạch nợ. Mỗi màn chỉ một nút vàng.
- Thanh menu dưới (5 mục): Sổ nợ, Nhóm, Báo nợ, Thống kê, Tôi. "Báo nợ" nằm ở thanh menu, không nằm trong thẻ Đang cho nợ (thẻ chỉ còn nút Mã QR). Icon Sổ nợ là cuốn sổ có gáy như bảng cũ: đặc khi đang chọn, viền khi không.
- Màn Sổ nợ tổng: thứ tự thẻ Đang cho nợ (đứng đầu, chốt 15/10), Ghi nhanh, danh sách Theo người (tab Tất cả | Nợ bạn | Bạn nợ). Ghi nhanh giữ như bảng Sổ nợ cũ: Ghi nợ | Ghi trả, ngày, chip chọn người có chip "Tất cả" đứng đầu, "+ Người mới", ô số tiền ("35k hoặc 25k+12", chip 12k–50k), ghi chú, nút vàng.
- Ghi trả nợ: thao tác nhanh bằng mũi tên xổ xuống ngay trên dòng người (chip Hết / 200k / 100k / Khác, nút "Ghi Lan trả 200k ✓"). Vào chi tiết chỉ khi cần; chi tiết không có Ảnh CK (đã có tin nhắn riêng hoặc nhóm). Ô số tiền ở chi tiết canh giữa cả ngang và dọc, số cỡ 30px.
- Gửi báo nợ: gửi qua tin nhắn, ứng dụng nào cũng được (Zalo, Messenger, SMS...), không gắn riêng Zalo. Đã bỏ cụm "Vì sao báo qua Zalo". Có: gửi chung 1 tin hoặc từng người, tùy chọn kèm từng ngày / tài khoản nhận tiền / mã QR / link xem sổ, xem trước tin, mã QR từng người. Các chữ "Zalo" trong bảng gộp đã đổi thành "tin nhắn", "nhóm".
- Cấn trừ chéo: ví dụ Minh nợ bạn 300k (Sổ riêng), bạn nợ Minh 120k (cơm trưa) thì còn 180k; chỉ làm khi bấm tay và Minh xác nhận.
- 15/10: đã vẽ tab Thống kê (Nợ | Nhóm, chuyến | Thẻ; bảng "Theo nơi" hai cột Nợ bạn / Bạn nợ) và tab Tôi (nhận tiền, dữ liệu, chi tiêu thẻ để sau, cài đặt, trạng thái đồng bộ). Các màn gộp đã nối link để bấm Play đi thử từ Sổ nợ tổng; bảng "Kiểm tra UX" liệt kê số lần chạm, chỗ rườm rà (R1–R4), chỗ thiếu (T1–T8) và 4 câu hỏi chờ anh chốt (ghi nhiều người mỗi người hay chia đều; chip Tất cả gồm ai; nút ghi chi nhanh cho chuyến; một chuông chung).
- Việc còn treo (cập nhật 16/10): đã che số tài khoản và tên chủ tài khoản ở Mobile-BaoZalo, Desktop-BaoZalo, Mobile-MaQR; bảng Sổ nợ cũ và bảng "Gộp" đã gắn nhãn "Sổ nợ cũ" / "Cũ" (không xóa). Đã vẽ đủ các màn trong danh sách cũ. Design System "Sổ nợ" đã đổi tên thành "Done Nha" và thêm màu tiền, thành phần mới.
- Bảng "Done Nha bấm thử" (15/10): một artboard 412×915 có state thật, cuộn trong khung, dùng để thử UX (ghi nợ/ghi trả cập nhật số, Hoàn tác, Nhắc nợ chọn sẵn người, Báo nợ đổi tin theo người chọn, Thêm khoản chi chia đều, Góp quỹ, Cân đối). Các bảng tĩnh chỉ để duyệt giao diện; nút trên bảng tĩnh không có hành vi.
- 15/10 chiều: bảng bấm thử có thêm trang xem sổ qua link (người nợ mở web, bấm "Mình đã chuyển" thì vào Chờ xác nhận), màn lần đầu (vào bằng khách/Google/Apple), tài khoản nhận tiền nhiều TK (vé QR vuốt đổi TK, số TK luôn che), cài đặt chuyến (đổi thủ quỹ có bàn giao, ủy quyền ghi chi quỹ), chi tiết khoản chi (lịch sử, sửa, xóa có Hoàn tác; ai ghi mới sửa, chi quỹ chỉ thủ quỹ/ủy quyền), nhóm không quỹ (Cơm trưa, nhóm mới), tạo nhóm, mời, vào nhóm bằng link/QR, sửa hồ sơ, nhập từ ảnh, chụp bill. Cân đối gộp quỹ vào thủ quỹ (không còn dòng "Quỹ → Kiệt"). "Ai trả" mặc định là thủ quỹ.
- 15/10 tối (theo góp ý anh): khoản chi trước chuyến chỉ là đặt cọc, vé xe, đồ mang theo, dụng cụ (không có ăn uống khi chưa đi). Số dư chuyến: hai ô "Bạn sẽ nhận / Bạn cần trả" kèm tên người, danh sách "Với từng người" mô tả ngắn, khối "Tiền của bạn trong chuyến" (ứng trước, phần của bạn, góp quỹ, phần dùng từ quỹ). Icon cài đặt là bánh răng. Góp quỹ chỉ hiện 1 STK thủ quỹ gửi, không đổi số tiền. Thống kê Nhóm, chuyến liệt kê mọi nhóm, bấm để xem chi tiết; "Tiền chi từ đâu" có chú thích màu. Thanh menu 6 mục: Sổ nợ, Chia bill, Nhóm, Báo nợ, Thống kê, Tôi. Mọi chỗ thêm tên: trùng thì hỏi "có phải người này không", chọn Người khác thì báo trùng để đặt tên khác. Đăng ký có thêm số điện thoại + mã 6 số.
- Bảng tĩnh tổng thể (15/10): 53 bảng `DN-*.dc.html` chụp từ bảng bấm thử bằng tools/snap.py + states.json, xếp 5 hàng dưới cùng canvas; các bảng "Gộp" cũ phía trên đã lỗi thời.
- Script sinh bảng thiết kế (gen_dn.py, gen_dn2.py, shoot2.py, gen_proto.py, proto_logic.js, proto_screens.py, snap.py, states.json) KHÔNG lưu vào repo công khai; bản lưu riêng của anh (17/10, gói dn-tools.zip kèm README chạy lại).

- Quy tắc vẽ danh sách/bảng (anh nhắc 2 lần, 15/10): dòng CUỐI của mọi bảng thông tin, danh sách, khối dòng KHÔNG có đường line phía dưới; chỉ có line ngăn giữa các dòng. Kiểm trước khi đăng.

## Chốt 16/10/2026
- Mô hình số dư nhóm: cách 3 "lai". Trong chuyến/nhóm tính một nồi (quỹ là thành viên ảo do thủ quỹ giữ), gợi ý chuyển chỉ là tạm tính; bấm Cân đối thì khóa, mới ghi nợ theo từng cặp vào Sổ nợ. Trả tiền khoản của nhóm thì ghi vào sổ nhóm, không ghi vào Sổ riêng.
- Thẻ đầu và danh sách Sổ nợ: kiểu D. Hiện số đã trừ qua lại cho gọn (chỉ để xem); người có nhiều nơi thì mũi tên xổ xuống mở bảng từng nơi (+ nợ bạn, − bạn nợ), dòng "đã trừ để dễ xem · chưa cấn trừ", nút Cấn trừ và Ghi trả theo từng nơi. Cấn trừ chỉ nằm trong chi tiết từng người, không đưa lên thẻ đầu. Ghi trả, báo nợ, trang xem sổ vẫn tính từng nơi cho tới khi người kia đồng ý cấn trừ.
- Nhóm Cơm trưa (nhóm dài hạn, không quỹ): trong tuần tính một nồi, chốt tuần vào thứ Bảy; ai thích thì trả từng buổi ("Trả buổi này" cho người trả bữa đó); ai mai nghỉ thì "Chốt riêng" cho người đó (tính phần của họ tới hôm nay, trả xong là sạch), người còn lại chốt thứ Bảy.
- Làm tròn khi chuyển tiền: tới 1.000đ, phần lẻ từ 500đ trở lên làm tròn lên, dưới 500đ bỏ (1.500đ → 2.000đ, 1.499đ → 1.000đ). Chênh lệch vài trăm đồng do người nhận tiền chịu.
- Đã làm trong bảng bấm thử (16/10): kiểu D ở Sổ nợ (xổ xuống từng nơi, Cấn trừ có giả lập người kia đồng ý, Ghi trả theo từng nơi); báo nợ và trang xem sổ xin theo từng nơi, người kia đồng ý trừ ngay trên trang; Ghi nhanh chia đều có "Gồm cả phần bạn" và làm tròn; Cân đối làm tròn 1.000đ; Cơm trưa theo tuần (Trả buổi này, Chốt riêng, Chốt tuần ghi vào Sổ nợ). Bảng tĩnh tổng thể giờ 61 bảng (thêm Minh xổ xuống, ghi trả từng nơi, chờ cấn trừ, chia đều, trang xem sổ của Minh, chốt tuần, chốt riêng).
- Sửa lỗi rà soát lần 2 (16/10, bảng bấm thử): Ghi nhanh có "Họ nợ bạn | Bạn nợ họ", Ghi trả tự biết chiều theo số dư và cảnh báo trả dư; Cân đối có nút Khóa (chỉ thủ quỹ), trước khóa chỉ là tạm tính và Sổ nợ hiện mục "Nhóm chưa chốt", sau khóa mới ghi nợ từng cặp; trả tiền chuyến ghi vào sổ chuyến, phát sinh sau khóa thành "đợt 2"; đổi thủ quỹ có bàn giao (quỹ vẫn ở người cũ tới khi xác nhận); góp quỹ chưa xác nhận thì cảnh báo trước khi khóa; khối "Tiền của bạn trong chuyến" cộng lại khớp Cân đối; Chia bill chọn "Ai trả đơn" và báo lỗi giảm giá lớn hơn tiền món; ô số tiền hiểu "2tr5", "1k5". Bảng tĩnh tổng thể giờ 68 bảng.
- Chốt 16/10 chiều (anh trả lời 4 câu hỏi; anh dùng Opus cho mọi việc): Ghi nhanh bỏ "Ai nợ ai" (đã có Ghi nợ | Ghi trả); chọn nhiều người thì mỗi người cùng số tiền (mặc định), bỏ chia đều ở Ghi nhanh. Chia đều nằm ở tab Chia bill: tổng tiền ÷ số người (tính cả bạn), chưa cần biết ai, bấm Ghi nợ thì sang Sổ nợ điền sẵn số tiền mỗi người để chọn người. Chip "Tất cả" là chọn hết; có Cài đặt Ghi nhanh để tạo chip nhóm (vd "Cơm trưa · 5") và sửa chip số tiền. Dùng một chuông chung cho cả app (màn Thông báo + Cài đặt thông báo). Anh hỏi "ghi chi nhanh cho nhóm có khác khoản chi không": cùng dữ liệu, chỉ là lối tắt (thẻ chuyến đã có nút + Khoản chi); chưa chốt có làm thêm lối tắt hay không.
- Đã vẽ 16/10 chiều trong bảng bấm thử: màn trống (tài khoản mới), mất mạng, gửi lỗi, sửa trùng trên 2 máy (chọn bản giữ), lưu trữ chuyến (chỉ ẩn ở máy mình, cần khóa cân đối trước), nhóm đã lưu trữ, sao lưu và khôi phục (khôi phục chỉ Sổ riêng), xuất CSV, nhập từ Sổ nợ cũ (chọn file, ghép tên, xem trước, hoàn tác), chi tiêu thẻ (màn mẫu, phần quét vẫn ở Apps Script). Công tắc giả lập nằm ở Tôi › Bản thử. Bảng tĩnh tổng thể giờ 94 bảng, 6 hàng.

## Chốt 17/10/2026
- Tra tên "Done Nha" (anh tự tra): hiện không thấy trùng; việc tra tên coi như xong, chỉ cần tra lại gần ngày đưa lên cửa hàng.
- Mức góp quỹ 2 triệu/người chỉ là dự kiến, chưa chốt; thiết kế không được ghi cứng con số này.
- Chia đều (tab Chia bill): số người gõ thẳng được, từ 2 đến 50, nhãn "Số người" (không phải "Số người ăn", vì còn đi chơi, uống, đá banh, cầu lông). Gõ 1 hoặc trống thì báo "Ít nhất 2 người".
- Tổng tiền đọc được từ ảnh bill là ô gõ được (camera và Nhập từ ảnh › bill giấy), hiểu "412k", "1tr2", sai thì nút mờ. Anh xác nhận đúng ý (thread "cho chỉnh sửa số tiền").
- Lối tắt "+ Khoản chi" (chốt có làm): nằm cuối thẻ Ghi nhanh ở Sổ nợ, chỉ hiện khi có chuyến; mở tờ Thêm khoản chi của chuyến, cùng dữ liệu với khoản chi thường, chỉ là lối tắt.
- Tờ Thêm khoản chi: hai nút Chụp bill và Done nha ✓ ghim sát đáy, nền đặc, viền trên 1px, bóng nhẹ; danh sách chia đều cuộn bên trên.
- Thanh menu dưới: cả 6 icon đều đặc khi chọn (Sổ nợ, Chia bill, Nhóm, Báo nợ, Thống kê, Tôi), viền khi không chọn.
- Thanh tiêu đề trang con (có nút quay lại) ghim trên cùng khi cuộn; chưa cuộn thì không bóng, cuộn xuống thì nền nguyên khối kèm bóng đổ phía dưới. Hàng thẻ ở Thống kê có lề trái 16px khi vuốt.
- Bảng tĩnh tổng thể: 94 bảng, 6 hàng; chín bảng Sổ nợ dài thêm 65px do lối tắt mới.
- Code Done Nha nằm ở repo RIÊNG TƯ `khang14052004-dev/done-nha` (nhánh main, chốt 18/10): `core/ledger.js` lõi sổ cái + test, `supabase/schema.sql` + `supabase/test/run.sh` (chạy thử trên Postgres tạm). Chỗ chạy app (Cloudflare Pages hoặc Netlify, gói miễn phí) chọn khi có bản đầu. Đăng ký bằng số điện thoại: anh CHỐT BỎ ngày 18/10 (SMS tốn phí).
- Tiến độ: pha 1 thiết kế kết thúc 25/10; pha 2 nền tảng (Supabase) bắt đầu 26/10; ngừng thêm tính năng 20/12; app sẵn sàng 28/12.

## Chốt 18/10/2026
- Bỏ đăng ký bằng số điện thoại + mã 6 số (anh chốt). Đăng nhập: khách + Google; Apple để sau (cần Apple Developer trả phí). Phải bật "Allow manual linking" trên Supabase khi làm nâng khách lên Google.
- Code Done Nha ở repo RIÊNG TƯ `khang14052004-dev/done-nha` (anh tự tạo repo và cấp quyền cho ứng dụng Claude trên GitHub; phiên Claude không tự tạo repo được). Chạy kiểm thử: `npm test` (lõi) và `bash supabase/test/run.sh` (schema trên Postgres 16 tạm). File SQL CHƯA chạy trên Supabase thật: 26/10 anh dán vào SQL Editor.
- Rà soát tính tiền 18/10: 30 bài test lõi + 500 chuyến ngẫu nhiên; 85 kiểm tra SQL; 40 chuyến ghi vào Postgres khớp lõi JS; bản bấm thử trên canvas lệch tối đa 1đ (dồn đồng lẻ khác), số chuyển sau làm tròn giống hệt.
- Quy tắc tính tiền mới (đã có trong code): khóa cân đối LƯU kế hoạch chuyển (nợ từng cặp, bảng settlement_transfers), máy chủ kiểm kế hoạch khớp số dư; mỗi lần khóa mở đợt mới (chuyến: đợt 2; Cơm trưa: mỗi tuần một đợt); trả theo nợ từng cặp ghi vào đúng đợt cũ và TRỪ khỏi kế hoạch; khóa không tính khoản góp chưa xác nhận; thủ quỹ tự trả hay trả từ quỹ cho cùng số cuối; quỹ âm thì thủ quỹ được nhận lại; chia đều ghi Sổ nợ: người khác nợ số tròn, người trả chịu lẻ; làm tròn theo bước nhóm chọn 1.000 (mặc định) / 5.000 / 10.000; Sổ riêng không vào bằng link; chủ nhóm hoặc thủ quỹ "mở lại tên" cho người mất phiên khách; STK nhận tiền chỉ hiện cho nhóm khi người đó bật chia sẻ.
- Nghiên cứu 18/10 (báo cáo trong phiên): iPhone tách bộ nhớ giữa Safari và app ở màn hình chính, nên phiên khách mất khi thêm vào màn hình chính → phải "Lưu bằng Google" hoặc link khôi phục TRƯỚC khi thêm. Trình duyệt trong Zalo không thêm vào màn hình chính được → trang đích nhận ra Zalo, chỉ cho xem, nút Mở bằng Safari + Chép link. Đẩy thông báo trên iPhone chỉ khi đã thêm vào màn hình chính → nhắc nợ bằng tin nhắn là chính. VietQR tự tạo trên máy, nội dung không dấu ≤25 ký tự, số tiền nguyên; MoMo: người dùng tải ảnh QR nhận tiền của mình, không tự sinh. Pháp lý: NĐ 52/2024 nhiều khả năng không áp (app không giữ tiền); Luật BVDLCN 91/2025 + NĐ 356/2025 hiệu lực 1/1/2026: cần đồng ý, lưu ở Singapore có thể phải lập hồ sơ chuyển dữ liệu ra nước ngoài trong 60 ngày, STK có thể là dữ liệu nhạy cảm → STK cá nhân giữ trên máy; hỏi luật sư trước khi mở cho người ngoài nhóm bạn.
- Việc UI theo rà soát: ĐÃ LÀM trên canvas ngày 18/10 (bản 203), bảng tĩnh giờ 96 bảng, 6 hàng.
  - Đã bỏ: đăng ký SĐT + OTP (màn lần đầu, sheet Lưu tài khoản; gỡ bảng DN-Dau-SDT, DN-Dau-OTP, DN-LienKet-OTP); ô SĐT ở Thêm người mới và Sửa hồ sơ; nút Apple và các câu "Google hoặc Apple"; Chi tiêu thẻ (dòng ở Tôi, tab Thẻ ở Thống kê, bảng DN-TheChiTieu, DN-TheChiTieu-Mau, DN-TK-The).
  - Đã thêm: màn lần đầu có bước "Dữ liệu của bạn" (Đồng ý và tiếp tục; DN-Dau-DongY); sau khi nhận tên vào màn "Giữ chỗ của bạn" (Lưu bằng Google / Chép link khôi phục / Để sau, lưu xong hiện 3 bước thêm vào màn hình chính; DN-VaoNhom-Luu, DN-VaoNhom-Luu-Xong); tên đã có người nhận báo nhờ thủ quỹ mở lại; Cài đặt chuyến có "Mở lại tên" (DN-CaiDat-MoLai), "Làm tròn khi chuyển" 1.000/5.000/10.000đ (Cân đối đổi theo), dòng "Ảnh hóa đơn tự xóa 30 ngày sau khi khóa cân đối", "Xóa chuyến" (chỉ khi đã khóa và chuyển xong); màn link mời mở trong Zalo (Mở bằng Safari, Chép link; DN-VaoNhom-Zalo, mở từ Tôi › Bản thử); Tôi › Quyền riêng tư và dữ liệu (lưu gì, ở đâu, xuất CSV, xóa tài khoản sau 7 ngày; DN-QuyenRiengTu, DN-QuyenRiengTu-Xoa); Tài khoản nhận tiền có công tắc "Cho nhóm thấy", ví MoMo dùng ảnh QR tải lên thay số (DN-TaiKhoan-MoMo); máy ảnh ghi chú ảnh tự xóa 30 ngày. Nút "Liên kết tài khoản" đổi thành "Lưu tài khoản".
  - Hoãn sau chuyến: Nhập từ Sổ nợ cũ, cài đặt thông báo đẩy (giữ chuông trong app).
- Tài liệu kế hoạch đã đổi tên "Done Nha – kế hoạch đến tháng 1/2027" và cập nhật 18/10: gộp app, Supabase đã tạo, việc của anh (tick xong), rủi ro iPhone/Zalo/dữ liệu cá nhân, 3 mục mới (Rà soát 18/10, Phương án thực tế cho người Việt, Pháp lý).

## Chốt 21/10/2026
- Lịch (anh đưa ảnh một app lịch chi tiêu có ảnh món; chỉ tham khảo, không làm giống) nằm TRONG TỪNG NHÓM/CHUYẾN, không ở Thống kê.
  - Bấm vào nhóm là thấy Lịch ngay (mặc định). Lịch GỘP với khoản chi: dưới lịch là danh sách khoản chi cả tháng; bấm một ngày thì lọc ngày đó, có nút "Cả tháng" để bỏ lọc.
  - Chuyến: "Lịch | Số dư | Quỹ" (bỏ mục Khoản chi riêng). Lịch chuyến đổi được tới tháng đi; ngày đi có viền nét đứt và nhãn "Đi".
  - Cơm trưa: "Lịch | Tuần này" (Tuần này giữ Trả ngay, Chốt riêng, Chốt tuần).
  - Link riêng tới Số dư/Quỹ (Sổ nợ, thông báo, góp quỹ) vẫn mở đúng mục đó.
- Thẻ đầu Lịch:
  - Chuyến: "Cả chuyến đã tiêu" + "Tháng này · cả nhóm" + "Phần của bạn cả chuyến".
  - Nhóm dài hạn: "Cả nhóm đã tiêu · tháng này" + "Phần của bạn tháng này" + "Từ lúc lập nhóm".
- Ô lịch:
  - Ô vuông.
  - Số trong ô là CẢ NHÓM tiêu trong ngày, chữ 10px (nhỏ hơn 1 cỡ).
  - Màu theo MỨC MỖI NGƯỜI trong ngày: xanh lá dưới 100k, vàng cam 100k–500k, đỏ từ 500k. Dùng nền nhạt, có chú thích "Mỗi người/ngày". Anh chốt dùng 3 màu này dù trùng màu tiền.
  - Ô có ảnh thì ảnh làm nền. Hôm nay có chấm tròn; ngày chọn viền xanh.
- Nút "+ Ghi khoản chi" / "+ Ghi bữa ăn" ghim sát đáy màn nhóm/chuyến (nền đặc, viền trên 1px, bóng nhẹ). Ở chuyến chỉ ghim ở mục Lịch, vì Số dư đã có nút vàng Cân đối.
- ẢNH (chốt lại 21/10 tối): lưu trên MÁY CHỦ cùng khoản chi để CẢ NHÓM thấy, giống Zalo. Thay hai ý cũ: "chỉ trên máy" (chiều 21/10) và "tự xóa 30 ngày sau khóa" (18/10).
  - Ảnh giữ tới khi người chụp xóa hoặc xóa nhóm. Chỉ người chụp có nút Xóa ảnh.
  - Chi tiết khoản chi có khối "Ảnh": ai chụp, Xem ảnh, Xóa ảnh (người chụp), Thêm ảnh bill.
  - Kho: Supabase Storage (bucket `receipts` đã có trong schema, RLS theo thành viên). Gói Free (kiểm 21/10): 1 GB lưu, 5 GB tải xuống chưa cache + 5 GB đã cache, tối đa 50 MB/tệp. KHÔNG có biến đổi ảnh (Image Transformations chỉ từ Pro), nên tự nén trên máy: ảnh ~200 KB + ảnh nhỏ ~15 KB cho ô lịch.
  - Cloudflare R2 (10 GB-tháng, tải xuống miễn phí) để dành khi vượt 1 GB.
  - Ảnh đơn Grab/ShopeeFood có tên, SĐT, địa chỉ người nhận, nên nhắc che trước khi lưu.
- Canvas bản 208:
  - Thêm DN-Chuyen-Lich-Ngay, DN-Chuyen-Lich-NgayDi, DN-Com-Lich, DN-Com-Lich-Ngay. DN-Chuyen-KhoanChi giờ là màn chuyến mở ra (Lịch).
  - Bảng tĩnh 100 bảng, 6 hàng.
  - Số Cơm trưa trước 12/10 chỉ là số mẫu; ảnh món là hình vẽ tay.

## Lỗi đã gặp, đừng lặp lại
- Trả tiền theo kế hoạch đã khóa phải TRỪ khỏi kế hoạch, không cộng thành lượt chuyển mới (lỗi bắt được khi viết test 18/10).
- Đừng nói chỉ Safari mới thêm được vào màn hình chính trên iPhone; Chrome và Edge cũng được.
- Giá gói của MoVi Group trên App Store Việt Nam là đồng (119.000 / 409.000 / 549.000), không phải USD.
- Sửa nguyên bảng trong tài liệu dễ mất định dạng; sửa từng ô hoặc từng dòng.
- Đặt mốc "app sẵn sàng" theo ngày đi trừ thời gian thử, không phải theo ngày đi.
- Supabase gói Free đã kiểm 17/10/2026 trên trang giá chính thức: 500 MB số liệu, 1 GB ảnh, 5 GB tải xuống, 50.000 người dùng/tháng, tối đa 2 dự án, tự ngủ sau 1 tuần không dùng. Đăng nhập Apple cần tài khoản Apple Developer (chưa kiểm giá); chuyến Đà Lạt dùng khách và Google trước. Pháp lý đã nghiên cứu 18/10 (xem mục Chốt 18/10) nhưng chỉ là suy luận từ văn bản, chưa có ý kiến luật sư.
- Địa chỉ dự án Supabase và khóa publishable chỉ nằm trong file cấu hình của app, không ghi vào tài liệu hay trí nhớ; khóa secret và service_role, mật khẩu cơ sở dữ liệu thì tuyệt đối không đưa cho Claude hay ghi ở đâu.
