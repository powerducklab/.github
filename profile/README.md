# PowerDuck

**Local-first OpenAPI 3.2 workbench.** Open, edit, and validate OpenAPI specs on your machine — then auto-generate API debug UIs, MCP servers, and documentation from a single source of truth.

[Website](https://www.powerduck.com) &nbsp;·&nbsp; [Documentation](https://www.powerduck.com/docs/) &nbsp;·&nbsp; [Live Demos](https://www.powerduck.com/demo/)

---

## What PowerDuck Does

PowerDuck is built around a simple idea: your OpenAPI document is the single source of truth. Everything else — debugging, mocking, MCP exposure, docs — should be generated from it, not maintained separately.

| Capability | Description |
|---|---|
| **Open & Validate** | Load any Swagger 2.0 / OpenAPI 3.0 / 3.1 / 3.2 file. Auto-upgrade and validate to OpenAPI 3.2 with machine-readable error codes. |
| **Spec Editing** | Edit YAML/JSON with real-time validation, circular-reference detection, and zero input mutation. |
| **API Debug UI** | Auto-generate a request debugger from your spec. HTTP, SSE, and WebSocket support with response write-back. |
| **MCP Server** | Expose any OpenAPI API as a Model Context Protocol server with Tools, Prompts, Resources, and an admin Web UI. |
| **Code Generation** | Generate runnable HTTP request code in 21 languages and 41 client combinations — browser-compatible, zero dependencies. |
| **API Documentation** | Generate clean, interactive API reference documentation from your spec. |

---

## Open-Source Libraries

PowerDuck's workbench is powered by a suite of standalone, production-grade libraries. Use them individually in your own projects, or together as the full workbench.

### OpenAPI Toolchain

| Package | Version | Description |
|---|---|---|
| [`@powerduck/openapi-parser`](https://www.npmjs.com/package/@powerduck/openapi-parser) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-parser)](https://www.npmjs.com/package/@powerduck/openapi-parser) | Upgrade any Swagger 2.0 / OpenAPI 3.0 / 3.1 / 3.2 document to a validated OpenAPI 3.2 document. Zero input mutation, machine-readable error codes, circular-reference guard, dual ESM/CJS builds. |
| [`@powerduck/openapi-codegen`](https://www.npmjs.com/package/@powerduck/openapi-codegen) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-codegen)](https://www.npmjs.com/package/@powerduck/openapi-codegen) | Generate runnable HTTP request examples from OpenAPI documents. 21 languages, 41 client combinations, browser-compatible, zero runtime dependencies. |
| [`@powerduck/x-to-openapi`](https://www.npmjs.com/package/@powerduck/x-to-openapi) | [![npm](https://img.shields.io/npm/v/@powerduck/x-to-openapi)](https://www.npmjs.com/package/@powerduck/x-to-openapi) | Extensible production-grade X-to-OpenAPI 3.2 conversion framework. Convert curl commands and Postman collections to OpenAPI 3.2 documents. |
| [`@powerduck/openapi-request`](https://www.npmjs.com/package/@powerduck/openapi-request) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-request)](https://www.npmjs.com/package/@powerduck/openapi-request) | OpenAPI 3.2 collection debugger with HTTP, SSE, and WebSocket support, plus response write-back. |
| [`@powerduck/openapi-cli`](https://www.npmjs.com/package/@powerduck/openapi-cli) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-cli)](https://www.npmjs.com/package/@powerduck/openapi-cli) | CI-ready CLI for batch-testing OpenAPI documents across HTTP, SSE, WebSocket, GraphQL, gRPC, and MCP. |
| [`@powerduck/openapi-mcp-server`](https://www.npmjs.com/package/@powerduck/openapi-mcp-server) | [![npm](https://img.shields.io/npm/v/@powerduck/openapi-mcp-server)](https://www.npmjs.com/package/@powerduck/openapi-mcp-server) | Production-oriented OpenAPI to MCP server library with Tools, Prompts, Resources, Web UI, and admin runtime. |

### Editor & Config Tools

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
npm install @powerduck/openapi-mcp-server
```

```ts
import { upgradeOasTo32, isOpenApiUpgradeError } from "@powerduck/openapi-parser";
import { generate } from "@powerduck/openapi-codegen";

// 1. Upgrade any Swagger 2.0 / OpenAPI 3.x document to validated 3.2
let document: Awaited<ReturnType<typeof upgradeOasTo32>>;
try {
  document = await upgradeOasTo32(openApiDoc);
} catch (error) {
  if (isOpenApiUpgradeError(error)) {
    console.error(`Upgrade failed [${error.code}]:`, error.message);
    console.error("Issues:", error.issues);
  } else {
    console.error("Unexpected error:", error);
  }
  process.exit(1);
}

// 2. Generate a runnable HTTP request for any operation
const code = generate({
  document,
  path: "/users/{id}",
  method: "get",
  language: "python",
  client: "requests",
});

console.log(code);
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
