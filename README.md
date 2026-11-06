# Mini-Jev: support inbox triage

A small Streamlit app that triages incoming support messages with zero-shot classification, no training data or fine-tuning required.

Paste a customer message in and it will:

- **Route it** — billing, technical problem, sales question, or thank you — and auto-route only above a confidence threshold you control, otherwise hand it to a human
- **Score urgency** on a 1-3 scale (can wait a week / handle today / needs action now)
- **Flag tone** — how angry or frustrated the message sounds

All of this runs on [MoritzLaurer/deberta-v3-base-zeroshot-v2.0](https://huggingface.co/MoritzLaurer/deberta-v3-base-zeroshot-v2.0) via Hugging Face `transformers`, which classifies text against plain-English labels without needing a labelled dataset for this specific task.

## Run it

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Why

Most support-inbox classifiers need a training set before they're useful. This is the other end of the trade-off: zero setup, works on day one, less accurate than a tuned model would be. Good enough to see whether automatic triage is worth building properly before investing in one.
