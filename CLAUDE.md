# CLAUDE.md – Sổ nợ và Done Nha

Chủ dự án: Nguyên Khang (UI/UX designer). Giao tiếp bằng tiếng Việt, ngắn gọn, hành động trước; việc nhiều lựa chọn thì dùng bảng so sánh có đánh đổi. Việc nặng cỡ Opus thì báo cho anh biết.

## Index nhanh (đọc mục này trước)
| Cần gì | Xem ở đâu |
|---|---|
| **Mở phiên mới / đổi model** | `docs/ban-giao-phien.md` (đọc đầu tiên: đọc gì, đang dở gì, chọn model) |
| **Anh nhắn "Báo cáo"** | `docs/bao-cao-tien-do.md`: gửi báo cáo (đã xong, tiếp theo, % tiến độ, việc trễ) theo mẫu, rồi cập nhật file đó |
| Việc theo tuần tới 28/12 | `docs/ke-hoach-tuan.md` |
| Quyết định đang áp dụng | Mục "Quyết định đang áp dụng" + các mục "Chốt …" trong file này (mới nhất ở dưới cùng) |
| Lịch sử chốt 14–18/10 (nguyên văn) | `docs/lich-su-chot-2026-10.md` |
| Đề xuất Xấp ảnh cho chuyến | `docs/de-xuat-xap-anh.md` |
| Lỗi đã gặp | Mục "Lỗi đã gặp, đừng lặp lại" cuối file |
| Định hướng sản phẩm | https://claude.ai/code/artifact/be6b0138-86ef-4cd1-bbf6-4a8a10dca24a |
| Kế hoạch đến tháng 1/2027 | https://claude.ai/code/artifact/1b8c88d0-e732-4508-a9e9-9040b27314f2 |
| Bảng thiết kế | Artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)": tìm bằng danh sách artifact, không ghi link vào repo |
| Quy tắc tính tiền, schema, test | `CLAUDE.md` và `README.md` của repo riêng tư `khang14052004-dev/done-nha` (nhánh `main`) |
| Script sinh bảng thiết kế | Gói `dn-tools.zip` do anh giữ riêng, không nằm trong repo nào |
| Màu, chữ, khoảng cách (token) | Artifact Design System "Done Nha" (tìm bằng danh sách artifact) |
| Tài nguyên, bản xuất, bàn giao từng màn, tiến độ tuần, mẫu quy trình UX/UI | Thư mục `So-no/done-nha-workspace` trên máy anh: đọc `00-START-HERE.md` |

## Nơi lưu trữ lịch sử dự án
| Chỗ | Lưu gì | Bền? |
|---|---|---|
| `CLAUDE.md` repo `so-no` (nhánh `claude/v3-ghi-no-nhieu-nguoi`) | Quyết định đang áp dụng, theo ngày chốt | Bền, có lịch sử commit |
| `docs/` repo `so-no` | Bàn giao phiên, kế hoạch tuần, lịch sử chốt cũ, đề xuất đang chờ | Bền, có lịch sử commit |
| `CLAUDE.md` repo `done-nha` (riêng tư, `main`) | Quy tắc tính tiền, việc tiếp theo, ghi chú kỹ thuật | Bền, có lịch sử commit |
| Hai tài liệu claude.ai (Định hướng sản phẩm, Kế hoạch) | Hướng sản phẩm, kế hoạch chuyến đi | Bền |
| Artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)" | Toàn bộ bảng thiết kế (bản 224, 115 bảng) | Bền, có các bản cũ |
| `dn-tools.zip` (anh giữ, kèm README chạy lại) | Script sinh và chụp bảng thiết kế | Bền nếu anh giữ bản này |
| Artifact Design System "Done Nha" | Token màu, chữ, khoảng cách, bo góc, bóng; thành phần | Bền, có các bản cũ |
| Thư mục `So-no/done-nha-workspace` trên máy anh | Bản xuất PDF/PNG, ảnh gốc, nghiên cứu gốc, bàn giao từng màn (`07-handoff`), `_progress.md`, mẫu quy trình (`_mau`) | Bền nếu anh sao lưu (không phải git) |
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
- Anh nhắn **"Báo cáo"** (anh dặn 30/10): làm theo `docs/bao-cao-tien-do.md`, gửi trong chat, ghi đè "Bản mới nhất" và thêm dòng "Lịch sử %".

## Dự án mới: Done Nha (app quỹ nhóm và chia tiền chuyến đi)
Tài liệu gốc (đọc trước khi làm):
- Định hướng sản phẩm: https://claude.ai/code/artifact/be6b0138-86ef-4cd1-bbf6-4a8a10dca24a
- Kế hoạch chuyến đi: https://claude.ai/code/artifact/1b8c88d0-e732-4508-a9e9-9040b27314f2

Đã chốt (13/10/2026):
- Tên app: **Done Nha**. Nhà phát triển: **Nguyên Khang**. Slogan: "Hùn chung đi chơi, tính tiền khỏi cãi."
- Giọng văn Nam bộ, Sài Gòn: nha, nè, lẹ, khỏi. "Tui, hông, dzô" chỉ ở chỗ vui. Nút chính "Done nha ✓". Tránh chữ "kèo" và "hụi".
- Chuyến đầu tiên: Đà Lạt, tối 2/1 đến chiều 5/1/2027, 7–9 người, chỉ anh dùng Android, còn lại iPhone. (Cập nhật 28/10: các bạn dùng iPhone chủ yếu dùng **Chrome**, không phải Safari.) Thủ quỹ: Kiệt (đổi được). Góp quỹ bằng chuyển khoản và tiền mặt, dự kiến 2 triệu/người (chưa chốt). App phải xong trước 28/12/2026.
- Lõi là sổ cái (ledger); quỹ chung là "thành viên ảo". Số dư luôn tính từ sổ, không lưu riêng. Cân đối tối thiểu số lần chuyển, VietQR điền sẵn cho từng người.
- Chỉ thủ quỹ (hoặc người thủ quỹ ủy quyền) được ghi khoản chi từ quỹ; thành viên vẫn tự ghi khoản mình trả.
- App KHÔNG bao giờ giữ tiền (tránh bị coi là trung gian thanh toán, Nghị định 52/2024). Quỹ chỉ là con số; tiền thật nằm ở thủ quỹ.
- Kiến trúc: ghi trên điện thoại trước, đồng bộ sau; Supabase (đăng nhập khách/Google/Apple, Postgres có Row Level Security, kho ảnh hóa đơn nén, realtime). Sổ cái chỉ ghi thêm, ID dòng do máy khách sinh để gửi lại không bị trùng, ảnh nén còn khoảng 200 KB.
- Phát hành: PWA trước (iPhone cần thêm vào màn hình chính bằng Safari, Chrome hoặc Edge). CH Play (25 USD một lần, tài khoản cá nhân cần thử kín ít nhất 12 người trong 14 ngày), App Store sau.
- Chụp bill (chốt 14/10/2026): bill giấy chỉ để ghi nhớ ăn ở đâu, bao nhiêu; đọc tổng tiền là chính, chấp nhận sai, mặc định chia đều. Chỉ ảnh đơn đặt nhóm (Grab, ShopeeFood, đặt nước ở công ty) mới cần chính xác từng món, từng người. Đọc ảnh trên máy, miễn phí; không dùng AI trả phí, không đi xin ảnh mẫu từng ngân hàng.
- Kiếm tiền: phần lõi miễn phí; gói chuyến đi hoặc gói nhẹ trả phí; hoa hồng giới thiệu và quảng cáo để sau. Không chặn số khoản chi như Splitwise.

- Gộp app (chốt 14/10/2026): Sổ nợ và Done Nha gộp thành MỘT app tên **Done Nha**, mô hình "1 app, 2 không gian, 1 sổ cái": Sổ cá nhân (ghi hộ, riêng tư) và Nhóm/Chuyến (thủ quỹ). Màn "Sổ nợ tổng" theo người chỉ để xem; không tự bù trừ, cấn trừ chéo phải bấm tay và người kia xác nhận. Quét thẻ giữ ở Apps Script, làm sau. Màu tạm dùng vàng #FFC925 và xanh #163D89 của Sổ nợ.

Còn mở: mức góp quỹ (2 triệu/người chỉ là dự kiến, chưa chốt được), màu chủ đạo chính thức và biểu tượng, tên gói trả phí, ảnh mẫu thông báo ngân hàng (Vietcombank, ACB, MB, Techcombank, MoMo, che số dư), việc Zalo Mini App có cho cá nhân đăng ký không.

