# LaTeX to Word Formula Converter

A powerful, intuitive web application that seamlessly converts LaTeX mathematical formulas into editable Word equations or high-quality PNG images. Designed for academics, researchers, and professionals who need to integrate complex mathematical notation into Microsoft Word documents.

## ✨ Features

### Smart Formula Detection
- **Automatic Recognition**: Intelligently detects LaTeX formulas embedded in plain text using multiple delimiters
- **Multi-Format Support**: Handles inline, block, and environment-based LaTeX expressions
- **Fallback Detection**: Recognizes LaTeX expressions even without explicit delimiters by analyzing mathematical syntax patterns
- **AI Copy Recovery**: Detects delimiter-free, line-based formulas commonly produced by AI chat copy/paste
- **macOS-friendly Normalization**: Optionally merges hard-wrapped AI text lines while preserving formula lines

### Flexible Export Options

#### 1. **MathML Export** (Editable in Word)
- Copies formulas in MathML format, compatible with Microsoft Word's equation editor
- Creates fully editable, scalable equations in Word documents
- Preserves all mathematical notation and formatting
- Uses a robust clipboard pipeline with rich MathML copy and automatic plain LaTeX fallback
- **How to Use**: 
  - Click "MathML kopyala" (Copy MathML)
  - Open Word equation editor (`Alt +=` on Windows, or `Insert › Equation` on macOS)
  - Paste (`Ctrl+V` or `Cmd+V`) — the formula appears as an editable equation object
  - Edit, resize, and format as needed

#### 2. **PNG Export** (High-Quality Images)
- Renders formulas as crisp, scalable PNG images
- Perfect for presentations, PDFs, or when editing capability isn't required
- High-resolution output (3x scale) for excellent clarity
- **How to Use**:
  - Click "PNG indir" (Download PNG)
  - The image downloads to your default folder
  - Insert into Word via `Insert › Pictures › This Device`
  - Resize and position as needed

### Modern, Professional UI
- **Dark Theme (Vercel Style)**: Sleek, minimalist black and white aesthetic
- **Fully Responsive**: Works flawlessly on desktop, tablet, and mobile devices
- **Real-time Statistics**: Character count updates as you type
- **Instant Rendering**: Live preview of all detected formulas
- **Keyboard Shortcuts**: Press `Ctrl + Enter` (Windows/Linux) or `Cmd + Enter` (macOS) to convert instantly

### Performance & Reliability
- **Instant Processing**: No server required — everything runs in your browser
- **Robust Error Handling**: Invalid LaTeX is highlighted with warning indicators
- **Visual Feedback**: Toast notifications confirm copy/download actions

## 📋 Supported LaTeX Delimiters

The converter recognizes formulas wrapped in any of these standard LaTeX delimiters:

| Delimiter | Type | Example |
|-----------|------|---------|
| `$...$` | Inline | `$E = mc^2$` |
| `$$...$$` | Block | `$$E = mc^2$$` |
| `\(...\)` | Inline | `\(E = mc^2\)` |
| `\[...\]` | Block | `\[E = mc^2\]` |
| `\begin{env}...\end{env}` | Environment | `\begin{equation}...\end{equation}` |

### Supported Environments
- `equation`, `equation*`
- `align`, `align*`
- `aligned`
- `gather`, `gather*`
- `multline`, `multline*`
- `matrix`, `pmatrix`, `bmatrix`, `vmatrix`, `Vmatrix`
- `cases`

## 🚀 Quick Start

### Installation
No installation required! Simply:
1. Download the project files
2. Open `latex_to_word_formula_converter.html` in any modern web browser
3. Start converting immediately

### Basic Usage

```
1. Paste or type your text containing LaTeX formulas
2. Click "Dönüştür" (Convert) or press Ctrl + Enter
3. Review the rendered formulas
4. For each formula:
   - Click "MathML kopyala" to copy as editable equation
   - Click "PNG indir" to download as image
5. Paste into Word (Alt += for MathML, or Insert › Pictures for PNG)
```

### Example Inputs

**Scientific Document:**
```
The quadratic formula is $x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$
and Einstein's mass-energy equivalence is $$E = mc^2$$
```

**Matrix Notation:**
```
For linear systems, $\mathbf{A}\mathbf{x} = \mathbf{b}$ 
can be solved when $\det(\mathbf{A}) \neq 0$
```

