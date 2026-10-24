# CLAUDE.md – Sổ nợ và Done Nha

Chủ dự án: Nguyên Khang (UI/UX designer). Giao tiếp bằng tiếng Việt, ngắn gọn, hành động trước; việc nhiều lựa chọn thì dùng bảng so sánh có đánh đổi. Việc nặng cỡ Opus thì báo cho anh biết.

## Index nhanh (đọc mục này trước)
| Cần gì | Xem ở đâu |
|---|---|
| **Mở phiên mới / đổi model** | `docs/ban-giao-phien.md` (đọc đầu tiên: đọc gì, đang dở gì, chọn model) |
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
| Artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)" | Toàn bộ bảng thiết kế (bản 211, 104 bảng) | Bền, có các bản cũ |
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

## Quyết định đang áp dụng (tóm tắt 14–18/10; nguyên văn và lịch sử: `docs/lich-su-chot-2026-10.md`)
Cách làm:
- Bảng thiết kế: artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)". Nguồn là bảng "Done Nha bấm thử" (412×915, có state); bảng tĩnh `DN-*` chụp từ đó bằng `snap.py` + `states.json` (script trong `dn-tools.zip`, không đưa lên repo). Ảnh mẫu anh đưa chỉ tham khảo, không làm giống.
- Bình luận "gửi cho Claude" trên artifact: sửa trong artifact, trả lời trong thread, đóng thread; trong phiên chỉ ghi một dòng.
- Dòng CUỐI của mọi bảng, danh sách, khối dòng KHÔNG có đường kẻ dưới (anh nhắc 2 lần). Kiểm trước khi đăng.

Sản phẩm và tính tiền:
- Mô hình số dư "lai": trong nhóm tính một nồi, gợi ý chuyển chỉ là tạm tính; thủ quỹ bấm Khóa ở Cân đối mới ghi nợ từng cặp (lưu kế hoạch chuyển); phát sinh sau khóa là đợt 2. Trả tiền khoản nhóm ghi vào sổ nhóm, không vào Sổ riêng. Góp quỹ chưa xác nhận thì cảnh báo trước khi khóa.
- Cơm trưa (nhóm dài hạn, không quỹ): một nồi trong tuần, chốt thứ Bảy; "Trả buổi này"; "Chốt riêng" cho người nghỉ.
- Làm tròn khi chuyển theo bước nhóm 1.000 (mặc định) / 5.000 / 10.000đ, lẻ từ nửa bước trở lên thì lên; chênh lệch do người nhận chịu. Chia đều ghi Sổ nợ: người khác nợ số tròn, người trả chịu lẻ.
- Đổi thủ quỹ có bàn giao (quỹ ở người cũ tới khi người mới xác nhận). Thủ quỹ ủy quyền ghi chi quỹ được. Chủ nhóm hoặc thủ quỹ "Mở lại tên" cho người mất phiên khách. Cân đối gộp quỹ vào thủ quỹ (không có dòng "Quỹ → Kiệt").
- Chi tiết khoản chi: lịch sử, sửa, xóa có Hoàn tác; ai ghi mới sửa; khoản chi từ quỹ chỉ thủ quỹ hoặc người được ủy quyền. Cài đặt chuyến có "Xóa chuyến" (chỉ khi đã khóa và chuyển xong). Lưu trữ chuyến chỉ ẩn ở máy mình, cần khóa trước.
- Đăng nhập: khách + Google. ĐÃ BỎ đăng ký SĐT + OTP (18/10). Apple để sau. Bật "Allow manual linking" trên Supabase.
- iPhone tách bộ nhớ Safari và app ở màn hình chính: phải "Lưu bằng Google" hoặc chép link khôi phục TRƯỚC khi thêm vào màn hình chính (màn "Giữ chỗ của bạn"). Link mời mở trong Zalo: chỉ cho xem, nút Mở bằng Safari + Chép link. Thông báo đẩy iPhone chỉ khi đã thêm vào màn hình chính, nên nhắc nợ bằng tin nhắn là chính.
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
  - SỬA 24/10 chiều muộn (anh góp ý "icon thanh menu vuông quá" + "chia bill vẽ lại %"): Sổ nợ và Chia bill dùng icon Done Nha VẼ RIÊNG bo tròn (`dn-notebook`, `dn-receipt`), không dùng Phosphor `notebook`/`receipt`. Cùng nét 1,5px, đầu nét tròn; sổ bo 4,5 và rộng hơn, hóa đơn bo 3,75 đáy lượn sóng, CÓ dấu % (hai chấm tròn + gạch chéo). Bản Fill là hình đặc, chi tiết khoét bằng màu viên vàng. Bốn mục menu còn lại vẫn Phosphor. Mã nguồn: `custom_icons.py` trong `dn-tools.zip`; hình SVG ghi trong README Design System.
  - Canvas bản 212: thêm bảng so sánh `DN-Icon-Phosphor` (1280 × 2810, dưới hàng cuối, ngoài 104 bảng tĩnh). Canvas bản 213: áp dụng Regular cho bảng bấm thử và chụp lại 104 bảng (chiều cao bảng không đổi); bảng icon giữ lại làm bản so sánh. Design System bản 21: mục "Biểu tượng" viết lại (quy tắc Regular/Bold/Fill, bảng tên icon), preview PhotoStack dùng Phosphor.
  - Canvas bản 214 (hệ thống nhảy lên 215 sau khi bù bảng DN-VaoNhom-Zalo): chụp lại 104 bảng với hai icon mới (chiều cao không đổi), bảng `DN-Icon-Phosphor` cao 3260 có thêm mục 2b "Sổ nợ và Chia bill" và cột "ĐANG DÙNG (canvas 214)". Design System bản 22: README "Biểu tượng" (hai icon riêng + mã SVG), TabBar, và xem trước của Banner, Chip, EmptyState, Notice, Tag, Stepper đổi sang Phosphor/icon riêng.
  - Cách làm trong script: `phosify.py` đổi icon vẽ tay sang Phosphor ở bước cuối của `gen_proto.py` (đối chiếu từng svg; Bold khi nét vẽ tay >= 2; Fill cho mục đang chọn; icon không có trong bảng ánh xạ giữ nguyên). Dữ liệu icon ở `phosphor_icons.json` (52 icon gồm 2 icon riêng, tạo bằng `build_phosphor_json.py`).
  - Phosphor `lock-simple` trông như túi xách ở 24px, dùng `lock`. Nút "Đổi số tiền" trên màn Mã QR dùng `qr-code` (mất dấu cộng của bản vẽ tay).
