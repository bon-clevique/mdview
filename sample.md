# mdview Sample

This file is a sample for testing `mdview` functionality.

## Features

`mdview` provides the following features:

- Markdown rendering in terminal
- Inline Mermaid diagram conversion
- Language labels for code blocks

## Architecture

```mermaid
flowchart TD
    A[Markdown File] --> B{mdview}
    B --> C[Detect Mermaid Blocks]
    C --> D[Convert to PNG via mmdc]
    D --> E[Replace with Image Reference]
    B --> F[Code Block Processing]
    F --> G[Add Language Labels]
    E --> H[Processed Markdown]
    G --> H
    H --> I[Render with mdcat]
    I --> J[Terminal Output]
```

## Processing Flow

```mermaid
flowchart LR
    subgraph Input
        MD[.md File]
    end

    subgraph Processing
        Parse[Parse] --> Detect[Detect Mermaid]
        Detect -->|Yes| Convert[PNG Conversion]
        Detect -->|No| Label[Add Labels]
        Convert --> Merge[Merge]
        Label --> Merge
    end

    subgraph Output
        Render[mdcat Render]
    end

    MD --> Parse
    Merge --> Render
```

## Code Samples

Regular code blocks are also formatted with language labels.

```bash
#!/bin/bash
mdview README.md
```

```python
def hello():
    print("Hello, mdview!")
```

## State Diagram

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Reading: File specified
    Reading --> Processing: Read complete
    Processing --> Converting: Mermaid found
    Processing --> Rendering: No Mermaid
    Converting --> Rendering: Conversion complete
    Rendering --> [*]: Display complete
```

## Summary

Run `mdview sample.md` to see this file rendered in your terminal.
