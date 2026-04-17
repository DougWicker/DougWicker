# Data Engineering Portfolio — GitHub Roadmap

## Context

- **GitHub:** [DougWicker](https://github.com/DougWicker)
- **Target Role:** Mid-level Data Engineer
- **Existing Skills:** Python (ETL), SQL, PostgreSQL, PostGIS, FME, pytest, uv, Tableau/Power BI
- **Existing Repos:** 6 repos — mostly 2023 mini-projects (BlogMe, Blue-Bank, Value-Inc), VideoGameCriticReview, ProblemSolutions, profile config


---

## Repository Roadmap

### Phase 1 — Foundations

#### 1. `etl-pipeline-framework` ⭐ Start here
- Modular Python ETL pipeline (extraction → validation → load to PostgreSQL)
- Docker container for the app; `uv` for environment management
- `pytest` for unit + integration tests
- Clean project structure: `src/`, `tests/`, `.env`, `Dockerfile`, `docker-compose.yml`
- **Why first:** Every DE job expects Python + SQL + testing + containerisation. Sets the foundation and code standards for everything else.

#### 2. `sql-and-duckdb-playbook` ⭐
- Advanced PostgreSQL patterns: window functions, CTEs, recursive queries, explain plans
- DuckDB as a second engine — same queries benchmarked locally, parquet file querying
- Notebooks + raw `.sql` files, well-commented
- **Why second:** Quick to build, strong signal, demonstrates SQL depth and DuckDB familiarity which is trending heavily in 2025–26.

---

### Phase 2 — Transformation Layer

#### 3. `dbt-analytics-engineering`
- dbt project using the dbt-duckdb adapter (fast, zero infra, perfect for portfolio)
- Dimensional model: staging → intermediate → mart layers on a realistic dataset
- Tests, documentation, lineage graph in README
- **Why here:** dbt is now standard on most mid-level DE job specs. dbt + DuckDB is the modern local dev pattern.

#### 4. `data-quality-framework`
- Builds on Repo 1's pipeline — adds a DQ layer
- Custom `pytest`-based checks + optionally Great Expectations profiles
- Runs as a step in the pipeline (pre-load validation)
- **Why here:** Shows production maturity. Few candidates proactively add DQ — it differentiates.

---

### Phase 3 — Orchestration

#### 5. `prefect-data-pipelines`
- Prefect orchestrating flows from Repos 1 and 4
- Docker Compose stack (Prefect server + PostgreSQL + DuckDB target)
- Realistic flows: daily ingest, dbt run trigger, DQ check, alerting on failure
- **Why here:** Needs foundation repos to pull in. Prefect is Python-native and increasingly preferred over Airflow for its simpler setup and better developer experience.

---

### Phase 4 — Differentiators & Capstone

#### 6. `open-data-pipeline` — Capstone
- End-to-end pipeline on a real public UK dataset (e.g. Environment Agency, ONS, OS OpenData)
- Stack: Python ingest → PostgreSQL/DuckDB → dbt transform → DQ checks → Prefect orchestration
- **Streamlit** dashboard as the serving layer — interactive data app to surface the pipeline's outputs
- Full Docker Compose stack; README with architecture diagram
- **Why last:** Showpiece repo. References patterns from all previous repos and demonstrates the full DE lifecycle. Streamlit ties the analytical output to a user-facing app — recruiters can see results without touching SQL.

---
