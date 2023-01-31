FROM python:3.7-alpine3.14

WORKDIR /home

COPY resources/docs docs
COPY ../mkdocs.yml .
COPY ../requirements .

RUN pip install -r requirements

RUN mkdocs build
# site dir generated with previous cmd
WORKDIR /home/site

ENTRYPOINT ["python3", "-m", "http.server", "8000"]