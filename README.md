# GPU.ai OpenAPI Specification

The official [OpenAPI 3.1](https://spec.openapis.org/oas/v3.1.0) specification for the
**GPU.ai public REST API** — the same API behind the dashboard and the `gpuctl` CLI.
List GPU types, provision instances, manage SSH keys and webhooks, and pull usage data.

- **Spec:** [`openapi.json`](./openapi.json) — OpenAPI 3.1, version `1.0.0`
- **Guides & quickstart:** https://demo.gpu.ai/docs/api
- **Live spec endpoint:** https://api.demo.gpu.ai/v1/openapi.json

> **Read-only mirror.** This file is synced automatically from the spec the live API
> serves — see [`.github/workflows/sync.yml`](./.github/workflows/sync.yml). Don't edit
> it by hand; changes are overwritten on the next sync.

## Base URLs

| Environment | Base URL | Spec |
|-------------|----------|------|
| Demo | `https://api.demo.gpu.ai/v1` | https://api.demo.gpu.ai/v1/openapi.json |
| Production | `https://api.gpu.ai/v1` | _lights up with the v1.0 production launch_ |

## Using the spec

**Generate a client SDK** (any language `openapi-generator` supports):

```bash
npx @openapitools/openapi-generator-cli generate \
  -i https://raw.githubusercontent.com/gpuai-dev/openapi/main/openapi.json \
  -g python -o ./gpuai-sdk
```

**Preview interactive docs** locally:

```bash
npx @redocly/cli preview-docs openapi.json
```

**Import** `openapi.json` into Postman, Insomnia, or Stoplight to explore the API
interactively.

## Authentication

Write endpoints require a Bearer API key (`gpuai_live_…`) minted from the dashboard or
via `gpuctl auth login`. Catalog endpoints (e.g. `GET /v1/gpu-types`) are public. See
the [quickstart](https://demo.gpu.ai/docs/api) for details.

## Questions

This repo is a mirror — for API support, contact **support@gpu.ai**.
