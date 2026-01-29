# Dự Án Luận Văn LaTeX

## Cấu Trúc Project

```
main.tex
preamble.tex
references.bib
appendices/
    appendixA.tex
chapters/
    chap1.tex
    chap2.tex
    chap3.tex
    chap4.tex
    chap5.tex
    chap6.tex
    chap7.tex
frontmatter/
    abstract.tex
    acknowledgment.tex
    certification.tex
    cover.tex
    declaration.tex
    important_notice.tex
images/
```

- `main.tex`: Tập tin chính để biên dịch luận văn.
- `preamble.tex`: Khai báo các gói và thiết lập chung.
- `references.bib`: Tập tin tài liệu tham khảo.
- `appendices/`: Thư mục phụ lục.
- `chapters/`: Các chương nội dung chính.
- `frontmatter/`: Phần đầu (bìa, tóm tắt, v.v.).
- `images/`: Hình ảnh, minh họa.

## Hướng Dẫn Chạy Trên Overleaf

1. Tải toàn bộ thư mục project lên Overleaf.
2. Đặt `main.tex` làm tập tin chính.
3. Nhấn "Recompile" để biên dịch PDF.

## Cài Đặt Môi Trường (Windows & macOS với VS Code)

### Yêu Cầu
- [VS Code](https://code.visualstudio.com/)
- [LaTeX Workshop extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
- Bộ cài LaTeX:
  - **Windows**: [MiKTeX](https://miktex.org/download)
  - **macOS**: [MacTeX](https://tug.org/mactex/)

### Các Bước
1. Cài đặt MiKTeX hoặc MacTeX.
2. Cài đặt VS Code và extension LaTeX Workshop.
3. Mở thư mục project bằng VS Code.
4. Mở `main.tex` và nhấn "Build LaTeX project" (hoặc dùng `Ctrl+Alt+B`).

## Lưu Ý
- Luôn biên dịch từ `main.tex`.
- Đảm bảo đã cài đủ các package cần thiết (MiKTeX/MacTeX sẽ tự động hỏi nếu thiếu).
- Khi dùng Overleaf, cần tải lên đầy đủ các file (bao gồm hình ảnh, tài liệu tham khảo).
- Nên dùng mã hóa UTF-8 cho tất cả các file `.tex`.

---

Nếu có thắc mắc hoặc gặp lỗi, liên hệ giảng viên hoặc người hướng dẫn.