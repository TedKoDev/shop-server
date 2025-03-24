FROM postgres:latest

# Install build dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    git \
    postgresql-server-dev-17 \
    && rm -rf /var/lib/apt/lists/*

# Clone and install pgvector
RUN git clone --branch v0.5.1 https://github.com/pgvector/pgvector.git \
    && cd pgvector \
    && make \
    && make install

# Clean up
RUN apt-get remove -y build-essential git postgresql-server-dev-17 \
    && apt-get autoremove -y \
    && rm -rf /pgvector

# 데이터 디렉토리 유지
VOLUME /var/lib/postgresql/data

# 기본 포트 노출
EXPOSE 5432
