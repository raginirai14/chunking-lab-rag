# Chunking Lab: Text Chunking and Document Processing for RAG

An interactive, 45-minute, self-paced lesson on splitting documents into chunks for Retrieval-Augmented Generation (RAG).

**Live demo:** https://raginirai14.github.io/chunking-lab-rag/

## What students learn
- Why RAG systems split documents into chunks
- Fixed-size, sentence-based and recursive chunking
- How chunk size and overlap affect retrieval quality
- How to apply chunking in real AI applications

## Lesson flow (45 minutes)
1. Why chunk (5 min): clickable RAG pipeline diagram and sliding-window diagram
2. Playground (12 min): try strategies, size and overlap on any text, with a live document map
3. Retrieval challenge (12 min): answer 3 questions with the least context
4. Build it (6 min): Python code and a LangChain example
5. Quiz (6 min)
6. Real-world use (4 min)

## Repository structure
```
index.html                 Interactive lesson (open in any browser, no install)
code/chunkers.py           Fixed, sentence and recursive chunkers in plain Python
code/evaluate.py           The retrieval challenge as code
code/sample_doc.txt        Sample document (library rules)
code/test_chunkers.py      Unit tests
code/chunking_lab.ipynb    Hands-on Jupyter notebook
```

## Run it
- **Lesson:** open `index.html` in a browser, or use the live demo above.
- **Python (3.8+, no dependencies):**
```
cd code
python evaluate.py              # prints which settings answer 3/3 questions
python -m unittest -v           # runs the tests
jupyter notebook chunking_lab.ipynb
```

## Expected output of `python evaluate.py`
```
strategy    size  overlap  k  answered  chunks
fixed        120        0  1  1/3       6
fixed        120        0  3  1/3       6
fixed        200       30  1  3/3       4
sentence     250        0  1  3/3       4
recursive    250        0  1  3/3       4
recursive    250       20  1  3/3       4
recursive    900        0  1  3/3       1
```

## Note
The retriever scores chunks by shared keywords, a simplified stand-in for embedding similarity, so the effect of chunking is visible instantly and offline.
