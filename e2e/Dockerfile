FROM python:3.8

# Install poetry
ENV POETRY_VERSION=1.0.10
RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python
RUN ~/.poetry/bin/poetry --version

# Install dependencies
WORKDIR /code/e2e
COPY ./e2e/poetry.lock ./e2e/pyproject.toml /code/e2e/
RUN ~/.poetry/bin/poetry config virtualenvs.create false && ~/.poetry/bin/poetry install

# Copy code
COPY ./e2e /code/e2e

# Set command
CMD pytest
