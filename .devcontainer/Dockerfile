FROM mcr.microsoft.com/devcontainers/python:3.11

# Add jq, docker CLI, ping
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y --no-install-recommends \
       jq docker.io iputils-ping \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Install DuckDB CLI (latest stable)
RUN curl -L https://github.com/duckdb/duckdb/releases/latest/download/duckdb_cli-linux-amd64.zip \
    -o /tmp/duckdb.zip \
    && unzip /tmp/duckdb.zip -d /usr/local/bin \
    && rm /tmp/duckdb.zip

# Install uv (standalone binary)
RUN curl -LsSf https://astral.sh/uv/install.sh | sh \
    && mv /root/.local/bin/uv /usr/local/bin/uv \
    && mv /root/.local/bin/uvx /usr/local/bin/uvx