## Quyết định đang áp dụng (tóm tắt 14–18/10; nguyên văn và lịch sử: `docs/lich-su-chot-2026-10.md`)
Cách làm:
- Bảng thiết kế: artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)". Nguồn là bảng "Done Nha bấm thử" (412×915, có state); bảng tĩnh `DN-*` chụp từ đó bằng `snap.py` + `states.json` (script trong `dn-tools.zip`, không đưa lên repo). Ảnh mẫu anh đưa chỉ tham khảo, không làm giống.
- Bình luận "gửi cho Claude" trên artifact: sửa trong artifact, trả lời trong thread, đóng thread; trong phiên chỉ ghi một dòng.
- Dòng CUỐI của mọi bảng, danh sách, khối dòng KHÔNG có đường kẻ dưới (anh nhắc 2 lần). Kiểm trước khi đăng.

Sản phẩm và tính tiền:
- Mô hình số dư "lai": trong nhóm tính một nồi, gợi ý chuyển chỉ là tạm tính; thủ quỹ (nhóm không quỹ: chủ nhóm, chốt 29/10) bấm Khóa ở Cân đối mới ghi nợ từng cặp (lưu kế hoạch chuyển); phát sinh sau khóa là đợt 2. Trả tiền khoản nhóm ghi vào sổ nhóm, không vào Sổ riêng. Góp quỹ chưa xác nhận thì cảnh báo trước khi khóa.
- Cơm trưa (nhóm dài hạn, không quỹ): một nồi trong tuần, chốt thứ Bảy; "Trả buổi này"; "Chốt riêng" cho người nghỉ.
- Làm tròn khi chuyển theo bước nhóm 1.000 (mặc định) / 5.000 / 10.000đ, lẻ từ nửa bước trở lên thì lên; chênh lệch do người nhận chịu. Chia đều ghi Sổ nợ: người khác nợ số tròn, người trả chịu lẻ.
- Đổi thủ quỹ có bàn giao (quỹ ở người cũ tới khi người mới xác nhận). Thủ quỹ ủy quyền ghi chi quỹ được. Chủ nhóm hoặc thủ quỹ "Mở lại tên" cho người mất phiên khách. Cân đối gộp quỹ vào thủ quỹ (không có dòng "Quỹ → Kiệt").
- Chi tiết khoản chi: lịch sử, sửa, xóa có Hoàn tác; ai ghi mới sửa; khoản chi từ quỹ chỉ thủ quỹ hoặc người được ủy quyền. Cài đặt chuyến có "Xóa chuyến" (chỉ khi đã khóa và chuyển xong). Lưu trữ chuyến chỉ ẩn ở máy mình, cần khóa trước.
- Đăng nhập: khách + Google. ĐÃ BỎ đăng ký SĐT + OTP (18/10). Apple để sau. Bật "Allow manual linking" trên Supabase.
- iPhone tách bộ nhớ trình duyệt (Chrome hay Safari đều vậy) và app ở màn hình chính: phải "Lưu bằng Google" hoặc chép link khôi phục TRƯỚC khi thêm vào màn hình chính (màn "Giữ chỗ của bạn"). Link mời mở trong Zalo: chỉ cho xem; iPhone nút vàng "Mở bằng Chrome" + nút phụ "Mở bằng Safari", "Chép link" (đổi 28/10); Android "Mở bằng Chrome" + "Chép link". Thông báo đẩy iPhone chỉ khi đã thêm vào màn hình chính, nên nhắc nợ bằng tin nhắn là chính.
- VietQR tự tạo trên máy (nội dung không dấu ≤25 ký tự, số tiền nguyên). MoMo: người dùng tải ảnh QR nhận tiền của mình. STK chỉ hiện cho nhóm khi bật "Cho nhóm thấy"; STK cá nhân giữ trên máy.
- Pháp lý (suy luận 18/10, CHƯA hỏi luật sư): NĐ 52/2024 nhiều khả năng không áp vì app không giữ tiền. Luật BVDLCN 91/2025 + NĐ 356/2025 (từ 1/1/2026): cần màn đồng ý ("Dữ liệu của bạn"), lưu ở Singapore có thể phải lập hồ sơ chuyển dữ liệu ra nước ngoài, STK có thể là dữ liệu nhạy cảm. Hỏi luật sư trước khi mở cho người ngoài nhóm bạn.
- Mức góp quỹ CHƯA chốt; thiết kế không ghi cứng 2 triệu. Tên "Done Nha" đã tra, không trùng (tra lại gần ngày lên cửa hàng).
- Hoãn sau chuyến: Nhập từ Sổ nợ cũ, cài đặt thông báo đẩy (giữ chuông trong app). Chi tiêu thẻ đã gỡ khỏi giao diện (18/10); phần quét vẫn ở Apps Script.

Giao diện:
- Màu tiền: ĐỎ = người ta nợ bạn, XANH DƯƠNG = bạn nợ / cần góp, XANH LÁ = sạch nợ; luôn kèm chữ. Mỗi màn chỉ một nút vàng.
- Thanh menu 6 mục: Sổ nợ, Chia bill, Nhóm, Báo nợ, Thống kê, Tôi. Cả 6 icon đặc khi chọn, viền khi không. Cài đặt là bánh răng. Một chuông chung cho cả app.
- Sổ nợ tổng: thẻ Đang cho nợ (đầu, chỉ nút Mã QR) → Ghi nhanh → danh sách Theo người (Tất cả | Nợ bạn | Bạn nợ).
  - Ghi nhanh: Ghi nợ | Ghi trả, ngày, chip người có "Tất cả" đứng đầu (chọn hết), "+ Người mới", ô số tiền, ghi chú, nút vàng. Chọn nhiều người thì mỗi người cùng số tiền (không chia đều ở đây). Cài đặt Ghi nhanh: chip nhóm (vd "Cơm trưa · 5"), sửa chip số tiền. Lối tắt "+ Khoản chi" cuối thẻ, chỉ hiện khi có chuyến.
  - Kiểu D: số đã trừ qua lại chỉ để xem; người có nhiều nơi thì xổ xuống bảng từng nơi; Cấn trừ chỉ trong chi tiết người và người kia phải đồng ý. Ghi trả, báo nợ, trang xem sổ tính từng nơi.
  - Ghi trả nhanh bằng xổ xuống trên dòng người (Hết / 200k / 100k / Khác), tự biết chiều, cảnh báo trả dư. Chi tiết người không có Ảnh CK; ô số tiền ở chi tiết canh giữa, số 30px.
- Chia bill: Chia đều = tổng ÷ "Số người" (gõ 2–50, gồm cả bạn; dưới 2 báo "Ít nhất 2 người"), bấm Ghi nợ thì sang Sổ nợ điền sẵn mỗi người. Theo món cho đơn nhóm (Grab, ShopeeFood): chọn "Ai trả đơn", báo lỗi giảm giá lớn hơn tiền món.
- Báo nợ: gửi qua tin nhắn app nào cũng được (không gắn Zalo); chung 1 tin hoặc từng người; tùy chọn kèm từng ngày / TK nhận / mã QR / link xem sổ; xem trước tin. Trang xem sổ qua link: "Mình đã chuyển" → Chờ xác nhận.
- Ô số tiền hiểu "35k", "25k+12", "2tr5", "1k5", "1tr2". Tổng tiền đọc từ ảnh bill là ô sửa được, sai thì nút mờ.
- Chuyến: khoản chi trước chuyến chỉ là đặt cọc, vé xe, đồ mang theo, dụng cụ. "Ai trả" mặc định là thủ quỹ. Số dư: "Bạn sẽ nhận / Bạn cần trả", "Với từng người", khối "Tiền của bạn trong chuyến" cộng khớp Cân đối. Góp quỹ hiện 1 STK thủ quỹ.
- Thêm tên trùng: hỏi "có phải người này không"; chọn Người khác thì báo trùng để đặt tên khác.
- Thanh tiêu đề trang con ghim khi cuộn (cuộn mới có bóng). Thanh nút ghim đáy (tờ Thêm khoản chi: Chụp bill + Done nha ✓): nền đặc, viền trên 1px, bóng nhẹ. Hàng thẻ vuốt ngang có lề trái 16px.
- Thống kê: Nợ | Nhóm, chuyến (bảng "Theo nơi" hai cột Nợ bạn / Bạn nợ; Nhóm, chuyến liệt kê mọi nhóm, "Tiền chi từ đâu" có chú thích màu). Tài khoản nhận tiền nhiều TK: vé QR vuốt đổi TK, số TK luôn che.
- Đã có trên canvas: màn trống, mất mạng, gửi lỗi, sửa trùng trên 2 máy, lưu trữ chuyến, sao lưu/khôi phục (chỉ Sổ riêng), xuất CSV, Quyền riêng tư và dữ liệu (xóa tài khoản sau 7 ngày), link mời mở trong Zalo. Công tắc giả lập ở Tôi › Bản thử.
- Repo `done-nha` do anh tự tạo và cấp quyền cho Claude trên GitHub (phiên Claude không tự tạo repo được).
- Tiến độ: pha 1 thiết kế xong 25/10; pha 2 nền tảng từ 26/10; ngừng thêm tính năng 20/12; app sẵn sàng 28/12. Chỗ chạy app (Cloudflare Pages hoặc Netlify, miễn phí) chọn khi có bản đầu.

