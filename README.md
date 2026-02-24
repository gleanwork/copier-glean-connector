# copier-glean-connector

A [copier](https://copier.readthedocs.io/) template for scaffolding custom [Glean](https://www.glean.com/) indexing connectors using the `glean-indexing-sdk`.

## Prerequisites

- [Python](https://www.python.org/) 3.10+
- [uv](https://docs.astral.sh/uv/) (recommended) or pip
- [copier](https://copier.readthedocs.io/) 9+

Install copier:

```bash
uv tool install copier
```

## Usage

Generate a new connector project:

```bash
copier copy gh:gleanwork/copier-glean-connector my-connector
```

The wizard will prompt for project name, connector type, and other options. After generation, the template automatically runs `git init`, `uv sync`, and `ruff format`.

## Connector Types

### Datasource Connectors

Index documents and content into Glean.

| Type | SDK Base Class | Best For |
|---|---|---|
| **Basic** | `BaseDatasourceConnector` | Small data sources (~1,000 records) where all data fits in memory |
| **Streaming** | `BaseStreamingDatasourceConnector` | Paginated APIs or larger datasets; yields records in batches |
| **Async Streaming** | `BaseAsyncStreamingDatasourceConnector` | Large or high-latency data sources; concurrent I/O with async generators |

### People Connectors

Index employee/people data into Glean using `BasePeopleConnector`.

## Updating a Generated Project

When this template is updated, pull changes into your project:

```bash
copier update
```

