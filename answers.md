**Câu A1 (5đ) — HTTP & Browser
Nguồn tham chiếu: 01_introduction_html_universe.md → HTTP Request Lifecycle
1. Quy trình khi nhập https://shopee.vn

Thứ tự quá trình duyệt:
1. DNS Lookup
Trình duyệt hỏi DNS server để chuyển shopee.vn → địa chỉ IP server.
2. TCP Connection
Trình duyệt tạo kết nối TCP với server qua cổng 443 (HTTPS).
3. TLS/SSL Handshake
Thiết lập mã hóa bảo mật HTTPS, xác thực chứng chỉ SSL.
4. HTTP Request
Browser gửi request:
GET / HTTP/1.1
Host: shopee.vn
5. Server Response
Server trả về HTML + CSS + JS + hình ảnh.
6. Browser Parsing
Browser parse HTML → DOM Tree, CSS → CSSOM.
7. Render Tree + Layout
Kết hợp DOM + CSSOM → Render Tree → tính toán vị trí.
8. Paint/Render
Hiển thị trang hoàn chỉnh lên màn hình.

Mục 2.1. Tab Network trong DevTools cho thấy thông tin:
- Request URL
- Status Code (200, 404, 500)
- Request Method (GET/POST)
- File Type (HTML/CSS/JS/Image)
- Size
- Load Time / Waterfall
- Tổng thời gian tải

Mục 2.2 Mở tab của https://shopee.vn
Ảnh Screenshot Tab Network:
![alt text](image.png)
![alt text](image-1.png)
1. Status Code của request đầu tiên: Status = 200
2. Tổng thời gian load trang: Finish = 15.37s
3. Một request trả về file CSS: Type Stylesheet

**Câu A2 (5đ) — Semantic HTML
Nguồn tham chiếu: 04_semantic_html.md → Semantic HTML, SEO, Accessibility
- Vì Google đánh giá thấp vì cấu trúc HTML thiếu ngữ nghĩa (semantic), khiến search engine khó hiểu nội dung chính của trang.

- 4 lỗi Semantic:
Lỗi 1: Dùng <div> cho phần đầu trang thay vì <header>
<div class="header">
Vấn đề: Google không biết đây là phần đầu trang.
Sửa lỗi: <header>

Lỗi 2: Menu điều hướng không dùng <nav>
<div class="menu">
Vấn đề: Bot không nhận diện đây là navigation menu.
Sửa lỗi: <nav>

Lỗi 3: Tên sản phẩm không dùng heading (<h1>, <h2>)
<div class="title">iPhone 16 Pro</div>
Vấn đề: Google ưu tiên heading để hiểu chủ đề chính.
Sửa lỗi: <h1>iPhone 16 Pro</h1>

Lỗi 4: Sản phẩm không dùng <article>
<div class="product">
Vấn đề: Google không biết đây là một nội dung/sản phẩm độc lập.
Sửa lỗi: <article>

Lỗi 5: Ảnh thiếu thuộc tính alt
<img src="iphone.jpg">
Vấn đề: Google Image khó index
Sửa lỗi: <img src="iphone.jpg" alt="iPhone 16 Pro">

**Câu A3 — Block vs Inline (5đ)
Nguồn tham chiếu: 01_introduction_html_universe.md → Chương 02/03: Block vs Inline Elements

Vẽ bằng text art: kết quả hiển thị HTML
    Hộp 1
    Text A Text B
    Hộp 2
    Text C Text D
    Hộp 3
