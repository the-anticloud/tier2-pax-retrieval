# Deploy Guide — PAX_RETRIEVAL
**Stack:** Python 3.11, FAISS, BM25 (rank-bm25), sentence-transformers, AIOSS_FORMAT | Air-gap capable

## Prerequisites
Anticloud core stack installed. PAX 27B weights (pax-27b-q4.gguf). AIOSS_FORMAT.

## Install
```bash
pip install anticloud-pax-retrieval
```

## AIOSS Integration
```bash
aioss init --module PAX_RETRIEVAL --output ./pax_retrieval.aioss
```

## Air-Gap
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(model_path="./pax-27b-q4.gguf", module="PAX_RETRIEVAL",
                     aioss_chain="./pax_retrieval.aioss",
                     classification="L5_NARROW_L2_GENERAL")
```

## Verification
```bash
aioss verify --chain ./pax_retrieval.aioss --verbose
python -m pax_retrieval.tests.smoke
```