## Chốt 21/10/2026
- Lịch (anh đưa ảnh một app lịch chi tiêu có ảnh món; chỉ tham khảo, không làm giống) nằm TRONG TỪNG NHÓM/CHUYẾN, không ở Thống kê.
  - Bấm vào nhóm là thấy Lịch ngay (mặc định). Lịch GỘP với khoản chi: dưới lịch là danh sách khoản chi cả tháng; bấm một ngày thì lọc ngày đó, có nút "Cả tháng" để bỏ lọc.
  - Chuyến: "Lịch | Số dư | Quỹ" (bỏ mục Khoản chi riêng). Lịch chuyến đổi được tới tháng đi; ngày đi có viền nét đứt và nhãn "Đi".
  - Cơm trưa: "Lịch | Tuần này" (Tuần này giữ Trả ngay, Chốt riêng, Chốt tuần).
  - Link riêng tới Số dư/Quỹ (Sổ nợ, thông báo, góp quỹ) vẫn mở đúng mục đó.
- Thẻ đầu Lịch:
  - Chuyến: "Cả chuyến đã tiêu" + "Tháng này · cả nhóm" + "Phần của bạn cả chuyến". SỬA 24/10 tối: chỉ còn tổng tiền, nhãn "Cái hậu quả của nhóm" (xem mục Chốt 24/10).
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

## Chốt 24/10/2026
- Anh duyệt cấu trúc thư mục làm việc `done-nha-workspace` (trong thư mục So-no trên máy anh). Chỉ giữ thứ không nằm trong git; đánh số theo thứ tự làm: `01-brief`, `02-research`, `03-assets`, `04-design`, `05-tokens`, `06-claude-input`, `07-handoff`, `08-tools`, `99-luu-tru`, `_mau`.
  - Quyết định vẫn ghi ở file này. Việc đã làm trong tuần ghi ở `_progress.md` của thư mục đó.
  - `_mau/QUY-TRINH-UXUI.md`: quy trình 7 bước (brief → nghiên cứu → token → vẽ và bấm thử → chốt → bàn giao từng màn → code và kiểm), dùng lại cho dự án sau.
- Đánh giá báo cáo video (Design Tokens, cấu trúc PIKA): lấy token theo tầng, cấm ghi thẳng mã màu trong code (chỉ `tokens.css`), bàn giao từng màn có mẫu. Để sau: Tokens Studio, Style Dictionary, CI/CD (khi có giao diện tối hoặc người thứ 2). Báo cáo sai 3 chỗ: Done Nha đã có Design System; màu không theo thu/chi; SQL View dễ bỏ qua RLS nên dùng hàm. Chi tiết: `02-research/danh-gia-bao-cao-video.md`.
- Design System "Done Nha" thêm màu Lịch: `cal-low-bg/ink`, `cal-mid-bg/ink`, `cal-high-bg/ink`, `cal-trip-edge` (giờ 48 màu) và mục "Lịch nhóm/chuyến" trong README. Canvas còn vài màu lệch nhẹ DS: danh sách ở `05-tokens/khoang-trong-v208.md`.
- Schema `done-nha` (commit f619e79): cột ngày đi/về của chuyến + `set_trip_dates` (chủ nhóm hoặc thủ quỹ); `group_calendar` và `group_spend_totals` gộp theo giờ Việt Nam; chỉ người tải ảnh lên được xóa ảnh. 102 kiểm tra SQL qua.
- Bàn giao đầu tiên: Lịch nhóm/chuyến (`07-handoff/lich-nhom-chuyen.md`, nháp, chờ anh duyệt). Thứ tự đề xuất: Vào nhóm → Lịch → Thêm khoản chi → Góp quỹ → Cân đối → Sổ nợ → Báo nợ.
- Ảnh hóa đơn: anh chốt **bảng ảnh riêng** (`entry_photos`, commit 0df29e7), không nằm trên dòng sổ cái nữa.
  - "Thêm ảnh bill" cho khoản đã ghi được; ai trong nhóm cũng thêm ảnh, app ghi người chụp ("ai chụp").
  - Chỉ người chụp xóa ảnh, kể cả khi đã được mở lại tên.
  - Sửa khoản hoặc hoàn tác xóa thì ảnh đi theo khoản mới.
  - Ô Lịch dùng ảnh nhỏ (~15 KB), không có thì dùng ảnh lớn. 125 kiểm tra SQL qua.

- Lịch chuyến: **Xấp ảnh theo ngày** (anh chốt 24/10 trưa, đồng ý cả 6 câu). Chuyến mặc định Xấp, nút đổi "Xấp ảnh | Lịch tháng".
  - Thứ tự Trước chuyến → Ngày 1 → cuối; thẻ polaroid; tổng ngày bằng chữ thẳng + viên mức "~k/người" (ý "3 thẻ, +N, số tiền chỉ ở thẻ trên cùng" đã bị thay, xem dòng SỬA bên dưới).
  - SỬA 24/10 chiều (anh góp ý trên canvas): bỏ "+N" và bước mở dải; mỗi ngày là một hàng thẻ nghiêng vuốt ngang (giữ góc nghiêng), bấm thẻ ra thẳng chi tiết khoản; GIÁ ĐÓNG MỘC lên ảnh (kiểu "Done nha ✓" ở Tổng kết), tên khoản chữ nhạt dưới ảnh. Ngày chưa tới nét đứt "Sắp tới"; khoản không ảnh là thẻ chữ theo loại.
  - Cơm trưa chưa dùng Xấp. "Tổng kết chuyến" (ảnh story, không ghi ai nợ ai) mới là bảng phác; làm thật 14–20/12.
  - Chi tiết, nghiên cứu: `docs/de-xuat-xap-anh.md`.
- Canvas bản 211 (24/10 chiều; hệ thống tự nhảy từ 208 lên 210, rồi 211 sau góp ý):
  - Thêm DN-Chuyen-LichThang, DN-Chuyen-Xap-DangDi, DN-Chuyen-Xap-ChiTiet (bấm thẻ ra chi tiết; thay DN-Chuyen-Xap-MoNgay), DN-Chuyen-TongKet. DN-Chuyen-KhoanChi giờ mở ra Xấp ảnh.
  - Bảng tĩnh 104 bảng, 6 hàng. Công tắc Tôi › Bản thử › "Giả lập đang đi Đà Lạt" (hôm nay 4/1, 11 khoản, 6 ảnh).
  - Design System bản 19: thành phần PhotoStack (bản 20 sau sửa chiều 24/10: hàng vuốt ngang, giá đóng mộc).
