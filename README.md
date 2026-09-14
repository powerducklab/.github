# PowerDuck

Open-source developer tools for API-first workflows. We build production-grade libraries for OpenAPI document processing, code generation, Markdown editing, and configuration patching.

[Website](https://www.powerduck.com) &nbsp;·&nbsp; [Documentation](https://www.powerduck.com/docs/) &nbsp;·&nbsp; [Live Demos](https://www.powerduck.com/demo/)

---

## OpenAPI Toolchain

A complete suite of libraries for working with OpenAPI 3.2 documents — from parsing and validation to code generation, request debugging, and MCP server exposure.

| Package | Version | Description |
|---|---|---|
| [`@powerduck/openapi-parser`](https://www.npmjs.com/package/@powerduck/openapi-parser) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-parser)](https://www.npmjs.com/package/@powerduck/openapi-parser) | Upgrade any Swagger 2.0 / OpenAPI 3.0 / 3.1 / 3.2 document to a validated OpenAPI 3.2 document. Zero input mutation, machine-readable error codes, circular-reference guard, dual ESM/CJS builds. |
| [`@powerduck/openapi-codegen`](https://www.npmjs.com/package/@powerduck/openapi-codegen) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-codegen)](https://www.npmjs.com/package/@powerduck/openapi-codegen) | Generate runnable HTTP request examples from OpenAPI documents. 21 languages, 41 client combinations, browser-compatible, zero runtime dependencies. |
| [`@powerduck/x-to-openapi`](https://www.npmjs.com/package/@powerduck/x-to-openapi) | [![npm](https://img.shields.io/npm/v/@powerduck/x-to-openapi)](https://www.npmjs.com/package/@powerduck/x-to-openapi) | Extensible production-grade X-to-OpenAPI 3.2 conversion framework. Convert curl commands and Postman collections to OpenAPI 3.2 documents. |
| [`@powerduck/openapi-request`](https://www.npmjs.com/package/@powerduck/openapi-request) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-request)](https://www.npmjs.com/package/@powerduck/openapi-request) | OpenAPI 3.2 collection debugger with HTTP, SSE, and WebSocket support, plus response write-back. |
| [`@powerduck/openapi-cli`](https://www.npmjs.com/package/@powerduck/openapi-cli) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-cli)](https://www.npmjs.com/package/@powerduck/openapi-cli) | CI-ready CLI for batch-testing OpenAPI documents across HTTP, SSE, WebSocket, GraphQL, gRPC, and MCP. |
| [`@powerduck/openapi-mcp-server`](https://www.npmjs.com/package/@powerduck/openapi-mcp-server) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-mcp-server)](https://www.npmjs.com/package/@powerduck/openapi-mcp-server) | Production-oriented OpenAPI to MCP server library with Tools, Prompts, Resources, Web UI, and admin runtime. |

## Editor & Config Tools

| Package | Version | Description |
|---|---|---|
| [`@powerduck/md-editor`](https://www.npmjs.com/package/@powerduck/md-editor) | [![npm](https://img.shields.io/npm/v/@powerduck/md-editor)](https://www.npmjs.com/package/@powerduck/md-editor) | High-performance embeddable Markdown editor. KaTeX math, Markmap mindmaps, highlight.js code blocks, admonition blocks, rich toolbar, image upload hooks, block-level incremental rendering. Simple and complex modes, light/dark themes. |
| [`@powerduck/conf-patch`](https://www.npmjs.com/package/@powerduck/conf-patch) | [![npm](https://img.shields.io/npm/v/@powerduck/conf-patch)](https://www.npmjs.com/package/@powerduck/conf-patch) | Two-layer configuration editor. Pure core for patching JSON/JSONC/YAML strings (browser-safe), plus file layer with atomic writes and locking for Node.js/Electron. RFC 6902 JSON Patch, comment and formatting preservation. |

---

## Quick Start

```bash
# Install any package from npm
npm install @powerduck/openapi-parser
npm install @powerduck/openapi-codegen
npm install @powerduck/md-editor
```

```ts
import { parse } from "@powerduck/openapi-parser";

// Upgrade and validate any OpenAPI document to 3.2
const result = parse(openApiDoc);
if (result.valid) {
  console.log("Valid OpenAPI 3.2:", result.document);
} else {
  console.error("Validation errors:", result.errors);
}
```

## Live Demos

Try all libraries in the browser — no signup required:

- [OpenAPI Codegen Playground](https://www.powerduck.com/demo/openapi-codegen)
- [cURL to OpenAPI Converter](https://www.powerduck.com/demo/x-to-openapi)
- [Config Patch Editor](https://www.powerduck.com/demo/conf-patch)
- [Markdown Editor](https://www.powerduck.com/demo/md-editor)

## License

All packages are released under the [MIT License](https://opensource.org/licenses/MIT).

---

<p align="center">
  <sub>Built by <strong>POWERDUCK LIMITED</strong></sub>
</p>
