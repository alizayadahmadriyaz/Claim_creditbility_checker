# Contradiction Detector with FAISS + Gemini

[DEMO VIDEO](https://go.screenpal.com/watch/cTj6bmn2csK)

This project detects **factual or logical contradictions** between statements in a document (`.pptx` or `.txt`) using:

- **Sentence embeddings** (`all-MiniLM-L6-v2`)
- **FAISS ANN filtering** for semantic similarity search
- **Google Gemini API** (`gemini-2.5-flash`) for contradiction classification

---

## Features
Extracts text from `.pptx` slides or `.txt` files (with references like `Slide 3:` or `Page 2:`)  

Converts statements into embeddings and finds semantically similar pairs with **FAISS**  

Runs quick **local filters** (e.g., number mismatches) before sending to the LLM  

Uses **Google Gemini** to classify contradictions into:
- Numerical
- Timeline
- Qualitative
- None (if no contradiction)

---

## Requirements

### 1. Python Dependencies
Install dependencies:
```bash
pip install -r requirements.txt
```
## ENV

### 2. Create .env
```bash
GOOGLE_API_KEY=Your_API_KEY
```
### 3. Add PPT path
```bash
    if __name__ == "__main__":
    file_path = Your PPT Path  # or .txt
    result = analyze_document(file_path)
    print(result.text)
```

### 4. Run File
```bash
    python analyze_ppt.py
```