- Icon (24/10 chiều, anh chốt phương án C, rồi chọn nét **Regular**): Phosphor (MIT, bản 2.1.1) làm bộ nền cho cả app. Regular là mặc định (nét 1,5px ở 24px); Bold chỉ cho dấu nhỏ cần đậm, từ 18px trở xuống (tích, cộng, đóng, mũi tên chỉ vào, trừ, mũi tên xổ); Fill cho mục đang chọn trên thanh menu (chi tiết khoét trống, thấy nền vàng). Không dùng Thin, Light, Duotone.
  - GIỮ vẽ tay: Cấn trừ, biểu tượng app, và Cân đối (đang chờ anh duyệt đổi sang cán cân Phosphor `scales`). Cấn trừ và Cân đối nhìn gần giống nhau nhưng không bao giờ nằm chung một màn (Cân đối chỉ ở DN-Dau-1; Cấn trừ ở DN-Nguoi, DN-SoNo-MinhCanTru/MinhMo/MinhTra, DN-XemSo-Minh), nên không gấp.
  - SỬA 24/10 chiều muộn (anh góp ý "icon thanh menu vuông quá" + "chia bill vẽ lại %"): Sổ nợ và Chia bill dùng icon Done Nha VẼ RIÊNG bo tròn (`dn-notebook`, `dn-receipt`), không dùng Phosphor `notebook`/`receipt`. Cùng nét 1,5px, đầu nét tròn; sổ bo 4,5 và rộng hơn, hóa đơn bo 3,75 đáy lượn sóng (bản này bị chê vẫn "vuông", đã chỉnh thân đứng ở canvas 217, xem dưới), CÓ dấu % (hai chấm tròn + gạch chéo). Bản Fill là hình đặc, chi tiết khoét bằng màu viên vàng. Bốn mục menu còn lại vẫn Phosphor. Mã nguồn: `custom_icons.py` trong `dn-tools.zip`; hình SVG ghi trong README Design System.
  - Canvas bản 212: thêm bảng so sánh `DN-Icon-Phosphor` (1280 × 2810, dưới hàng cuối, ngoài 104 bảng tĩnh). Canvas bản 213: áp dụng Regular cho bảng bấm thử và chụp lại 104 bảng (chiều cao bảng không đổi); bảng icon giữ lại làm bản so sánh. Design System bản 21: mục "Biểu tượng" viết lại (quy tắc Regular/Bold/Fill, bảng tên icon), preview PhotoStack dùng Phosphor.
  - SỬA 24/10 chiều muộn (anh góp ý trên canvas, thread nút Xấp ảnh | Lịch tháng): (1) nút đổi kiểu xem ở chuyến CHỈ CÒN ICON (20px, ô 44 × 36px, chữ ở aria-label và tooltip); (2) icon Xấp hình vẽ riêng `dn-stack`: giữ dáng icon vẽ tay cũ (thẻ trước + thẻ nghiêng phía sau), nét 1,5px bo tròn, có mặt trời và núi nhỏ, thay Phosphor `cards`; (3) **đổi chữ "ảnh" thành "hình" trong mọi chữ hiển thị** cho giống miền Nam (Xấp hình, Nhập từ hình, Từ hình, Lưu hình QR...). "ảnh hưởng" giữ nguyên. Chuỗi mới trong giao diện dùng "hình". Tài liệu kỹ thuật (tên bảng `entry_photos`, mô tả) có thể còn chữ "ảnh", không sao.
  - Canvas bản 216 (chụp lại 104 bảng; 3 bảng Tôi, Mất mạng · Tôi, Gửi lỗi cao thêm 18px vì chữ dài ra), Design System bản 23 (README: dn-stack kèm SVG, giọng văn "hình"; PhotoStack, SegmentedControl có biến thể chỉ icon).
  - Canvas bản 214 (hệ thống nhảy lên 215 sau khi bù bảng DN-VaoNhom-Zalo): chụp lại 104 bảng với hai icon mới (chiều cao không đổi), bảng `DN-Icon-Phosphor` cao 3260 có thêm mục 2b "Sổ nợ và Chia bill" và cột "ĐANG DÙNG (canvas 214)". Design System bản 22: README "Biểu tượng" (hai icon riêng + mã SVG), TabBar, và xem trước của Banner, Chip, EmptyState, Notice, Tag, Stepper đổi sang Phosphor/icon riêng.
  - Cách làm trong script: `phosify.py` đổi icon vẽ tay sang Phosphor ở bước cuối của `gen_proto.py` (đối chiếu từng svg; Bold khi nét vẽ tay >= 2; Fill cho mục đang chọn; icon không có trong bảng ánh xạ giữ nguyên). Dữ liệu icon ở `phosphor_icons.json` (52 icon gồm 2 icon riêng, tạo bằng `build_phosphor_json.py`).
  - SỬA 24/10 tối (anh góp ý "icon đang bị vuông, chỉnh lại thành hình chữ nhật đứng giống bảng trước kia"): `dn-notebook` và `dn-receipt` vẽ lại THÂN ĐỨNG, gần số đo bảng vẽ tay cũ: sổ 13 × 18,5 (cũ 14 × 18), hóa đơn 12,5 × 19 (cũ 12 × 18,5), góc bo 3,25 (bản 214–216 rộng 14,5–16, bo 3,75–4,5 nên còn phồng). Nét 1,5px, dấu % giữ. Canvas bản 217: chụp lại 104 bảng (chiều cao không đổi); bảng `DN-Icon-Phosphor` cao 3769, mục 2b có so sánh ba bản (bảng cũ, 214–216, 217). Design System bản 24 (README "Biểu tượng" + SVG mới, TabBar, EmptyState).
  - SỬA 24/10 tối (anh góp ý trên canvas, thẻ đầu Lịch chuyến): **thu gọn thẻ đầu của CHUYẾN, chỉ còn tổng tiền đã tiêu; đổi nhãn "Cả chuyến đã tiêu" thành "Cái hậu quả của nhóm"** (in hoa như nhãn nhỏ của app). Bỏ hàng hai số phụ ("Tháng này · cả nhóm", "Phần của bạn cả chuyến"); phần của bạn xem ở Số dư. Thẻ đầu nhóm dài hạn (Cơm trưa) GIỮ ba số, chờ anh nói có thu gọn giống vậy không. Canvas bản 218 (5 bảng chuyến cao thấp đi 66px, xếp lại y các hàng dưới; công cụ `relayout.py` trong `dn-tools.zip`), Design System bản 25 (README Lịch).
  - SỬA 24/10 tối (anh góp ý trên canvas, Ghi nhanh: "thêm phần cài đặt thêm lẹ của nhóm, vì có thể có nhiều nhóm, cho tùy chỉnh ẩn hiện nhóm nào"): **lối tắt chi theo từng nhóm** ở cuối thẻ Ghi nhanh (thay dòng "+ Khoản chi" chỉ có cho chuyến). Mỗi nhóm/chuyến một dòng "Chi cho <tên> / gợi ý ngắn" + nút "+ Khoản chi" (chuyến, nhóm) hoặc "+ Bữa ăn" (Cơm trưa). Cài đặt Ghi nhanh có mục "Lối tắt chi cho nhóm": mỗi nhóm một công tắc, cho biết "n/m đang hiện". Mặc định: chuyến bật, Cơm trưa tắt, nhóm mới bật; chưa giới hạn số dòng (đề xuất tối đa 3 dòng + sắp xếp, chờ anh trả lời). Canvas bản 219: thêm bảng DN-SoNo-LoiTat (bật lối tắt Cơm trưa, Ghi nhanh có 2 dòng), chụp lại DN-SoNo, DN-GhiNhanh-CaiDat, DN-GhiNhanh-ChipMoi; tổng 105 bảng tĩnh, `relayout.py` tự thêm bảng mới. Design System bản 26 (mục "Danh sách" có "Lối tắt chi cho nhóm").
  - SỬA 24/10 tối (anh góp ý trên canvas: "thêm phần lịch sử các giao dịch trước"; anh chưa nói rõ chỗ nào, em hiểu là Sổ nợ tổng thiếu chỗ xem lại giao dịch đã ghi): **mục "Lịch sử giao dịch" ở Sổ nợ tổng** + màn xem tất cả. Mục nằm dưới "Nhóm chưa chốt": 5 khoản mới nhất của mọi người và mọi nơi trong Sổ nợ (mới nhất ở trên, sắp theo ngày), đếm "n khoản", nút "Xem tất cả lịch sử". Dòng: ngày d/m, tên người, "ghi chú · nơi", số tiền theo màu tiền kèm nhãn "nợ bạn / bạn nợ / trả / cấn trừ"; bấm dòng mở chi tiết người, quay lại về đúng chỗ. Màn "Lịch sử giao dịch": ô chọn Tất cả | Khoản nợ | Khoản trả (chưa dùng chữ Ghi nợ / Ghi trả để khỏi trùng nút Ghi nhanh), nhiều khoản cùng ngày chỉ dòng đầu hiện ngày. Chỉ gồm khoản Sổ nợ; khoản chi nhóm, chuyến xem ở Lịch từng nhóm. Chưa có khoản nào thì ẩn mục. Canvas bản 220: thêm DN-SoNo-LichSu và DN-SoNo-LichSu-Tra (cạnh DN-Nguoi); 10 bảng có Sổ nợ ở nền cao thêm 459px (DN-SoNo, ChipNhom, LoiTat, TuChiaBill, MinhMo, MinhTra, MinhCanTru, DaKhoa, GhiTra2, DN-MatMang); tổng 107 bảng tĩnh. Design System bản 27 (README "Danh sách và bảng"). Anh xác nhận (24/10 tối): mục này GIỮ NGUYÊN, sau này anh sẽ chỉnh vị trí cho dễ thao tác; điều anh thật sự muốn là lịch sử các đợt trước của từng người trong trang chi tiết (xem dòng bên dưới).
  - SỬA 24/10 tối (anh nói rõ ý "lịch sử giao dịch các đợt trước của từng người khi xem trong trang chi tiết, để biết đợt trước người ta trả ngày mấy, rà soát coi có nhập thiếu dữ liệu không"): **chi tiết một người có mục "Các đợt trước"** dưới hàng nút Nhắc nợ / Ghi trả. "Đợt" = từ lúc nợ lại tới khi số dư của người đó về đúng 0 (tính theo ngày; cấn trừ không tự chốt đợt); đợt chưa hết nợ là "đợt hiện tại" và là mục "Từng khoản" (có chữ "đợt hiện tại" bên phải tiêu đề khi người đó có đợt trước). Mỗi đợt trước là một dòng bấm xổ xuống (mới nhất ở trên): "Trả hết ngày 3/10", "Từ 20/9 · sau 13 ngày", "1 khoản nợ · 2 lần trả", tổng nợ của đợt theo màu tiền; xổ ra là từng khoản theo ngày (cũ ở trên). Ghi trả hết thì đợt hiện tại tự chuyển xuống Các đợt trước. Người chưa có đợt nào thì ẩn mục. Báo nợ, trang xem sổ qua link và số "đã trả" ở dòng Sổ nợ chỉ tính đợt hiện tại. Dữ liệu mẫu thêm 10 dòng của các đợt cũ (Lan 1 đợt, Minh 2 đợt, Tuấn 1 đợt; số dư không đổi). Chưa làm: cờ nhắc "có thể thiếu dòng" (vd trả dư hơn nợ) vì anh mới nói mục đích là tự rà bằng mắt. Canvas bản 221: thêm DN-Nguoi-DotTruoc (mở một đợt trước, Minh); DN-Nguoi cao thêm 264px; DN-SoNo-LichSu giờ 19 khoản; tổng 108 bảng. Design System bản 28 (README "Danh sách và bảng").
  - Phosphor `lock-simple` trông như túi xách ở 24px, dùng `lock`. Nút "Đổi số tiền" trên màn Mã QR dùng `qr-code` (mất dấu cộng của bản vẽ tay).
