# Unduck

DuckDuckGo's bang redirects are too slow. Add the following URL as a custom search engine to your browser. Enables all of DuckDuckGo's bangs to work, but much faster.

```
https://unduck.link?q=%s
```

## Running locally via Docker

Using Docker Compose:

```yaml
version: '3.8'

services:
  unduck:
    image: ghcr.io/myrenic/unduck:latest
    restart: unless-stopped
    ports:
      - "1234:80"
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost"]
      interval: 30s
      timeout: 10s
      retries: 3
```

Or run manually:

```sh
# run
docker run --rm -p 1234:80 ghcr.io/myrenic/unduck:latest
```

