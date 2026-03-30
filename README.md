# texforge-templates

Official template registry for [texforge](https://github.com/JheisonMB/texforge).

## Available Templates

| Template | Description |
|----------|-------------|
| `general` | Generic article — minimal setup for any document |
| `apa-general` | APA 7th edition — academic reports and theses |
| `apa-unisalle` | APA for Universidad de La Salle — thesis proposal format |
| `ieee` | IEEE journal format — technical papers |
| `letter` | Formal letter — Spanish business correspondence |

## Usage

```bash
# Create a project with the default template (general)
texforge new my-project

# Create a project with a specific template
texforge new my-thesis -t apa-general

# Add a template to local cache
texforge template add apa-unisalle
```

## Template Structure

Each template contains:

```
template-name/
├── template.toml     # Metadata and configuration
├── main.tex          # Entry point
├── bib/
│   └── references.bib
└── sections/
    └── ...
```

## License

MIT