- Làm gọn file này (24/10): các mục 14–18/10 chuyển nguyên văn sang `docs/lich-su-chot-2026-10.md`, thay bằng "Quyết định đang áp dụng" (đã bỏ các ý bị thay). Thêm `docs/ban-giao-phien.md` để đổi model không mất ngữ cảnh, `docs/ke-hoach-tuan.md` cho việc theo tuần.

## Chốt 26/10/2026
- Supabase: anh đã dán `schema.sql` (commit 0df29e7) và Run thành công; đủ 8 bảng + bucket `receipts`. Gói Free gửi thư cảnh báo tự tạm dừng sau 7 ngày ít hoạt động: tạm dừng không mất dữ liệu, bật lại trong dashboard (thư ghi 90 ngày, trang hướng dẫn ghi 1 năm; tính 90 ngày cho chắc). Trước 28/12 chọn cách giữ hoạt động hoặc lên Pro trong tháng đi chuyến.
- Anh ok theo đề xuất (26/10 sáng):
  - Cờ tự động "có thể thiếu dòng" ở Các đợt trước: **để sau chuyến**; giờ anh tự rà bằng mắt.
  - Lối tắt chi cho nhóm ở Ghi nhanh: **tối đa 3 dòng**, nhóm nào ghi khoản gần nhất đứng trên (ghi bằng lối tắt hay ở trong nhóm đều tính); nhóm bật mà ngoài 3 dòng thì ẩn, Cài đặt Ghi nhanh có ghi chú.
  - Thẻ đầu Lịch Cơm trưa **giữ 3 số** (không thu gọn như chuyến).
  - Cân đối dùng **cán cân Phosphor `scales`** (Regular); Cấn trừ vẫn vẽ tay.
- Canvas bản 222 (26/10), Design System bản 29:
  - Lối tắt Ghi nhanh: tối đa 3 dòng, sắp theo lần ghi khoản gần nhất; Cài đặt Ghi nhanh đếm "n/m đang bật", bật hơn 3 nhóm thì có thanh nhắc nhóm nào đang hiện. Thêm bảng DN-GhiNhanh-LoiTat-ToiDa.
  - Nhóm mới tạo và nhóm vừa vào bằng link giờ cũng mở ra **Lịch** (như Cơm trưa), bỏ danh sách "Khoản đã ghi" cũ. Chưa có khoản nào thì thẻ tiền đổi thành thẻ "Nhóm mới, chưa có khoản nào" chỉ xuống nút ghim đáy, ẩn danh sách. Thêm bảng DN-Nhom-MoiLich.
  - Hình đang tải: ô Lịch giữ nền màu mức + dấu hình mờ, dưới chú thích có dòng "Hình đang tải…". Công tắc Tôi › Bản thử › "Giả lập hình đang tải". Thêm bảng DN-Com-Lich-HinhTai.
  - Icon Cân đối (DN-Dau-1) là cán cân `scales`. Sửa 4 màu lệch DS: nền báo lỗi/hỏi xóa `#fdecea` → `danger-tint`; vòng tích "Bạn là …" → `success-tint` + `success`; thanh ghim tờ Thêm khoản chi → `cream`, viền trên `line`, bóng như nút ghim đáy; khung xem trước tin nhắn ở Báo nợ → `fill-faint`.
  - Tôi, Mất mạng · Tôi, Gửi lỗi cao thêm 61px (thêm một công tắc bản thử); Cài đặt Ghi nhanh cao thêm 36px (ghi chú dài hơn). Tổng 111 bảng tĩnh; bảng `DN-Icon-Phosphor` để nguyên làm bản so sánh cũ.
- Bàn giao **Vào nhóm** (`07-handoff/vao-nhom.md`, nháp 26/10): ghi 8 chỗ lệch giữa bảng vẽ và máy chủ (xem trước nhóm đang đòi đăng nhập, dòng tiền dưới tên làm lộ số, link khôi phục không mở được app ở màn hình chính, người tạo nhóm cũng cần Giữ chỗ, "hết hạn 7 ngày" chưa có, Google đã gắn tài khoản khác, nút "Mở bằng Safari" chưa chắc làm được, mã mời dài). 4 câu chờ anh chọn ở mục 10.
- Ba token mới (`toast-bg`, `pink-*`, `bubble-*`) và màu avatar vẫn chờ anh duyệt tên.
- **Vào nhóm, anh chốt 26/10 (đồng ý cả 4 đề xuất trong bàn giao):**
  1. Mở link mời: hiện **thẻ mời trước, chưa cần đăng nhập** (hàm mới `invite_card`: tên nhóm, người tạo, ngày, số người, có quỹ; không có tên, không có tiền). Bấm "Chọn tên của bạn" = đồng ý dữ liệu → tạo khách → chọn tên. Trong Zalo chỉ thấy thẻ mời, không tạo khách.
  2. Tên không có trong danh sách: **người đó tự thêm tên** (không chờ người mời), hỏi trùng tên như Sổ nợ ("Nhóm đã có X. Có phải bạn không?").
  3. Link mời **không hết hạn**; chủ nhóm có nút **"Đổi link mời"** ở màn Mời (hàm `rotate_join_code`): link cũ hết dùng, người đã vào vẫn ở lại.
  4. **Bỏ link khôi phục**: lưu bằng Google là chính; mất tên thì chủ nhóm hoặc thủ quỹ "Mở lại tên". Bỏ nút "Chép link khôi phục" ở Giữ chỗ và Lưu tài khoản.
  - Code: `done-nha` commit 821fc77 (2 hàm + 17 kiểm tra; 142 kiểm tra SQL qua). Anh đã dán lại `schema.sql` vào Supabase (26/10 trưa).
  - Canvas bản 223 (114 bảng): thêm DN-VaoNhom-Ten (chọn tên), DN-VaoNhom-TenMoi (tự thêm tên, hỏi trùng), DN-Moi-DoiLink; DN-VaoNhom-Link giờ là bước thẻ mời; bỏ "Chép link khôi phục" ở Giữ chỗ và Lưu tài khoản; chữ Zalo và lời nhắc khách ở Tôi sửa theo. Chiều cao bảng không đổi.
  - Anh ok thêm 3 chỗ (26/10 trưa): **bỏ dòng tiền dưới tên** khi chọn tên (ai có link cũng thấy); **người tạo nhóm còn là khách cũng qua Giữ chỗ** trước màn Mời (ghi chú: bạn là chủ nhóm, nhóm không quỹ thì mất tên không ai mở lại được; nút "Xong, mời mọi người"); thẻ mời có nút chữ **"Đã dùng Done Nha? Đăng nhập Google"** (chỉ khi máy chưa đăng nhập Google; vào xong thẳng Lịch, khỏi Giữ chỗ). Canvas bản 224: thêm DN-TaoNhom-Luu, tổng 115 bảng; DN-Nhom-MoiLich và DN-GhiNhanh-LoiTat-ToiDa thêm bước "Để sau". Bàn giao Vào nhóm đã chốt hết câu hỏi.

