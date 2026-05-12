# Báo cáo luận văn / đồ án tốt nghiệp được soạn thảo bằng **LaTeX**.

Phải công nhận là dùng cái này nhức hết cả đầu vì bữa giờ gặp lỗi liên tục 😟. Nào là lỗi tiếng việt - tiếng anh, rồi lỗi trình biên dịch (phải đổi từ pdfLatex --> XeLaTeX),... 

Nhưng bù lại thì xuất ra cái báo cáo cũng khá ok, giao diện ổn, dễ căn chỉnh hơn làm word. Mà Nói chung trường yêu cầu làm thì cứ làm cái đó vậy 😄.

Cơ bản thì cái này cũng là soạn thảo văn bản như word thôi, khác ở chỗ là có thêm mấy cái lệnh
định dạng chữ (in, thường, nghiêng, đậm, căn lề, mục lục, phụ đề, ...vv tùm lum :v)
để làm dc cái này thì phải đi kèm trình biên dịch **XeLaTeX** (tương tự như 
mingw của c++) và engine quản lý phần reference (tài liệu tham khảo) **BibTeX**.
Hai thứ này có sẵn sau khi mình cài nguyên bộ công cụ miktext (cái này tự tìm hiểu nhé).
Code thì tất nhiên là code trên **VS Code** hoặc **Overleaf** (cái này khuyên là không nên vì nó bào tiền lắm)

Giống như làm bài tập lớn c++ hay java, mình sẽ:

> Cài trình biên dịch —> cài extension —> vào vscode tạo dự án —> code —> biên dịch —> xuất ra pdf
>
---

## 2. Yêu cầu phải có
- **VS Code**  
- **LaTeX Workshop Extension**  

  Sau khi cài xong, một lúc sau sẽ có biểu tượng ▶️ để build và run
  thay vì phải chạy bằng lệnh giống như c++ hay java

- **Bộ LaTeX** (cài trên trang web chính chủ)
  - **Windows**: MiKTeX – https://miktex.org
  - **macOS**: MacTeX – https://tug.org/mactex/


---

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

Trong đó
- `main.tex` là File chính, điều phối toàn bộ tài liệu.  
    👉 *Luôn biên dịch từ file này.*
- `preamble.tex`: Khai báo các gói và thiết lập chung.
    
    👉 Cụ thể là khai báo package, font chữ, bố cục (ví dụ margin), ngôn ngữ (tiếng anh / tiếng việt), chèn link
- `references.bib`: Nơi định nghĩa tài liệu tham khảo (phần references trong báo cáo). 
    
    👉 Trong báo cáo nó gọi là Bibliography .
    Nói đơn giản là mình chèn mấy cái link bài báo của người khác nếu mình kham khảo của họ.
    Nhưng theo mình tìm hiểu thì không thể chèn trực tiếp như word mà phải có cách khác. 
    Mình sẽ "định nghĩa" từng bài báo vào file này rồi sau đó "import" vào `main.tex`.
    
    Phần này mình bị lỗi nhiều nhất, sửa 1 tiếng mới xong 🥲.
    
    ⚠️ Lưu ý, **Nếu bài báo có tiếng Việt thì nên bỏ dấu. Bị lỗi đấy**

- `appendices/`: Nơi chứa phụ lục.
- `chapters/`:  Các chương trong báo cáo (Chapter 1 → Chapter 7).
- `frontmatter/`: Phần đầu (bìa, cam kết, lời cảm ơn, tóm tắt, v.v.).
- `images/`: Hình ảnh, minh họa.

### Thiết lập trong setting (RẤT QUAN TRỌNG)
Phần này nhằm tránh các lỗi build mình đã gặp. Ví dụ như:

 - Phần reference không hiển thị trên báo cáo dù code đã đúng
 - Bấm ▶️ để build nhưng không thấy có gì mới trên báo cáo

Bấm tổ hợp `Ctrl + Shift + P` , vô file `settings.json`, rồi thêm vào đó cái đống dưới đây

```json
  // ===== LaTeX Workshop: Tools =====
  "latex-workshop.latex.tools": [
    {
      "name": "latexmk",
      "command": "latexmk",
      "args": [
        "-xelatex",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    }
  ],

  // ===== LaTeX Workshop: Recipes =====
  "latex-workshop.latex.recipes": [
    {
      "name": "latexmk (XeLaTeX)",
      "tools": ["latexmk"]
    }
  ],

  // ===== Set latexmk as default build =====
  "latex-workshop.latex.defaultRecipe": "latexmk (XeLaTeX)",

  // ===== Auto build on save (optional) =====
  "latex-workshop.latex.autoBuild.run": "onSave",

  // ===== PDF preview =====
  "latex-workshop.view.pdf.viewer": "tab",

  // ===== Clean behavior =====
  "latex-workshop.latex.clean.fileTypes": [
    "*.aux",
    "*.bbl",
    "*.blg",
    "*.log",
    "*.out",
    "*.toc",
    "*.lof",
    "*.lot",
    "*.synctex.gz",
    "*.fdb_latexmk",
    "*.fls"
  ]
```
sau đó tắt đi / mở lại vscode.

📌 Từ giờ:

- Chỉ cần mở main.tex

- Bấm ở góc phải trên cùng ▶️ hoặc Ctrl + Alt + B

Kết quả là mình sẽ có một file báo cáo pdf hoàn chỉnh.

## Trường hợp có thể bị lỗi 

Cái kiểu build bằng nút ▶️ không phải lúc nào cũng phù hợp, vì sẽ có lúc mình sửa code
mà không hiểu tại sao build đi build lại mà báo cáo vẫn như cũ, không thay đổi gì. 

Ví dụ như trường hợp bị lỗi "Không hiển thị Reference" vừa nãy. Dù đã thêm & sửa code, sau đó
bấm ▶️ thì dữ liệu không đổ lên báo cáo. Lúc đó hỏi gpt mãi mới lòi ra là phải debug bằng cách build thủ công. Cụ thể, mình phải xóa mấy cái file .aux , .log, .out cũ đi vì mấy cái này track cấu hình cũ trong
khi code của mình là đã khác bọt nhiều lắm rồi.

Đầu tiên là phải xóa đi bằng lệnh

    latexmk -C

Sau đó build lại:
    
    latexmk -xelatex -f main.tex




## Lời kết

Mình viết file này để tự hướng dẫn bản thân cũng như người làm cùng nhóm viết báo cáo bằng Latex sao cho ok, có lỗi thì sửa được. 

Và tất nhiên không phải cái nào cũng hướng dẫn hết được. Trong quá trình làm sẽ có nhiều lỗi phải tự xử lý hoặc prompt gpt để sửa sao cho hợp lý.

Nhưng nói gì thì nói, để hạn chế conflict khi cả 2 cùng code cái dự án này, phải thống nhất một số quy ước chung:

- Không dùng `pdfLatex`, chỉ dùng `XeLaTeX`
- Không để tiếng việt, chỉ để tiếng Anh

Nhớ nhé, không khéo lúc prompt là bị gpt dắt như đăt bò rồi lỗi code luôn 😗

Đọc thêm: [Trải nghiêm người dùng Latex](https://dunglq2000.github.io/mathematics/stuff/latex/index.html)