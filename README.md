# Social Media Analytics and NLP with NLTK

An educational Jupyter notebook introducing social media analytics, Twitter/X data collection, and foundational natural language processing (NLP) with Python's [Natural Language Toolkit (NLTK)](https://www.nltk.org/).

The notebook was prepared by **Arash Ghahraman** at **Eötvös Loránd University** as webinar material. It moves from the concepts behind social media research to a hands-on analysis of English-language tweets.

## What the notebook covers

- An introduction to social media and social media analytics
- Common research methods, including content, thematic, network, semantic, time-series, and machine-learning analysis
- Examples of accessing Twitter data with OAuth and Tweepy
- Loading a tab-separated tweet dataset with pandas
- Filtering tweets by language
- Sentence and word tokenization
- Hashtag extraction
- Stop-word and punctuation removal
- Porter stemming and WordNet lemmatization
- Part-of-speech (POS) tagging
- Word-frequency analysis and basic matplotlib visualizations

## Repository contents

```text
.
├── webinar_NLTK.ipynb   # Main tutorial notebook
├── twitter2500.csv      # Input dataset expected by the local-data section (not included)
└── README.md
```

> The notebook expects `twitter2500.csv` in the same directory. The file is read as a tab-separated dataset and should contain at least `lang` and `text` columns.

## Requirements

- Python 3
- Jupyter Notebook or JupyterLab
- NumPy
- pandas
- matplotlib
- NLTK
- oauth2 (only for the legacy API examples)
- Tweepy (only for the Twitter/X API examples)

Install the main dependencies with:

```bash
python -m pip install jupyter numpy pandas matplotlib nltk oauth2 tweepy
```

The notebook downloads these NLTK resources when needed:

- `stopwords`
- `punkt`
- `tagsets`
- `averaged_perceptron_tagger`
- `wordnet`

Depending on your installed NLTK version, you may also need newer resource packages such as `punkt_tab`, `averaged_perceptron_tagger_eng`, or `tagsets_json`.

## Getting started

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. Create and activate a virtual environment (recommended):

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

   On Windows PowerShell:

   ```powershell
   .venv\Scripts\Activate.ps1
   ```

3. Install the dependencies:

   ```bash
   python -m pip install jupyter numpy pandas matplotlib nltk oauth2 tweepy
   ```

4. Place `twitter2500.csv` beside the notebook if you want to run the local-dataset section.

5. Start Jupyter:

   ```bash
   jupyter notebook webinar_NLTK.ipynb
   ```

6. Run the cells in order. Skip the live Twitter/X API cells unless you have updated credentials and API-compatible code.

## Optional Twitter/X API configuration

The notebook imports credentials from a local module named `twitter_credentials.py`. If you use this section, create the file locally with the following structure:

```python
CONSUMER_KEY = "your-consumer-key"
CONSUMER_SECRET = "your-consumer-secret"
ACCESS_KEY = "your-access-token"
ACCESS_SECRET = "your-access-token-secret"
```

Never commit this file. Add it to `.gitignore`:

```gitignore
twitter_credentials.py
twitter_credentials.json
fetched_tweets.txt
.ipynb_checkpoints/
.venv/
```

## Compatibility note

The live data-acquisition examples use the legacy Twitter API v1.1 and older Tweepy interfaces, including `api.search`, `StreamListener`, and `wait_on_rate_limit_notify`. Current X API access levels and recent Tweepy versions may not support these calls as written. Treat those cells as historical examples unless you update them for the current API; the CSV-based NLTK tutorial can be used independently.

## Learning outcomes

After completing the notebook, you should be able to:

- Load and filter social-media text with pandas
- Tokenize text into sentences and words
- Remove common noise such as punctuation and stop words
- Compare stemming with lemmatization
- Assign POS tags to tokens
- Build a simple word-frequency distribution
- Recognize the security and compatibility considerations of social-media APIs

## Known limitations

- `twitter2500.csv` is required but is not embedded in the notebook.
- Some cells depend on live API credentials and historical endpoints.
- The final frequency plots are exploratory and may be difficult to read without selecting the most frequent terms first.
- The last `Draft` section contains incomplete experimental code and is not part of the main workflow.

## License

No license is specified in the notebook. Add a `LICENSE` file before distributing or reusing the material outside the terms permitted by its author.

## Author

**Arash Ghahraman**  
Eötvös Loránd University
