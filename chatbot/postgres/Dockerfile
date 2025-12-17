FROM postgres:13

RUN apt-get update && \
    apt-get install -y --no-install-recommends wget build-essential postgresql-server-dev-13 && \
    rm -rf /var/lib/apt/lists/*

RUN wget https://github.com/pgvector/pgvector/archive/v0.4.4.tar.gz && \
    tar -xzvf v0.4.4.tar.gz && \
    cd pgvector-0.4.4 && \
    make && \
    make install

COPY ./init.sql /docker-entrypoint-initdb.d/