- Giải thích: Các thẻ <div> trong đoạn HTML trên là block-level elements nên mỗi thẻ sẽ chiếm toàn bộ chiều ngang của trang và tự động bắt đầu trên một dòng mới, vì vậy “Hộp 1”, “Hộp 2” và “Hộp 3” đều xuất hiện thành từng khối riêng biệt, tách nhau rõ ràng theo chiều dọc. 
+ Tiếp đó <span> và <strong> là inline elements nên chúng không chiếm toàn bộ chiều rộng mà chỉ sử dụng đúng phần không gian cần thiết cho nội dung bên trong. Vì vậy, “Text A” và “Text B” sẽ hiển thị liên tiếp trên cùng một dòng, tương tự “Text C” và “Text D” nếu còn đủ chỗ hiển thị.
+ <strong> còn mang ý nghĩa nhấn mạnh nội dung (thường in đậm), nhưng về cách bố trí dòng thì vẫn hoạt động như một phần tử inline giống <span>. 

**Câu A4 (5đ) — Table
Nguồn tham chiếu: 05_tables_hyperlinks.md → Table Structure (thead, tbody, tfoot)
Giải thích sự khác nhau giữa <thead>, <tbody>, <tfoot>:
+ <thead> là phần đầu của bảng, dùng để chứa hàng tiêu đề (header row), giúp xác định tên các cột như “Tên sản phẩm”, “Giá”, “Số lượng”, đồng thời hỗ trợ trình duyệt, SEO và screen reader hiểu cấu trúc bảng rõ hơn.
+ <tbody> là phần thân bảng, chứa toàn bộ dữ liệu chính của bảng, tức các hàng nội dung thực tế mà người dùng cần xem hoặc so sánh.
+ <tfoot> là phần cuối bảng, thường dùng cho tổng kết, ghi chú hoặc các thông tin như tổng tiền, trung bình, hoặc kết luận dữ liệu.

- Không nên dùng table để tạo layout toàn bộ trang web vì:

+ Table không mang ý nghĩa semantic cho bố cục trang, khiến Google và công cụ tìm kiếm khó hiểu cấu trúc nội dung chính.
+ Table làm giảm accessibility vì screen reader sẽ hiểu nhầm nội dung là dữ liệu dạng bảng thay vì giao diện bố cục.
+ Table khó responsive trên điện thoại và thiết bị nhỏ, vì cấu trúc hàng/cột cứng nhắc không linh hoạt như CSS Flexbox hoặc Grid.
+ Code layout bằng table thường dài, rối, khó bảo trì và chỉnh sửa hơn so với semantic HTML + CSS hiện đại.

**B3 Bài B3 (15đ) — Debug HTML
# Bài B3 — Debug HTML

Nguồn tham chiếu: 01_introduction_html_universe.md → HTML5 Structure Basics, 04_semantic_html.md → Semantic Tags, 05_tables_hyperlinks.md → Table Structure

Tìm lỗi file HTML:
Lỗi 1: Dòng 1 — `<!DOCTYPE>` sai chuẩn — Sửa thành `<!DOCTYPE html>`
Lỗi 2: Dòng 2 — Thiếu `lang="vi"` trong thẻ `<html>` — Thêm `lang="vi"`
Lỗi 3: Dòng 4 — Thẻ `<title>` không đóng — Thêm `</title>`
Lỗi 4: Dòng 5 — `utf8` sai chuẩn — Sửa thành `UTF-8`
Lỗi 5: Thiếu meta viewport — Thêm `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
Lỗi 6: `<h1>` không đóng đúng — Sửa `</h1>`
Lỗi 7: Thẻ `<a>` đầu tiên không đóng — Thêm `</a>`
Lỗi 8: Link `href="home"` không rõ ràng — Sửa `home.html`
Lỗi 9: `<img>` thiếu `alt` — Thêm mô tả ảnh
Lỗi 10: `<b>` và `<p>` lồng sai thứ tự — Dùng `<strong>` đúng semantic
Lỗi 11: Bảng thiếu `<thead>` và `<tbody>` — Bổ sung cấu trúc chuẩn
Lỗi 12: Dùng `<td>` cho header — Sửa thành `<th>`
Lỗi 13: Có 2 thẻ `<main>` — Đổi phần sidebar thành `<aside>`
Lỗi 14: Footer thiếu đóng `</p>` — Bổ sung đầy đủ