## Chốt 27/10/2026
- Cách viết giao diện app (pha 2): **Vite + Preact** (anh chốt 27/10). Mỗi thành phần Design System là một khối code dùng lại; `core/ledger.js` vẫn là JS thuần, không phụ thuộc Preact. Cần bước build (Vite), Claude lo. Hosting (Cloudflare Pages hoặc Netlify) chưa chọn, chạy thử trên máy trước.
- Thứ tự việc anh làm với Supabase và Google (Claude dẫn từng bước): (1) bật Anonymous sign-ins + Allow manual linking, (2) gửi Project URL + publishable key (chỉ đặt vào file cấu hình app), (3) tạo khóa OAuth Google dán thẳng vào Supabase (không gửi Claude), (4) duyệt 3 token mới + màu avatar.
- Tiến độ 27/10 chiều: đã bật Anonymous sign-ins + Allow manual linking; đã gửi Project URL + publishable key (chưa ghi vào đâu, sẽ đặt vào file cấu hình app); đã tạo dự án Google Cloud "Done Nha" + OAuth client, dán vào Supabase (đã bật Google; secret cũ lộ trong ảnh chụp nên đã thay secret mới). Shell của Claude KHÔNG gọi được supabase.co (proxy chặn) nên kiểm kết nối thật phải làm trên máy anh.
- Màn hình đồng ý Google đang **Testing** (chỉ "test users" đăng nhập được, tối đa 100): nút Publish bị khóa tới khi điền trang Branding (trang chủ app, link chính sách quyền riêng tư, tên miền). Làm khi có chỗ chạy app: Claude làm trang chủ + trang Chính sách quyền riêng tư (cần cho Luật BVDLCN dù sao), anh điền Branding rồi Publish. Hạn: trước thử kín 7–13/12. Trong lúc phát triển: thêm email anh và vài người thử vào Test users.
- Anh duyệt (27/10, "ok hết"): 3 token mới `toast-bg`, `pink-wash` + `pink-ink`, `bubble-bg` + `bubble-edge` + `bubble-ink` (vào Design System bản 31, giờ 54 màu). **Avatar:** một màu đặc + chữ cái đầu tên (không gradient); chỉ dùng 6 màu `avatar-*` của DS, không thêm cam `#ef9a2f` và tím `#7b5cc4`; gán màu theo thứ tự vào nhóm (Sổ riêng: thứ tự thêm người) lần lượt `blue → orange → green → pink → sky → gold` rồi quay lại, gán một lần không đổi. Chữ cái dùng `ink`, riêng `avatar-blue` dùng chữ trắng (đã đo: chữ trắng trên 5 màu còn lại chỉ 2.3–3.2:1; lúc đề xuất em nói "chữ trắng luôn đọc rõ" là SAI, đã sửa). Canvas vẫn vẽ avatar gradient cũ: sửa ở lần chụp lại canvas kế tiếp.
- **Khung app (27/10 chiều, Opus):** repo `done-nha`, thư mục `app/` (commit 1d20de6): Vite 7.3.7 + Preact 10.29.8 + supabase-js 2.117.3 (Preact 11 / Vite 8 mới ra, chưa dùng). PWA: manifest + service worker (không lưu đệm dữ liệu Supabase), icon TẠM chữ "DN" nền vàng (biểu tượng app chưa chốt). `tokens.css` sinh từ Design System (`npm run tokens`); `npm run check` chặn mã màu ngoài tokens.css; luật giao diện `done-nha/.claude/rules/ui.md`. Màn **thẻ mời** `/j/<mã>` gọi `invite_card` (chưa tạo khách) + bản trong Zalo; chụp 412px khớp vị trí từng khối với `DN-VaoNhom-Link`. Chưa thử với Supabase thật. Ghi chú code (icon theo loại nhóm, dòng phụ, trạng thái thêm, cách mở Safari từ Zalo): mục 12 của `07-handoff/vao-nhom.md`. Design System bản 32: sửa ghi chú `pink-wash` (ô icon trên thẻ mời, không phải "nhóm có quỹ").
- Chỗ chạy app: em đề xuất **Cloudflare** (miễn phí, băng thông không giới hạn, 500 lần build/tháng, tự cập nhật khi đẩy code; R2 cho hình sau này cùng tài khoản). Netlify gói Free mới tính bằng credit: khoảng 20 lần đưa bản mới/tháng, hết credit thì trang bị tạm dừng tới tháng sau. **Anh chọn Cloudflare (27/10)**: Pages nối repo `done-nha`, thư mục gốc `app`, build `npm run build`, xuất `dist`.
- **App đã chạy trên Cloudflare Pages (27/10 chiều):** địa chỉ `https://done-nha.pages.dev` (tự build khi đẩy lên `main` của `done-nha`). Supabase Auth › URL Configuration đã đặt Site URL + Redirect URLs (`https://done-nha.pages.dev/**`, `http://localhost:5173/**`). Đăng nhập Google đi qua Supabase nên CHƯA cần thêm Authorized JavaScript origins ở Google (ghi chú cũ sửa lại). Đã thử trên Android với Supabase thật (nhóm thử `Đà Lạt (thử)` tạo bằng SQL, xóa sau khi thử): thẻ mời đọc đúng từ `invite_card` trên Chrome và trong Zalo; nút "Mở bằng Chrome" trong Zalo chạy (Zalo hỏi thoát rồi mở Chrome), Chép link và ⋯ › Mở bằng trình duyệt cũng được. iPhone (`x-safari-https`) ĐÃ thử 28/10: chạy (Zalo hỏi thoát rồi mở Safari, Chép link cũng được). Tệp `_redirects` đã bỏ (Pages tự trả `index.html`). Trang chủ + Chính sách quyền riêng tư cho Google Publish: dùng tên miền này.

## Chốt 28/10/2026
- Thẻ mời trong Zalo → Safari đã thử trên iPhone thật: chạy (Zalo hỏi thoát rồi mở Safari; Chép link cũng được). Bỏ dòng báo "chưa mở được" theo giờ ở cả hai hệ điều hành (hộp hỏi của Zalo làm nó báo sai).
- **Chọn tên đã code (28/10, Opus)**, repo `done-nha` commit 4656f95, chạy ở `done-nha.pages.dev`:
  - Bấm "Chọn tên của bạn" = đồng ý dữ liệu (tạm ghi ngày giờ trên máy, khóa `dn.consent`) → tạo khách CHỈ khi máy chưa có phiên → danh sách tên (`preview_group`) → "Vào nhóm là <tên>" (`join_group`).
  - Lệch bảng vẽ có chủ ý: **chưa chọn sẵn tên nào** (DN-VaoNhom-Ten chọn sẵn tên đầu; dễ bấm nhầm vào tên người khác). Nút vàng mờ "Chọn tên của bạn ở trên" tới khi chọn. Dòng tên cao 44px (bảng 42px) cho đủ vùng bấm.
  - Tên đã có người nhận: mờ, bấm thì nhắc nhờ chủ nhóm hoặc thủ quỹ "Mở lại tên". Tự thêm tên: so trùng bỏ dấu, không phân biệt hoa thường ("lân" trùng "Lan"), hỏi "Đúng, là tui / Người khác" như Sổ nợ.
  - Mở lại link khi đã ở trong nhóm: "Bạn đã ở trong <nhóm> rồi, tên <X>." + "Mở nhóm".
  - Sau khi vào: màn nhóm TẠM `/g/<id>` (thẻ "Bạn là …", nhắc iPhone, danh sách thành viên đã vào/chưa vào); màn đầu có "Nhóm của bạn". Giữ chỗ + Lưu bằng Google và Lịch là bước kế tiếp.
  - Toast giờ chạm xuyên qua (trước đó che nút vàng ở đáy) và rộng đủ đọc câu dài.
- Anh thử chọn tên với Supabase thật (28/10 chiều, Chrome + Samsung Internet trên S24 Ultra): đạt hết (nhận Khang, mở lại link báo "đã ở trong nhóm", Khang mờ ở máy thứ hai, hỏi trùng "Lan", "Kiet" trùng "Kiệt", thêm "Khang Samsung", danh sách 4 người đúng ở cả hai bên).
- Anh chốt (28/10): **gợi ý tên khỏi trùng bằng SỐ**: "Trùng tên Lan trong nhóm. Thêm số cho dễ phân biệt, ví dụ Lan 2" (có "Lan 2" rồi thì gợi "Lan 3"); bỏ kiểu "Lan Anh", "Kiệt Anh". Canvas DN-VaoNhom-TenMoi vẫn ghi kiểu cũ, sửa ở lần chụp lại sau.
- Samsung Internet tự đổi trang sang nền tối (vòng tròn chọn tên gần như mất, nút vàng thành nâu) và theo diễn đàn Samsung thì trang web không tắt được. App đã khai `color-scheme: only light` (Chrome nghe). Nhóm Đà Lạt dùng Safari/Chrome nên không chặn. Ghi nhớ cho VietQR sau này: vẽ mã QR thành hình (`<img>`/canvas), đừng vẽ bằng SVG màu trong trang, kẻo bị đảo màu.

