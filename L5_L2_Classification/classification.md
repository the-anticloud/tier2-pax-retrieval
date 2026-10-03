# L5 Narrow / L2 General Classification — PAX_RETRIEVAL
**Platform:** Anticloud | **PAX:** 27B | **IP:** USPTO pending 2026, Anticloud FZ LLE
**Domain:** RAG retrieval module: hybrid dense+sparse search for PAX 27B

## L5 Narrow
PAX_RETRIEVAL operates at L5 Narrow within its specialized scope: rag retrieval module: hybrid dense+sparse search for pax 27b.
It does not generalize outside this function. PAX 27B inference is scoped to this module's
specific input/output contract. All outputs are deterministically validated before AIOSS append.

## L2 General
PAX_RETRIEVAL is available to all 9 Anticloud deployment tiers. Any tier project that needs
rag retrieval module: hybrid dense+sparse search for pax 27b capability calls PAX_RETRIEVAL without reconfiguration. Same API across all domains.

## PAX Integration
PAX 27B interfaces with PAX_RETRIEVAL as a specialized inference module. Inputs are preprocessed
to PAX_RETRIEVAL's schema, PAX generates outputs within that schema, and results are AIOSS-chained
before being returned to the calling module.

## AIOSS Audit Relevance
Every retrieval result (query hash + top-k chunk hashes + retrieval strategy) is appended to the AIOSS chain.
H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n)
Full reproducible audit trail, verifiable offline without cloud.

## Regulatory
GDPR Art. 17 (retrieval must support erasure), ISO 27001 A.8.2
