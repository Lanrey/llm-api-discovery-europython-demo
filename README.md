# LLM API Discovery — EuroPython 2026 Demo

Talk materials from EuroPython 2026 showing how zero-to-pipeline connects any API in under five minutes — the LLM discovers endpoints, auth, and pagination from just the provider name. Data engineers can reproduce the full fraud-detection demo on their laptops. Built with Python, Feast, MLflow, and Prometheus.

**Stack:** Python · zero-to-pipeline (agentctl/pipeline CLI) · Feast · MLflow · Prometheus · Linear API · uv

## What

Talk materials and a working fraud-detection demo for a EuroPython 2026 / PyData Helsinki presentation, showing how zero-to-pipeline eliminates manual connector writing — connecting Feast, MLflow, Prometheus, and Linear in under five minutes.

## Why

Data engineers spend hours writing boilerplate connectors, pagination handlers, and auth flows for each new API. This talk demonstrates that the entire setup can be done in shell commands using an LLM-powered discovery layer.

## How

A `fraud_demo` Python package generates 15,000 synthetic transactions (5.5% fraud rate), materialises Feast feature views to a local SQLite store, runs a scikit-learn model, logs to MLflow, pushes metrics to Prometheus, and files a Linear issue — all orchestrated as a DAG in 4.4 seconds. `pipeline source add <name>` uses the LLM to auto-discover endpoints and auth.

## Impact

Demonstrated live at PyData Helsinki — reframes data-pipeline setup from "hours of connector code" to "one CLI command", directly promoting the `zero-to-pipeline` open-source library to a data-engineering audience.

## Use Cases

- Conference attendees reproduce the full fraud-detection pipeline on their laptops with `uv run python -m fraud_demo.run_pipeline` — no cloud dependencies
- Show cursor-based checkpoint resumption: second `pipeline sync run mlflow` fetches only 3 new records, not 13
- Use as a standalone teaching resource for data-engineering workshops on LLM-powered API discovery