- **Giữ chỗ + Lưu bằng Google đã code (28/10 chiều, Opus)**, `done-nha` commit 68f20ac:
  - Vào nhóm bằng khách xong → màn Giữ chỗ (`/g/<id>/luu`, như DN-VaoNhom-Luu). "Lưu bằng Google" gắn Google vào chính tài khoản khách (giữ nguyên tên, nhóm); Google trả về đúng màn đó → "Giờ thêm vào màn hình chính" 3 bước + "Xong, vào nhóm" (DN-VaoNhom-Luu-Xong). Android ghi bước 2 là "⋮ › Thêm vào màn hình chính (hoặc Cài đặt ứng dụng)".
  - Lỗi: Google này đã gắn Done Nha ở máy khác → nhắc chọn tài khoản Google khác hoặc Để sau; hủy ở Google / chưa phải test user → nhắc bấm lại hoặc Để sau. Google chặn người ngoài Test users ngay trên trang Google (app không thấy được), nên trước thử kín phải Publish.
  - "Đã dùng Done Nha? Đăng nhập Google" có ở thẻ mời VÀ màn đầu (để app ở màn hình chính iPhone vào lại đúng tên), CHỈ hiện khi máy chưa có phiên nào (chặt hơn bàn giao "chưa đăng nhập Google": đang là khách mà đăng nhập Google thì bỏ rơi tên khách; khách thì lưu ở Giữ chỗ). Máy đã có Google thì vào nhóm xong thẳng vào nhóm, khỏi Giữ chỗ.

- Anh thử Google trên Supabase thật (28/10 chiều): **đạt cả 3**. (A) Chrome: Khang lưu bằng Google, nhóm ghi "Đã lưu bằng Google"; Supabase chỉ có 1 tài khoản Google (khách Khang được gắn Google, không sinh tài khoản mới). (B) Tab ẩn danh: Đăng nhập Google → "Nhóm của bạn" có Đà Lạt (thử) (sau khi sửa lỗi nhúng `groups(...)`, commit 8e54938). (C) Samsung Internet: "Khang Samsung" lưu bằng cùng Google → báo đúng "đã gắn với Done Nha ở máy khác", tên khách vẫn còn. Chrome Android chặn chụp màn hình trong tab ẩn danh (bật được ở `chrome://flags` › Incognito Screenshot).

- Anh báo (28/10): **các bạn iPhone dùng Chrome là chủ yếu.** Đã sửa (`done-nha` sau commit 8e54938): trong Zalo trên iPhone, nút vàng là "Mở bằng Chrome" (`googlechromes://`), "Mở bằng Safari" và "Chép link" là hai nút phụ; mọi chữ nhắc iPhone nói "Chrome hay Safari"; bước thêm vào màn hình chính trên Chrome iPhone ghi "nút Chia sẻ (cạnh thanh địa chỉ)". Chrome iPhone thêm được vào màn hình chính từ iOS 16.4, và app ở màn hình chính vẫn tách bộ nhớ với Chrome như với Safari. CHƯA thử: `googlechromes://` từ Zalo trên iPhone thật (chưa cài Chrome thì nút không mở được gì, còn Safari, Chép link, ⋯).

- Anh chốt (28/10) **cách 1** cho người kẹt "Google này đã gắn Done Nha ở máy khác": nhờ chủ nhóm hoặc thủ quỹ "Mở lại tên", rồi bấm "Đăng nhập bằng Google đó" (rời phiên khách trên máy này) và mở lại link mời chọn tên. Câu báo lỗi nói đúng tên người mở lại được (chủ nhóm, thủ quỹ, trừ chính mình); không ai mở được (chủ nhóm kiêm thủ quỹ, hay nhóm không quỹ mà mình là chủ) thì chỉ gợi chọn Google khác.
- **Tạo nhóm + Mời + Mở lại tên đã code (28/10 chiều, Opus)**, `done-nha` commit 4d54d3a:
  - Màn đầu: nút vàng "Tạo nhóm hoặc chuyến", nút phụ "Có link mời? Vào nhóm bằng link".
  - Tạo nhóm (DN-TaoNhom): loại, tên, ngày đi/về (lịch của máy), Có quỹ chung + **chọn thủ quỹ ngay lúc tạo** (chip tên; Khang tạo Đà Lạt chọn Kiệt được, khỏi bàn giao), thêm tên hỏi trùng gợi ý "Lan 2". Lệch bảng vẽ: chưa có "Chọn từ danh bạ Sổ nợ" (Sổ nợ chưa làm) và ô "Góp dự kiến" (mức góp chưa chốt); có thêm ô "Tên của bạn trong nhóm" (điền sẵn tên gần nhất); Ăn uống, Ở chung, Khác đều lưu là nhóm dài hạn (icon riêng từng loại để sau).
  - Người tạo còn là khách → Giữ chỗ (DN-TaoNhom-Luu) → Mời; có Google rồi thì thẳng Mời.
  - Mời (DN-Moi): mã QR là hình, link hiện gọn ở giữa (mã thật dài 32 ký tự; bảng vẽ ghi mã ngắn), Sao chép, "Gửi vào nhóm chat" (bảng chia sẻ của máy), "Ai đã vào". Đổi link mời (DN-Moi-DoiLink) chỉ chủ nhóm, có hỏi lại.
  - Mở lại tên (DN-CaiDat-MoLai) TẠM nằm ở màn nhóm (chủ nhóm, thủ quỹ; có hỏi lại); dời vào Cài đặt nhóm khi có màn đó.
  - Máy chủ: `create_group` nhận thêm tên thủ quỹ; tên thêm cùng lúc giữ đúng thứ tự (màu avatar). 147 kiểm tra SQL qua.
  - Anh đã dán lại `schema.sql` (commit 4d54d3a) vào Supabase và thử trên Android với Supabase thật (28/10 chiều): **đạt cả 5 bước** (tạo chuyến "Thử tạo" chọn Kiệt làm thủ quỹ, vào thẳng Mời vì đã có Google; mời máy thứ hai bằng link; Đổi link làm link cũ hết dùng, người đã vào vẫn ở lại; Mở lại tên rồi chọn lại được). Thứ tự tên và màu avatar đúng.

- Anh chốt (28/10 chiều): đợt code kế làm **Lịch + Thêm khoản chi cùng lúc** (để thử trọn vòng), và **làm Xấp hình luôn** cho chuyến dù chưa có tải hình (khoản chưa có hình là thẻ chữ theo loại).
- **Lịch + Xấp hình + khoản chi đã code (28/10 chiều, Opus)**, `done-nha` commit 9497018 (không đổi schema, khỏi dán lại):
  - Bấm vào nhóm mở Lịch. Chuyến mặc định Xấp hình (Trước chuyến → Ngày 1…, thẻ nghiêng vuốt ngang, giá đóng mộc, ngày chưa tới nét đứt "Sắp tới"), nút đổi Xấp hình | Lịch tháng chỉ icon. Nhóm dài hạn: Lịch tháng + thẻ đầu 3 số. Nhóm mới: thẻ "Nhóm mới, chưa có khoản nào".
  - Thêm khoản chi: số tiền (35k, 2tr5, 25k+12…), tên, ngày, ai trả, loại, chia đều; chi tiết khoản có Sửa, Xóa (hỏi trước) và Hoàn tác ở Lịch.
  - Lệch bảng vẽ: (1) **Ai trả mặc định là người đang ghi**, không phải thủ quỹ; người không phải thủ quỹ chỉ chọn được chính mình (người được ủy quyền thêm Quỹ chung), vì máy chủ chỉ cho ghi khoản mình trả. (2) Thêm ô **Ngày** để ghi bù khoản hôm trước (mặc định ngày đang chọn ở Lịch, không thì hôm nay). (3) Chưa có mục Số dư / Quỹ / Tuần này; bánh răng mở Cài đặt nhóm tạm (Giữ chỗ, Mời, thành viên, Mở lại tên). (4) Lịch tháng ghi "n khoản trong tháng" thay "n hình". (5) Nhóm dài hạn chưa biết là Cơm trưa nên nút luôn là "Ghi khoản chi". (6) Chưa có: Chụp bill và hình, Lịch sử thay đổi, Gửi đề nghị sửa, ghi khi mất mạng (giờ cần mạng; bấm lại không ghi đôi), Tổng kết chuyến (thẻ chỉ báo "có sau khi về").
  - Anh chốt (29/10): nhóm không quỹ (Cơm trưa) **giữ luật ai trả người đó tự ghi**, không cho ghi hộ khoản người khác trả. Không sửa `add_entry`.
- Anh thử Lịch + khoản chi với Supabase thật (29/10 sáng, iPhone Chrome + Android): **chạy đúng hết**, chỉ lỗi giao diện ô chọn ngày: iPhone ô ngày giãn rộng hơn khung làm cả màn kéo ngang; Android mũi tên chọn ngày dính sát viền ô. Anh dặn: **mọi mũi tên xổ xuống phải đồng bộ, không dính đường viền ô**. Đã sửa (`done-nha` commit 8cd84cb): ô ngày dùng chung `DateInput`, tắt kiểu gốc của trình duyệt, mũi tên giống ô "Ai trả" (caret-down Bold 16px, cách viền phải 14px); chặn kéo ngang cả màn. Ghi vào luật giao diện `done-nha/.claude/rules/ui.md`. Chờ anh xem lại trên iPhone.