**Complex Equations:**
```
\begin{equation}
\int_{-\infty}^{\infty} e^{-x^2} \, dx = \sqrt{\pi}
\end{equation}
```

## 🎨 Technical Implementation

### Project Structure

```
latex-to-word-formula/
├── latex_to_word_formula_converter.html  # Main application (HTML + JavaScript)
├── styles.css                            # Styling and theming
└── README.md                             # This file
```

### Key Components

- **Formula Detection Engine**: Advanced regex-based parser with fallback heuristics
- **Rendering Engine**: KaTeX for mathematical typesetting
- **Export Pipeline**: 
  - MathML: Direct extraction from KaTeX output with clipboard API
  - PNG: HTML-to-canvas conversion with high-DPI scaling
- **UI Framework**: Vanilla JavaScript with CSS Grid/Flexbox

## 🛠️ Technologies Used

### Core Libraries

- **[KaTeX](https://katex.org/)** (v0.16.9)
  - Fast, reliable LaTeX math typesetting
  - Supports 800+ LaTeX commands and environments
  - Automatic error recovery with helpful messages

- **[html2canvas](https://html2canvas.hertzen.com/)** (v1.4.1)
  - Converts DOM elements to canvas
  - High-quality PNG rendering with configurable resolution
  - Cross-browser compatibility

### Frontend Stack
- **Vanilla JavaScript**: No framework dependencies
- **CSS3**: Modern features (CSS Grid, Flexbox, Custom Properties)
- **HTML5**: Semantic markup for accessibility
- **Modern APIs**: Clipboard API for secure copy operations

### Browser Requirements
- Modern browser with ES6 support
- Clipboard API support (Chrome 63+, Firefox 53+, Safari 13.1+, Edge 79+)
- Canvas support for PNG export
- At least 1GB RAM for processing large documents

## 📝 Advanced Features

### Smart Formula Fallback
If your LaTeX doesn't use explicit delimiters, the app intelligently detects mathematical content by recognizing:
- LaTeX commands (`\frac`, `\sqrt`, `\mathbf`, etc.)
- Mathematical operators (`_`, `^`, `\times`, etc.)
- Environment declarations (`\begin{equation}`, etc.)

### Error Handling
- **Invalid LaTeX**: Displays the problematic formula in a warning box with the error message
- **Missing Dependencies**: Graceful degradation if external resources fail
- **Edge Cases**: Handles nested delimiters and special characters correctly

### Performance Optimizations
- Single-pass regex matching for fast detection
- Lazy-loaded external libraries
- Efficient DOM manipulation
- Minimal reflows and repaints

## 💡 Use Cases

- **Academic Papers**: Convert research notes with formulas into Word documents
- **Engineering Documents**: Export technical specifications with complex equations
- **Educational Materials**: Create textbooks and course materials with proper equation formatting
- **Scientific Reports**: Include publication-quality mathematical notation
- **Thesis Writing**: Integrate formulas from computational notebooks into formal documents

## 🔒 Privacy & Security

- **100% Client-Side**: All processing happens in your browser
- **No Data Collection**: Your formulas are never sent to any server
- **No Tracking**: No analytics or telemetry
- **Secure Copy**: Uses the secure Clipboard API with user confirmation

## 🐛 Troubleshooting

### MathML Not Pasting in Word
- Ensure you're using Word desktop version (web version has limited support)
- Try pasting in a fresh equation box (`Alt +=` on Windows, `Insert › Equation` on macOS)
- Check that your system clipboard hasn't been cleared
- If your browser blocks rich clipboard types, the app automatically falls back to plain LaTeX copy

### PNG Quality Issues
- Increase your browser's zoom level before downloading
- Ensure sufficient RAM available
- Try a different browser if html2canvas fails

### Formula Not Being Recognized
- Check for correct delimiter usage
- Verify LaTeX syntax using [KaTeX Docs](https://katex.org/docs/autorender.html)
- Use explicit delimiters (`$...$`) rather than relying on fallback detection

## 📄 License

This project is open source and available for educational and professional use.

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs and issues
- Suggest new features
- Improve documentation
- Submit code improvements

## 📞 Support

For questions or issues:
- Check the troubleshooting section above
- Review the [KaTeX Documentation](https://katex.org/)
- Consult Microsoft Word's equation editor help

---

**Made with ❤️ for researchers, students, and professionals worldwide.**
