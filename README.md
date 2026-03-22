# Bookworm 📚

A lightweight NLP engine that generates **book cards** from Project Gutenberg texts.

## Features

| Command | Description |
|---|---|
| `--lexdiv <ID>` | Lexical diversity metrics (TTR, hapax, mean word length…) |
| `--topics <ID>` | Topic modeling — top 10 words per section |
| `--entities <ID>` | Named Entity Recognition — characters & locations |
| `--summarize <ID>` | Extractive book summary |
| `--similar <ID>` | 5 most similar books from the collection |
| `--card <ID>` | Full book card combining all analyses |

## Setup

```bash
# Clone the repo
git clone <your-repo-url>

# Create a virtual environment
python3 -m venv .venv
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Download spaCy model (for NER)
python -m spacy download en_core_web_sm
```

## Usage

```bash
# Lexical diversity for Alice in Wonderland (Gutenberg ID: 11)
python bookworm.py --lexdiv 11

# Full book card
python bookworm.py --card 11
```

## Project Structure

```
bookworm.py          # CLI entry point
src/
├── fetcher.py       # Download & cache Gutenberg books
├── cleaner.py       # Strip headers/footers, tokenize
├── cache.py         # Result caching on disk
├── lexdiv.py        # Lexical diversity metrics
├── topics.py        # Topic modeling (LDA/LSA)
├── entities.py      # Named Entity Recognition
├── summarizer.py    # Extractive summarization
├── similarity.py    # TF-IDF + cosine similarity
└── card.py          # Book card aggregation
cache/               # Cached books & results (gitignored)
requirements.txt
README.md
```

## Book Collection

The similarity engine works on a curated collection of 21 books spanning three genres:
Children/Young Adult, Crime/Mystery/Thriller, and Science-Fiction/Fantasy.

## License

Educational project — Epitech.