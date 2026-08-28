# Font glyphs tu host

PBF glyph (SDF) cho MapLibre GL, chi 3 khoang can cho tieng Viet:
`0-255` (Basic Latin + Latin-1 Supplement), `256-511` (Latin Extended-A/B,
gom ă/đ/ơ/ư), `7680-7935` (Latin Extended Additional U+1E00-1EFF, gom toan
bo dau thanh tieng Viet: ạ/ệ/ố/ữ...).

Nguon: build san tu `github.com/openmaptiles/fonts` (nhanh `gh-pages`,
thu muc "Klokantech Noto Sans Regular/Bold") — Noto Sans, giay phep SIL OFL
1.1 (xem LICENSE-OFL.txt). Tai ve 29/08/2026, thay the
`demotiles.maplibre.org` (server demo, khong SLA) trong `glyphs:` cua style.

Đổi tên thư mục thành "Noto Sans Regular"/"Noto Sans Bold" (khớp
`text-font` dùng trong `xem_ban_do.html`), không đổi nội dung file.
