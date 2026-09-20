# Bushy-Docs

Bushy-Docs is a lightweight, browser-based writing workspace built around **Bushy Writer v0.2**. It provides a distraction-friendly editor for drafting documents, saving them locally, adding images, and exporting finished work without requiring a backend.

**Website:** <https://bushydocs.netlify.app>

## Features

- ✍️ Rich-text editing with **bold, italic, underline, strikethrough, headings, lists, and blockquotes**
- 📝 New documents, document titles, and automatically saved drafts
- 💾 Browser-local document storage using `localStorage`
- 🖼️ Images from URLs, local uploads, clipboard pastes, and drag-and-drop
- ↔️ Image alignment controls and image removal
- 🔐 Optional AES encryption for locally stored document content
- 🌙 Light/dark theme toggle
- 📊 Live word count, character count, reading-time estimate, and storage usage
- 📋 Built-in templates for blog posts and meeting notes
- 📤 Export to Markdown or JSON backup

## Getting started

1. Clone the repository:

   ```bash
   git clone https://github.com/gfsorg/Bushy-Docs.git
   cd Bushy-Docs
   ```

2. Open `index.html` in a modern web browser.

For a local development server, you can also use any static HTTP server, for example:

```bash
python -m http.server 8000
```

Then visit <http://localhost:8000>.

## How it works

Bushy Writer is currently a self-contained front-end application. The main implementation lives in [`index.html`](./index.html), which contains the UI, styling, and JavaScript application logic.

Documents are stored in the browser's `localStorage`. Each saved document contains its title, editor content, encryption state, and update timestamp. There is no application server or database in this repository.

### Encryption

The editor can optionally encrypt saved document content with AES using CryptoJS. Encryption is performed in the browser before the document is written to `localStorage`.

This is intended as a convenient local privacy feature, not a substitute for a professionally audited password-management or secure-storage system. Keep your encryption password safe: the application does not provide a password-recovery mechanism.

## External dependencies

The application currently loads several front-end dependencies from CDNs:

- [Tailwind CSS](https://tailwindcss.com/)
- [Font Awesome](https://fontawesome.com/)
- [Google Fonts](https://fonts.google.com/) — Inter and JetBrains Mono
- [CryptoJS](https://cryptojs.gitbook.io/docs/) — AES encryption

An internet connection may therefore be required when loading the page unless these dependencies are made local.

## Project structure

```text
Bushy-Docs/
├── index.html   # Bushy Writer application
├── README.md    # Project documentation
└── LICENSE      # Project license
```

## Exporting documents

Use the **Export** menu in Bushy Writer to download the current document as:

- **Markdown (.md)** — a simple text/Markdown export of the editor contents
- **JSON (.json)** — a backup containing the document title and editor HTML

## Status

Bushy Writer is currently at **v0.2**. The project is intentionally small and self-contained, making it easy to run, inspect, and extend.

## Contributing

Bug reports, improvements, and feature ideas are welcome. For changes, please keep the application dependency-light and preserve the ability to run it as a static page.

## License

See [LICENSE](./LICENSE) for the applicable license terms.
