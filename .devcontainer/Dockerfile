FROM mcr.microsoft.com/devcontainers/python:3.11-bookworm

# Install DuckDB CLI (latest stable)
RUN curl -L https://github.com/duckdb/duckdb/releases/latest/download/duckdb_cli-linux-amd64.zip \
    -o /tmp/duckdb.zip \
    && unzip /tmp/duckdb.zip -d /usr/local/bin \
    && rm /tmp/duckdb.zip

# Install uv (standalone binary)
RUN curl -LsSf https://astral.sh/uv/install.sh | sh \
    && mv /root/.local/bin/uv /usr/local/bin/uv \
    && mv /root/.local/bin/uvx /usr/local/bin/uvx
