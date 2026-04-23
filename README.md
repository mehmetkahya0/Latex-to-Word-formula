# LaTeX to Word Formula Converter

Bu proje, LaTeX içeren metni tarayıp formülleri görsel olarak render eder ve Word'e uygun biçimde dışa aktarmanıza yardımcı olur.

## Özellikler

- Metin içindeki LaTeX formüllerini otomatik algılar
- KaTeX ile hızlı ve temiz formül render'ı yapar
- Her formül için:
  - **MathML kopyalama** (Word'de düzenlenebilir denklem)
  - **PNG indirme** (Word'e görsel ekleme)
- Modern, responsive ve koyu tema destekli arayüz

## Desteklenen LaTeX sınırlandırıcıları

- `$...$` (inline)
- `$$...$$` (block)
- `\(...\)` (inline)
- `\[...\]` (block)

## Kullanım

1. `latex_to_word_formula_converter.html` dosyasını tarayıcıda açın.
2. Metninizi kutuya yapıştırın.
3. **Dönüştür** butonuna tıklayın.
4. İhtiyaca göre formül kartlarındaki:
   - **MathML kopyala** butonunu kullanın (Word'de `Alt +=` sonrası yapıştırın)
   - veya **PNG indir** ile görsel alın

## Dosya yapısı

- `latex_to_word_formula_converter.html`: Uygulama iskeleti ve JavaScript mantığı
- `styles.css`: Modern UI stilleri

## Kullanılan teknolojiler

- [KaTeX](https://katex.org/) — LaTeX render
- [html2canvas](https://html2canvas.hertzen.com/) — PNG dışa aktarma
