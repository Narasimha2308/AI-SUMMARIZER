# ✦ AI Text Summarizer

An AI-powered text summarization web app built with **Streamlit** and **BART** (Facebook's `bart-large-cnn` model). Summarize plain text, web articles, YouTube videos, or uploaded documents — all from one clean interface.

## Features

- **📝 Plain Text** — Paste any article, blog post, or long-form text and get a concise summary.
- **🔗 URL / YouTube** — Paste a web article link or a YouTube video URL. The app automatically extracts the article text or video transcript before summarizing.
- **📄 Document Upload** — Upload a file and summarize it directly. Supports:
  - PDF (`.pdf`)
  - Word documents (`.docx`)
  - Text files (`.txt`, `.md`)
  - CSV (`.csv`)
- **🎛 Adjustable Output** — Control summary length (max/min tokens) and generation parameters (beam width, length penalty, no-repeat n-gram) from the sidebar.
- **📊 Stats** — See input word count, summary word count, reduction percentage, and inference time after each run.
- **⬇ Download** — Export the generated summary as a `.txt` file.

## Tech Stack

- Python
- [Streamlit](https://streamlit.io/) — web app framework
- [Hugging Face Transformers](https://huggingface.co/docs/transformers) — BART model & tokenizer
- PyTorch
- BeautifulSoup4 — web article extraction
- pdfplumber — PDF text extraction
- python-docx — Word document extraction
- youtube-transcript-api — YouTube transcript extraction

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Narasimha2308/AI-SUMMARIZER.git
   cd AI-SUMMARIZER
   ```

2. (Recommended) Create a virtual environment:
   ```bash
   python -m venv venv
   venv\Scripts\activate      # Windows
   source venv/bin/activate   # macOS/Linux
   ```

3. Install dependencies:
   ```bash
   pip install streamlit transformers torch requests beautifulsoup4 pdfplumber python-docx youtube-transcript-api
   ```

## Usage

Run the app with:

```bash
streamlit run app.py
```

Then open the local URL shown in your terminal (usually `http://localhost:8501`).

1. Pick a tab — **Plain Text**, **URL / YouTube**, or **Upload Document**.
2. Provide your content (paste text, paste a URL, or upload a file).
3. For the URL/YouTube tab, click **Fetch Content** first, then **Summarize**.
4. Adjust output length and generation settings in the sidebar if needed.
5. Click **Summarize** and view the result, along with stats and a download option.

## Notes

- First run will download the `facebook/bart-large-cnn` model (~1.6 GB) from Hugging Face — this may take a few minutes depending on your connection.
- GPU (CUDA) is used automatically if available; otherwise the app falls back to CPU.
- YouTube transcript extraction requires the video to have captions/subtitles available.

## License

This project is open source and available for personal and educational use.