## Chốt 29/10/2026
- **Góp quỹ + Số dư + Cân đối đã code (29/10, Opus)**, `done-nha` commit d1d5646, KHÔNG đổi schema (khỏi dán lại):
  - Màn nhóm có mục **Lịch | Số dư | Quỹ** (Quỹ chỉ nhóm có quỹ). Nút ghim "Ghi khoản chi" chỉ ở Lịch.
  - Số dư (DN-Chuyen-SoDu): thẻ "Nếu cân đối bây giờ · tạm tính" / "Sau khi khóa cân đối", Dòng chuyển của bạn, Tiền của bạn trong chuyến (cộng khớp Cân đối; thủ quỹ có thêm dòng "Quỹ đang ở bạn"), thẻ Quỹ chung, nút vàng Cân đối cuối chuyến.
  - Quỹ (DN-Chuyen-Quy, DN-Quy-ThuQuy): ai đã góp; thủ quỹ "Đã nhận ✓" hoặc "Chưa thấy" (= gỡ báo góp, người đó báo lại), "Ghi góp" hộ người đưa tiền mặt mà chưa vào app, "+ Ghi chi từ quỹ", "Ủy quyền" (công tắc ở Cài đặt nhóm).
  - Góp quỹ (DN-GopQuy): Chuyển khoản | Tiền mặt → "Mình đã chuyển" / "Mình đã đưa Kiệt" → chờ thủ quỹ xác nhận. Ô số tiền điền sẵn số mọi người đang góp nhiều nhất (không ghi cứng 2 triệu).
  - Cân đối (DN-CanDoi, DN-CanDoi-Khoa): tạm tính + cảnh báo góp chưa xác nhận; thủ quỹ "Khóa cân đối" (hỏi lại); đã khóa thì người chuyển "Done nha", người nhận "Đã nhận", thủ quỹ "Ghi đã chuyển" hộ, có Hoàn tác; "Gửi bảng cân đối vào nhóm". Khoản thuộc đợt đã khóa không sửa, xóa được nữa.
  - Góp chưa được thủ quỹ xác nhận KHÔNG tính ở cả Số dư và Cân đối (giống lúc khóa trên máy chủ), để hai màn khớp nhau.
  - Lệch bảng vẽ: chưa có VietQR (làm cùng Tài khoản nhận tiền, đợt sau); chưa có "Mở khóa" (máy chủ chưa có hàm); bỏ "dự kiến 2.000.000đ", "mục tiêu 18.000.000đ", "Bạn cần góp 2.000.000đ" (mức góp chưa chốt); chưa có bàn giao thủ quỹ; nhóm không quỹ chưa khóa được (máy chủ chỉ cho thủ quỹ khóa, nhóm không quỹ không có thủ quỹ).
- Anh chốt (29/10): **nhóm không quỹ (Cơm trưa, chuyến không quỹ) thì CHỦ NHÓM khóa cân đối / chốt tuần**; nhóm có quỹ vẫn chỉ thủ quỹ khóa. Code: `done-nha` commit be75d74 (`lock_group` đổi, 4 kiểm tra SQL mới, 151 qua; app ghi "Thảo (chủ nhóm) khóa cân đối"). **Anh cần dán lại `schema.sql` vào Supabase.**

- **Rà soát chữ toàn app (29/10, anh duyệt "sửa hết")**, `done-nha` commit sau be75d74, dựa trên nghiên cứu (Splitwise, Tricount, Settle Up, MoMo Quỹ nhóm; NN/g, GOV.UK):
  - Trên màn chỉ để nhãn, số, trạng thái, nút. Bỏ câu nói khối làm gì, câu lặp tên nút, hướng dẫn tĩnh dưới ô nhập.
  - Cách tính, làm tròn, khóa, "app không giữ tiền" gom vào tờ **"Tính sao ra vậy?"** (Số dư, Cân đối).
  - Giữ chữ (ngắn) cho: thao tác không hoàn tác (khóa, xóa, mở lại tên, đổi link), app không chuyển tiền giùm (Góp quỹ, Cân đối đã khóa), đồng ý dữ liệu, cảnh báo iPhone mất tên (giờ chỉ hiện ngoài Android), báo lỗi.
  - Chữ phụ tối đa 1 câu ~12 chữ, nút 1–4 chữ. Ví dụ: "Nếu cân đối bây giờ · tạm tính" → "Tạm tính"; "Phần của bạn trong các khoản ai đó ứng" → "Phần của bạn"; nút "Tạo chuyến · mời bằng link" → "Tạo chuyến".
  - 20 màn giả lập: 2.613 → 1.665 chữ (−36%). Luật viết ở `done-nha/.claude/rules/ui.md`. Canvas chưa sửa theo (chữ trên bảng vẽ vẫn bản cũ).

## Chốt 30/10/2026
- **Xấp hình kiểu cổ điển, đơn giản, hơi châu Âu** (anh góp ý 30/10), `done-nha` commit 94bbd08:
  - Tên khoản dưới hình là **chữ viết tay** (font Charm, có đủ dấu tiếng Việt, tự chứa trong app). Dưới tên là ngày giờ ghi khoản gọn "3/1 · 12:35"; khoản ghi bù ngày khác (không có giờ thật) chỉ hiện ngày.
  - Giá là **mảnh giấy cắt** (hai đầu răng cưa, giấy kem, chữ Newsreader) dán đè góc dưới hình, lố ra mép một chút; thay mộc viền xanh.
  - Thẻ to hơn khoảng 10% (148 → 163px, hình 134 → 147px), góc gần vuông như hình in. Tiêu đề ngày và tổng ngày dùng chữ Newsreader.
  - Bỏ dòng "n khoản · loại · phần bạn" dưới mỗi hàng.
  - Chưa cập nhật: Design System (token chữ `hand`, thành phần PhotoStack) và canvas; làm khi anh ưng kiểu này.

## Lỗi đã gặp, đừng lặp lại
- Prompt dùng lại được mà chỉ nằm trong hội thoại thì mất khi hội thoại bị tóm tắt (prompt Figma Make 21/10). Lưu vào `06-claude-input/` của thư mục làm việc.
- Trả tiền theo kế hoạch đã khóa phải TRỪ khỏi kế hoạch, không cộng thành lượt chuyển mới (lỗi bắt được khi viết test 18/10).
- Đừng nói chỉ Safari mới thêm được vào màn hình chính trên iPhone; Chrome và Edge cũng được.
- Giá gói của MoVi Group trên App Store Việt Nam là đồng (119.000 / 409.000 / 549.000), không phải USD.
- Sửa nguyên bảng trong tài liệu dễ mất định dạng; sửa từng ô hoặc từng dòng.
- Đặt mốc "app sẵn sàng" theo ngày đi trừ thời gian thử, không phải theo ngày đi.
- Supabase gói Free đã kiểm 17/10/2026 trên trang giá chính thức: 500 MB số liệu, 1 GB ảnh, 5 GB tải xuống, 50.000 người dùng/tháng, tối đa 2 dự án, tự ngủ sau 1 tuần không dùng. Đăng nhập Apple cần tài khoản Apple Developer (chưa kiểm giá); chuyến Đà Lạt dùng khách và Google trước. Pháp lý đã nghiên cứu 18/10 (xem mục Chốt 18/10) nhưng chỉ là suy luận từ văn bản, chưa có ý kiến luật sư.
- Địa chỉ dự án Supabase và khóa publishable chỉ nằm trong file cấu hình của app, không ghi vào tài liệu hay trí nhớ; khóa secret và service_role, mật khẩu cơ sở dữ liệu thì tuyệt đối không đưa cho Claude hay ghi ở đâu.
- Bản giả lập (`?mock=1`) chạy đúng không có nghĩa Supabase thật chạy đúng: 28/10 "Nhóm của bạn" không hiện vì câu đọc nhúng `groups(...)` bị PostgREST từ chối (3 khóa ngoại giữa groups và members), app lại nuốt lỗi im lặng. Phần gọi máy chủ phải nhờ anh thử trên điện thoại sau mỗi lần sửa; lỗi tải luôn hiện ra, không giấu.
- Đo tương phản bằng số trước khi nói một cặp màu đọc rõ (27/10 em nói chữ trắng đọc rõ trên màu avatar, thực tế chỉ `avatar-blue` đạt).
- App một trang không tự tải bản mới khi chỉ đổi màn: 29/10 anh không thấy nút Khóa vì điện thoại còn chạy bản trước. Đã thêm tự nhận bản mới (`done-nha/app/src/lib/update.js`). Mỗi lần nhờ anh thử bản mới, nhắc tải lại trang trước.
- Ghi tệp về máy anh (bàn giao, `_progress.md`): mỗi lần ghi dùng một thư mục tạm MỚI trong outputs và kiểm kích thước tệp trên máy sau khi ghi. 28/10 dùng lại đường dẫn cũ nên máy nhận bản cũ; tệp đọc từ máy cũng có lúc là bản cũ, đọc lại nếu thấy lạ.
