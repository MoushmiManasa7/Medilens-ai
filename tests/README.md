# Tests

Test suite for MediLens AI.

## Structure

- `backend/` (this folder, `tests/backend/`) — API and integration tests that talk to PostgreSQL
  - `test_health.py` — Health endpoint tests
  - `test_auth.py` — Auth tests
  - `test_reports.py` / `test_report_file.py` / `test_ingestion.py` — Report and upload tests
  - `test_retention.py` — Retention purge tests
  - `test_settings.py` — User settings tests
- `../backend/tests/` — Unit tests that do not require a database
  - `test_extraction.py` — Lab result extraction
  - `test_knowledge.py` — Chunking and embeddings
  - `test_rag.py` — RAG pipeline helpers
  - `test_safety.py` — Safety engine
  - `test_evaluation.py` — Evaluation helpers

There is no frontend test script (`npm test` is not configured).

## Running Tests

```bash
# Unit tests (no external services)
cd backend
pytest tests/ -v

# API / integration tests (need PostgreSQL, Redis, and Qdrant)
cd backend
pytest ../tests/backend -v
```
