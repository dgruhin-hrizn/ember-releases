# Diagram, SVG and CSV Previews

See Mermaid diagrams, SVG images and CSV tables rendered, and switch back to the source in one click.

Ember can show some files rendered instead of as text: Mermaid diagrams, SVG images and CSV tables. The preview
keeps up with the file as you edit it, and uses your theme's colours.

## Mermaid diagrams

Files ending in `.mmd` or `.mermaid` open as a diagram by default. If the diagram has a syntax error, the preview
says **Unable to render** with the reason, and **View Source** opens the text.

## SVG images and CSV tables

`.svg` and `.csv` files still open as text by default. To see them rendered:

- Click **Show Preview** in the editor's title bar, or run **Show Preview**.
- Or right-click the file, choose **Open With…**, then **SVG Preview** or **CSV Table**.

SVG images are shown with any scripts removed. A CSV table shows the first 5,000 rows and 256 columns; for anything
beyond that, switch to the source.

> **Tip:** To make the preview the default for SVG or CSV files, use **Open With…** › **Configure default editor
> for '\*.svg'** (or '\*.csv') in VS Code.

## Back to the text

In any preview, click **Show Source** in the editor's title bar, or run
**Show Source**, to open the file in the normal text editor.

## Mermaid in Markdown

VS Code's own Markdown preview draws ` ```mermaid ` code blocks as diagrams too, in light and dark. They are drawn
inside Ember, so nothing is fetched from the network. A block with an error shows **Mermaid Syntax Error** with the
reason, then the code.

---

[All documentation](../README.md)
