# PAX Retrieval — Dense Retrieval & Re-ranking

**Status:** Production | **Version:** 1.0.0 | **Author:** PAX Reasoning Team  
**Domain:** 0-1.gg/pax/retrieval

---

## What Is PAX Retrieval?

PAX Retrieval performs dense vector search and cross-encoder re-ranking for information retrieval, enabling efficient semantic search across document corpora.

**Specifications:**
- Search method: FAISS (vector similarity)
- Re-ranking: Cross-encoder (90% accuracy improvement)
- Throughput: 1M queries/sec
- Latency: <100ms P95 (search + ranking)
- Corpus size: 10M documents (scalable)

---

## Architecture

- **Layer 1:** Query embedding (via PAX_EMBEDDINGS)
- **Layer 2:** Vector search (FAISS, ANN)
- **Layer 3:** Re-ranking (cross-encoder model)
- **Layer 4:** Result formatting

---

## Quick Start

```python
from pax_retrieval import Retriever

retriever = Retriever(base_url="http://localhost:8002")

# Search documents
results = retriever.search(
    query="How do transformers work?",
    top_k=5,
    rerank=True
)
for result in results:
    print(f"{result.score}: {result.text}")
```

---

## Integration

- **PAX_EMBEDDINGS:** Query embedding
- **PAX_KNOWLEDGE_GRAPH:** Document indexing
- **PAX_INFERENCE_CORE:** Context for reasoning
- **PAX_CACHE:** Cache frequent queries

---

**Next:** See APPENDIX/
