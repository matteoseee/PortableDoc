# PortableDOC (HTML)

<img width="1894" height="910" alt="image" src="https://github.com/user-attachments/assets/f87b3098-18d5-4744-96e7-e2a5122178ae" />

A text editor self-contained in a single HTML file: no dependencies, no installation, no internet connection required. Double-click to open it in your browser, and your data always stays on your computer.

Clean interface on a white background, featuring lightweight SVG icons.

Write from scratch or use Open to load a `.txt` or `.docx` file.

No server needed: works directly from `file://`.



## **How it works, in brief**

* **Editing:** A `contenteditable` element using the browser's native commands.
* **Pagination:** After every edit, paragraphs are measured and pushed to the next page when they exceed the bottom margin. Headers, footers, and page numbers are rendered as overlaid layers.
* **Reading DOCX:** ZIP archive decompressed using `DecompressionStream`, followed by XML reading via `DOMParser`.
* **Writing DOCX:** XML generation and hand-built ZIP archive (without compression), with zero libraries.
* **PDF:** Browser print dialog with `@page` configured to the chosen size.



## **Contributing**

Bug reports and proposals are welcome via Issues and Pull Requests. To keep the project simple, every modification should remain within the single file and avoid introducing external dependencies.



## **Features**

* **Text**
* Paragraph styles: Normal and Heading 1–5
* Font family and size (pt)
* Bold, italic, underline
* Text color and highlighter
* Alignment: left, center, right, justified
* Bulleted and numbered lists
* Clear formatting, undo, and redo
* **Paragraph \& Page**
* Top, bottom, left, and right margins in cm
* Line spacing and space after paragraph
* Left indent and first-line indent
* Page format: A4, A3, A5, Letter, Legal, portrait or landscape
* Automatic pagination: text flows to the next page upon reaching the bottom margin
* **Headers, Footers \& Page Numbers**
* Editable headers and footers repeated on every page
* Toggleable page numbers
* Option to set the starting display page for page numbers
* Option to set the starting page number count
* **Headings \& Table of Contents**
* Multilevel heading numbering (1, 1.1, 1.1.1, ...)
* Automatic Table of Contents with headings and page numbers, updating as you type
* **Images**
* Insert single or multiple images (PNG, JPEG, and other formats, converted when necessary)
* Resize by dragging the control handle or setting the width in pixels
* Position: inline with text, left, right, or centered
* File import and export



## **Supported Import \& Export Formats**

|Format|Import|Export|Notes|
|-|:-:|:-:|-|
|**TXT**|Yes|Yes|Plain text only. Disabled if the document contains images.|
|**DOCX**|Yes|Yes|Preserves styles, colors, margins, page size, header, footer, and images.|
|**PDF**|No|Yes|Via browser printing (Save as PDF).|

> \*\*Note:\*\* The PDF is generated using the browser's print dialog, which reproduces the pages exactly as they appear in the editor.



## **Known Limitations**

* **DOCX:** Lists are exported as plain text with "•" or numbers. Images are always inserted inline, even if wrapped beside text in the editor. The Table of Contents is exported as static text rather than an automatic Word TOC field.
* **DOCX Numbering:** If page numbers start on a page other than the first, Word may only update the field after pressing `F9`.
* **Pagination:** Word calculates layout using its own fonts, so page breaks in the exported DOCX may land in slightly different places than in the editor.
* **Long Paragraphs:** A paragraph that does not fit in the remaining page space moves in its entirety to the next page, leaving some blank space at the bottom.
* **Input Formats:** `.doc` files (Word 97–2003) are not supported. Please save them as `.docx` first.
* **Complex DOCX Files:** Nested tables, text boxes, shapes, footnotes/endnotes, and fields are not imported.
* **DOCX Reading:** Requires a browser with `DecompressionStream` support.



## **Compatibility**

|Browser|Minimum Version|
|-|-|
|Chrome / Edge|80|
|Firefox|113|
|Safari|16.4|



## **Privacy**

Everything happens locally in the browser. The file makes no network requests, and no content is ever sent to external servers.



## **Project Structure**

`index.html` — The entire application (HTML + CSS + JavaScript)



Enjoy!

