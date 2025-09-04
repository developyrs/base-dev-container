FROM mcr.microsoft.com/devcontainers/python:3.11-bookworm

# Install DuckDB CLI (latest stable)
RUN curl -L https://github.com/duckdb/duckdb/releases/latest/download/duckdb_cli-linux-amd64.zip \
    -o /tmp/duckdb.zip \
    && unzip /tmp/duckdb.zip -d /usr/local/bin \
    && rm /tmp/duckdb.zip

# Install pipx and Poetry
RUN apt-get update && apt-get install -y --no-install-recommends curl build-essential git \
    && rm -rf /var/lib/apt/lists/* \
    && pip install --no-cache-dir pipx \
    && pipx install poetry \
    && poetry config virtualenvs.create false

# Set working directory
WORKDIR /workspace

# Copy source code
COPY . .

CMD ["sleep", "infinity"]
