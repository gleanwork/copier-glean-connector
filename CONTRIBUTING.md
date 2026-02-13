# Contributing

## Development

To test the template locally:

```bash
copier copy . /tmp/test-connector --defaults
cd /tmp/test-connector
uv sync
uv run pytest
```

You can test each connector variant by passing `--data` flags:

```bash
copier copy . /tmp/test-basic --defaults --data connector_category=datasource --data datasource_type=basic
copier copy . /tmp/test-streaming --defaults --data connector_category=datasource --data datasource_type=streaming
copier copy . /tmp/test-async --defaults --data connector_category=datasource --data datasource_type=async_streaming
copier copy . /tmp/test-people --defaults --data connector_category=people
```

In each generated project, verify:

```bash
uv sync
uv run ruff check src/ tests/
uv run ruff format --check src/ tests/
uv run pyright
uv run pytest
```
