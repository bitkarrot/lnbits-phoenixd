FROM python:3.10-slim-bullseye

ARG LNBITS_BRANCH=dev
ARG LNBITS_COMMIT_HASH=0076a85fdb557552f51c5ec11e0f8ff8df2e17de

RUN apt-get clean
RUN apt-get update
RUN apt-get install -y curl pkg-config build-essential libnss-myhostname
RUN apt-get install -y --no-install-recommends bash git \
    && apt clean

RUN curl -sSL https://install.python-poetry.org | python3 -
ENV PATH="/root/.local/bin:$PATH"

# needed for backups postgresql-client version 14 (pg_dump)
RUN apt-get install -y apt-utils wget
RUN echo "deb http://apt.postgresql.org/pub/repos/apt bullseye-pgdg main" > /etc/apt/sources.list.d/pgdg.list
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -
RUN apt-get update
RUN apt-get install -y postgresql-client-14

WORKDIR /app

RUN git clone --recursive --single-branch --branch ${LNBITS_BRANCH} -c advice.detachedHead=false \
    https://github.com/lnbits/lnbits . \
    && test `git rev-parse HEAD` = ${LNBITS_COMMIT_HASH} || exit 1 
    

RUN mkdir data

RUN poetry install --only main

ENV LNBITS_PORT="5000"
ENV LNBITS_HOST="0.0.0.0"

EXPOSE 5000

# Expose default data directory as VOLUME
VOLUME ["/app"]

CMD ["sh", "-c", "poetry run lnbits --port $LNBITS_PORT --host $LNBITS_HOST"]
