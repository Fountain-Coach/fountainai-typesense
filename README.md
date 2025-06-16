# fountainai-typesense

This repository provides a custom containerized Typesense service, preconfigured for use within the FountainAI ecosystem.

## Purpose

- Hosted under `ghcr.io/fountain-coach/fountainai-typesense`
- Used in `fountainai-stack.yml` to provide internal semantic indexing
- Allows future baking of schema, collections, and development defaults

## Image Usage

```yaml
typesense:
  image: ghcr.io/fountain-coach/fountainai-typesense:latest
  command: "--data-dir /data --api-key=xyz"
  ports:
    - "8108:8108"
  volumes:
    - typesense_data:/data
  environment:
    - TYPESENSE_API_KEY=xyz
```

## Status

This image is currently based on `typesense/typesense:0.24.1` and adds no schema or customization yet. Future versions may preload schema for faster onboarding.

## License

MIT License.
