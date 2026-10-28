# truesource-demo-search

Demo product search for [TrueSource Viewer](https://github.com/nkuhn-vmw/truesource-viewer-hub-edition).

**Intentionally vulnerable demo. Do not deploy it, do not install from it.** It contains only
manifests and lock files, written by hand: the lock files have no integrity hashes, and the
versions named below are pinned on purpose so that the viewer has something to find.

A Flask search API over Elasticsearch, versions locked with uv.

| File | Pins | What the viewer should report |
|---|---|---|
| `uv.lock` | `flask` 1.1.2, `werkzeug` 1.0.1, `jinja2` 2.11.3, `requests` 2.25.1, `urllib3` 1.26.5, `certifi` 2020.12.5 | Known vulnerabilities |
| `compose.yaml` | `bitnami/elasticsearch:7.10.2`, `bitnami/kibana:7.10.2` | Elasticsearch 7.10 is past its end of life |
| `compose.yaml` | `bitnami/redis:6.2.6`, `bitnami/rabbitmq:3.8.9`, `bitnami/nginx:1.21.6` | Old images with newer TrueSource builds |
| `Dockerfile` | `python:3.10.0-slim` | An old Python 3.10 image |
