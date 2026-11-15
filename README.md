
# DocuMind AI

### CPU-Based Retrieval-Augmented Generation for Intelligent PDF Question Answering

DocuMind AI is an AI-powered document intelligence application that
allows users to upload PDF documents, retrieve relevant information
using semantic and keyword search, and generate answers using a
locally executed language model.

## Features

- PDF text extraction using PyMuPDF
- Overlapping text chunking
- Semantic embeddings using Sentence Transformers
- FAISS vector similarity search
- Hybrid retrieval using semantic and TF-IDF search
- Local LLM inference using Qwen2.5-0.5B-Instruct
- Source-page references
- Interactive Gradio interface
- CPU-only execution without paid inference APIs

## Architecture

```text
             PDF DOCUMENT
                  |
                  v
           PDF TEXT EXTRACTION
                  |
                  v
              CHUNKING
                  |
                  v
         SENTENCE TRANSFORMERS
                  |
                  v
           FAISS VECTOR INDEX
                  |
          USER QUESTION
                  |
                  v
            HYBRID SEARCH
          /             \
    SEMANTIC SEARCH   TF-IDF SEARCH
          \             /
                  |
                  v
          RELEVANT CONTEXT
                  |
                  v
       QWEN2.5-0.5B-INSTRUCT
                  |
                  v
        GENERATED ANSWER
                  |
                  v
         SOURCE REFERENCES
```

## Technology Stack

| Component | Technology |
|---|---|
| Language | Python |
| Environment | Google Colab |
| PDF Processing | PyMuPDF |
| Embeddings | Sentence Transformers |
| Vector Database | FAISS |
| Keyword Retrieval | TF-IDF |
| Language Model | Qwen2.5-0.5B-Instruct |
| Interface | Gradio |
| Evaluation | Precision@5, Recall@5, MRR |

## Execution

1. Open the Colab notebook.
2. Install dependencies.
3. Load the local CPU language model.
4. Upload a PDF document.
5. Extract and chunk its contents.
6. Generate embeddings and build the FAISS index.
7. Retrieve relevant passages.
8. Generate answers using the local language model.

## Evaluation

An initial evaluation was performed using five manually
labelled questions from the research paper
"Attention Is All You Need".

The initial page-level retrieval evaluation reported:

- Precision@5: 0.76
- Recall@5: 1.00
- MRR: 1.00

These are preliminary results from a small evaluation set.
They should not be interpreted as general-purpose retrieval
accuracy or answer-generation accuracy.

## Limitations

- Small language models can produce hallucinated answers.
- CPU inference is slower than GPU inference.
- Retrieval quality depends on document chunking and query quality.
- OCR is not implemented for scanned PDFs.
- Citation generation requires further verification.

## Future Improvements

- Reranking with cross-encoder models
- OCR support for scanned PDFs
- Improved citation verification
- Larger quantized language models
- Automated RAG evaluation
- Persistent vector database storage

## Project Type

Artificial Intelligence | Natural Language Processing |
Retrieval-Augmented Generation | Large Language Models

## Author

Add your name and professional contact details here.

---

Built using open-source AI technologies.
