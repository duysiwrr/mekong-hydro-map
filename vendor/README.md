# `web/vendor/` — thư viện phục vụ tại chỗ

Thêm 14/09/2026. Trước đó `xem_ban_do.html` nạp maplibre-gl và pmtiles từ
`unpkg.com`. CDN bên ngoài là nguồn lỗi **"Failed to fetch"** thường gặp nhất
khi mạng chập chờn hoặc bị chặn, và là phụ thuộc vào một dịch vụ không do mình
kiểm soát — nay tải về đặt cạnh trang.

| Tệp | Nguồn | Phiên bản | Giấy phép |
|---|---|---|---|
| `maplibre-gl.js`, `maplibre-gl.css` | `https://unpkg.com/maplibre-gl@4.7.1/dist/` | 4.7.1 | BSD-3 → `LICENSE-maplibre-gl.txt` |
| `pmtiles.js` | `https://unpkg.com/pmtiles@3.0.7/dist/pmtiles.js` | 3.0.7 | BSD-3 → `LICENSE-pmtiles.txt` |

Tệp giữ **nguyên bản phát hành**, không sửa. Phiên bản maplibre đã kiểm chứng
qua header trong `maplibre-gl.js` (`.../maplibre-gl-js/blob/v4.7.1/LICENSE.txt`).

Trang kiểm tra trực tiếp (`typeof maplibregl !== "undefined" && typeof pmtiles
!== "undefined"`) và **chỉ lui về CDN khi file nội bộ thiếu** — không dùng
`onerror` vì `<script>` ở đó là đồng bộ, chạy đến dòng kiểm tra là chắc chắn đã
nạp xong; `document.write` giữ đúng thứ tự nạp (pmtiles phải có trước khi khởi
tạo `pmtiles.Protocol` ở cuối trang).

Thư mục này **được miễn quét bảo mật** trong `_quet_toan_bo_web()`
(`scripts/xay_csdl.py`) vì là mã nguồn thư viện ngoài, không chứa dữ liệu hay
đường dẫn nội bộ của mình. Khi nâng cấp thư viện: tải lại 2 file + giấy phép
tương ứng, cập nhật bảng trên, rồi chạy `node scripts/kiem_tra_trang_web.js`.
