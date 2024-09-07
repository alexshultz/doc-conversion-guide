# Instructions for Converting DOCX and DOC Files to PDF on macOS

This guide provides step-by-step instructions on how to convert `.docx` and `.doc` files to PDF using command-line tools on macOS. The instructions cover scenarios where you already have MacTeX installed or not.

## Converting DOCX to PDF Using Pandoc and LaTeX

### If You Don't Have Pandoc or MacTeX Installed

1. **Install Pandoc**:
   Use Homebrew to install `pandoc`:
   ```bash
   brew install pandoc
   ```

2. **Install MacTeX (if you don't have it installed yet** (for LaTeX support):
   ```bash
   brew install --cask mactex
   ```

3. **Update Your PATH (if necessary)**:
   If LaTeX commands are not recognized, add the following line to your `.zshrc` or `.bash_profile`:
   ```bash
   export PATH="/Library/TeX/texbin:$PATH"
   ```
   Then reload your shell:
   ```bash
   source ~/.zshrc  # or source ~/.bash_profile
   ```

4. **Convert DOCX to PDF**:
   Once both Pandoc and LaTeX are installed, use the following command to convert a `.docx` file to a PDF:
   ```bash
   pandoc /path/to/yourfile.docx -o /path/to/outputfile.pdf
   ```

## Converting DOC to PDF Using LibreOffice

Pandoc does not support `.doc` files, so you can use `LibreOffice` for `.doc` to `.pdf` conversions.

### Steps:

1. **Install LibreOffice**:
   Use Homebrew to install LibreOffice, which can handle `.doc` to `.pdf` conversion:
   ```bash
   brew install --cask libreoffice
   ```

2. **Convert DOC to PDF**:
   Use the following command to convert `.doc` to `.pdf`:
   ```bash
   /Applications/LibreOffice.app/Contents/MacOS/soffice --headless --convert-to pdf /path/to/yourfile.doc
   ```
   The PDF will be saved in the same directory as the original `.doc` file.

### If You Already Have LibreOffice Installed

You can directly use the following command to convert `.doc` files:
```bash
/Applications/LibreOffice.app/Contents/MacOS/soffice --headless --convert-to pdf /path/to/yourfile.doc
```
The resulting PDF will be placed in the same directory as your `.doc` file.

---

With these tools, you can convert both `.docx` and `.doc` files to PDF easily from the command line on macOS.
