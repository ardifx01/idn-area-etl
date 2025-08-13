# 📄 idn-area ETL

A command-line interface for extracting Indonesian administrative area data from PDF files, transforming it, and saving it in structured CSV format.

The extractor processes PDF tables containing area codes and names for provinces, regencies, districts, and villages, organizing them into separate CSV files with proper hierarchical relationships.

## Usage

```
Usage: idn-area-etl [OPTIONS] PDF_PATH

Extract tables of Indonesian administrative areas data from PDF file and save the cleaned data to a CSV file.

╭─ Arguments ──────────────────────────────────────────────────────────────────────────────╮
│ *    pdf_path      FILE  Path to the PDF file [default: None] [required]                 │
╰──────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ────────────────────────────────────────────────────────────────────────────────╮
│ --chunk-size          -c      INTEGER    Number of pages to read per chunk [default: 3]  │
│ --range               -r      TEXT       Specific pages to extract, e.g., '1,3,4' or     │
│                                          '1-4,6'                                         │
│                                          [default: None]                                 │
│ --output              -o      TEXT       Name of the output CSV file (without extension) │
│                                          [default: None]                                 │
│ --destination         -d      DIRECTORY  Destination folder for the output files         │
│ --parallel                               Enable parallel processing for reading PDF      │
│                                          tables                                          │
│ --version             -v                 Show the version of this package                │
│ --install-completion                     Install completion for the current shell.       │
│ --show-completion                        Show completion for the current shell, to copy  │
│                                          it or customize the installation.               │
│ --help                                   Show this message and exit.                     │
╰──────────────────────────────────────────────────────────────────────────────────────────╯
```

## Development Setup

### Prerequisites

- [`uv`](https://docs.astral.sh/uv/getting-started/installation) package manager
- Python 3.12 or higher

> Tip: You can use `uv` to install Python. See the [`uv` Python installation guide](https://docs.astral.sh/uv/guides/install-python) for more details.

### Installation Steps

1. Clone this repository
1. Navigate to the project directory
1. Install dependencies using `uv`:
   ```bash
   uv sync --all-extras
   ```
1. Run the tool locally

   You can run the tool directly using `uv` or by activating the virtual environment created by `uv`.

   With `uv`:
   ```bash
   uv run idnareaetl --help
   ```

   From the virtual environment:
   ```bash
   source .venv/bin/activate
   idnareaetl --help
   ```

   > **Note:** To exit the virtual environment, use the command `deactivate`.

## Building the Package

To build the package, you can use the `uv` command:

```bash
uv build
```