- Làm gọn file này (24/10): các mục 14–18/10 chuyển nguyên văn sang `docs/lich-su-chot-2026-10.md`, thay bằng "Quyết định đang áp dụng" (đã bỏ các ý bị thay). Thêm `docs/ban-giao-phien.md` để đổi model không mất ngữ cảnh, `docs/ke-hoach-tuan.md` cho việc theo tuần.

## Lỗi đã gặp, đừng lặp lại
- Prompt dùng lại được mà chỉ nằm trong hội thoại thì mất khi hội thoại bị tóm tắt (prompt Figma Make 21/10). Lưu vào `06-claude-input/` của thư mục làm việc.
- Trả tiền theo kế hoạch đã khóa phải TRỪ khỏi kế hoạch, không cộng thành lượt chuyển mới (lỗi bắt được khi viết test 18/10).
- Đừng nói chỉ Safari mới thêm được vào màn hình chính trên iPhone; Chrome và Edge cũng được.
- Giá gói của MoVi Group trên App Store Việt Nam là đồng (119.000 / 409.000 / 549.000), không phải USD.
- Sửa nguyên bảng trong tài liệu dễ mất định dạng; sửa từng ô hoặc từng dòng.
- Đặt mốc "app sẵn sàng" theo ngày đi trừ thời gian thử, không phải theo ngày đi.
- Supabase gói Free đã kiểm 17/10/2026 trên trang giá chính thức: 500 MB số liệu, 1 GB ảnh, 5 GB tải xuống, 50.000 người dùng/tháng, tối đa 2 dự án, tự ngủ sau 1 tuần không dùng. Đăng nhập Apple cần tài khoản Apple Developer (chưa kiểm giá); chuyến Đà Lạt dùng khách và Google trước. Pháp lý đã nghiên cứu 18/10 (xem mục Chốt 18/10) nhưng chỉ là suy luận từ văn bản, chưa có ý kiến luật sư.
- Địa chỉ dự án Supabase và khóa publishable chỉ nằm trong file cấu hình của app, không ghi vào tài liệu hay trí nhớ; khóa secret và service_role, mật khẩu cơ sở dữ liệu thì tuyệt đối không đưa cho Claude hay ghi ở đâu.
