# LaTeX Thesis Project

## Project Structure

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

- `main.tex`: Main entry point for compiling the thesis.
- `preamble.tex`: Common packages and settings.
- `references.bib`: Bibliography file.
- `appendices/`: Appendix files.
- `chapters/`: Main content chapters.
- `frontmatter/`: Front matter (cover, abstract, etc.).
- `images/`: Figures and images.

## How to Use on Overleaf

1. Upload the entire project folder to Overleaf.
2. Set `main.tex` as the main file.
3. Click "Recompile" to build the PDF.

## Local Setup (Windows & macOS with VS Code)

### Prerequisites
- [VS Code](https://code.visualstudio.com/)
- [LaTeX Workshop extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
- LaTeX distribution:
  - **Windows**: [MiKTeX](https://miktex.org/download)
  - **macOS**: [MacTeX](https://tug.org/mactex/)

### Steps
1. Install a LaTeX distribution (MiKTeX or MacTeX).
2. Install VS Code and the LaTeX Workshop extension.
3. Open the project folder in VS Code.
4. Open `main.tex` and click "Build LaTeX project" (or use `Ctrl+Alt+B`).

## Notes
- Always compile `main.tex`.
- Ensure all required packages are installed (MiKTeX/MacTeX will prompt if missing).
- For Overleaf, all files must be uploaded, including images and bibliography.
- Use UTF-8 encoding for all `.tex` files.

---

For questions or issues, contact your instructor or project supervisor.