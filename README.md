# PDF Question Answering System (Extractive QA)

This project is a PDF-based Question Answering (QA) system built with a RoBERTa model. It extracts precise answers directly from uploaded PDF documents.

## Features

- Upload and process PDF files
- Extract text from PDFs
- Smart text chunking for model input
- Answer questions based on document content
- Display confidence score for each answer
- Support multiple questions (one per line)
- Show warnings for low-confidence answers

## Model

- `deepset/xlm-roberta-large-squad2`

This is an extractive QA model fine-tuned on SQuAD 2.0.

## Limitations

- Works only for extractive questions (the answer must exist in the source text)
- Does not generate creative or explanatory answers
- Performance depends on PDF text quality
- Scanned/image PDFs may require OCR for better results

## Installation

```bash
pip install transformers pymupdf torch
```

## How to Use

1. Open and run the notebook `QnA_from_PDF.ipynb`.
2. Upload your PDF file.
3. Enter one or more questions (one per line).
4. Review the extracted answer and confidence score.

## Example

Question:

```text
What is the capital of France?
```

Answer:

```text
Paris
```

Confidence:

```text
0.92
```

## Notes

- Low-confidence answers (for example, score < 0.40) should be treated carefully.
- Best results come from clean, text-based PDFs.
- If no clear answer exists in the document, the model may return a weak match.

## Future Improvements

- Add semantic retrieval for better context selection
- Add hybrid QA (extractive + generative)
- Improve handling for very long documents
- Add OCR pipeline for scanned PDFs