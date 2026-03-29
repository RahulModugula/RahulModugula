## Hey, I'm Rahul

Software engineer focused on distributed systems, data engineering, and ML infrastructure. Looking for new grad / early-career roles (F-1 OPT eligible).

### What I Build

**[kronos](https://github.com/RahulModugula/kronos)** — Distributed job scheduler in Go. gRPC API, PostgreSQL-backed queue (`SELECT FOR UPDATE SKIP LOCKED`), leader election via advisory locks, cursor-based pagination, idempotency key deduplication, exponential backoff with jitter. Worker pool benchmarks at ~1.1M jobs/sec in isolation, ~2,800 jobs/sec end-to-end against Postgres. CI via GitHub Actions.

**[streamline](https://github.com/RahulModugula/streamline)** — Real-time event pipeline: GitHub Archive → Kafka → Spark Structured Streaming → Delta Lake. Exactly-once semantics via idempotent MERGE sink, schema evolution, late-data watermark routing, SLA tracking (p50/p95/p99 latency tiers), S3/MinIO storage abstraction, Prometheus metrics exporter. 39 tests across 6 test files.

**[quantai-dashboard](https://github.com/RahulModugula/quantai-dashboard)** — ML trading dashboard with ensemble models (RF + XGBoost + LightGBM + LSTM), walk-forward backtesting, paper trading, and portfolio optimization. FastAPI + Plotly Dash. 199 tests, Prometheus metrics, Alembic migrations.

**[athena](https://github.com/RahulModugula/athena)** — RAG-powered research assistant with hybrid search (pgvector + BM25), cross-encoder reranking, and RAGAS evaluation.

**[odin](https://github.com/RahulModugula/odin)** — Multi-agent code review system combining Tree-sitter AST analysis with LLM agents for security, performance, and style feedback.

### Tech

Go · Python · TypeScript · gRPC · PostgreSQL · Kafka · Spark · Delta Lake · FastAPI · PyTorch · scikit-learn · Redis · Docker · Prometheus
