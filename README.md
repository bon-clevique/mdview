# mdview

Markdown + Mermaid viewer for the terminal. Displays Markdown files with inline Mermaid diagrams converted to images.

## Features

- Renders Markdown in the terminal using `mdcat`
- Converts Mermaid diagrams to inline images via `mermaid-cli`
- Adds language labels to code blocks for readability

## Dependencies

- [mdcat](https://github.com/swsnr/mdcat) - Markdown rendering in terminal
- [mermaid-cli](https://github.com/mermaid-js/mermaid-cli) - Mermaid diagram rendering

## Installation

### Prerequisites

```bash
brew install mdcat
npm install -g @mermaid-js/mermaid-cli
```

### Install mdview

```bash
# Clone and add to PATH
git clone https://github.com/bon/mdview.git
chmod +x mdview/mdview
ln -s "$(pwd)/mdview/mdview" /usr/local/bin/mdview
```

Or simply copy the script to a directory in your `$PATH`:

```bash
cp mdview /usr/local/bin/
```

## Usage

```bash
mdview <markdown-file>
```

### Example

```bash
mdview README.md
mdview docs/architecture.md
```

## How it works

1. Parses the Markdown file for Mermaid code blocks
2. Converts each Mermaid diagram to a PNG image (dark theme, transparent background)
3. Replaces the code block with an image reference
4. Adds language labels above non-Mermaid code blocks
5. Renders the processed Markdown using `mdcat` with inline image support

## License

[MIT](LICENSE)
