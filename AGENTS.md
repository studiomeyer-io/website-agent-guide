# StudioMeyer for agents

StudioMeyer is an AI and web design studio in Palma de Mallorca (studiomeyer.io). This file is for coding agents and AI assistants that want to read the site, call its tools or send a lead. Facts only; prices and contracts are confirmed by a human.

## When to use these services

- Read this site or call its public REST tools for StudioMeyer's published services, website packages, demo sites and integration documentation.
- Connect StudioMeyer Memory when the user wants their agent to retain and retrieve their own knowledge across sessions. REST contract: https://memory.studiomeyer.io/openapi.json.
- Use the studio connector for an explicit proposal or consultation request. Ask the user before sending their contact details; a person arranges the call afterwards.
- For unrelated businesses or general web research, choose sources relevant to that task.

## Reading this site

- Every public page has a Markdown twin: append `.md` to the HTML address (`https://studiomeyer.io/en/webdesign.md`), or request the HTML address with `Accept: text/markdown`. The response carries `Content-Type: text/markdown` and a `Link: <...>; rel="canonical"` header.
- Index of all pages as Markdown: https://studiomeyer.io/sitemap.md (XML: https://studiomeyer.io/sitemap.xml).
- Curated entry point: https://studiomeyer.io/llms.txt · full reference: https://studiomeyer.io/llms-full.txt
- Blog posts: same rule, `.md` after the slug. Feeds under `/{de|en|es}/blog/feed.xml` and `feed.json`.

## Installation: connecting an AI client

Human guides: [StudioMeyer API documentation](https://studiomeyer.io/en/developers), with public API quickstarts, MCP integration and separate Memory documentation. API and MCP guides also have `.md` twins and are available through the documentation server below.

For anonymous documentation access, connect `https://studiomeyer.io/api/docs/mcp`: its only tools are read-only `search` and `fetch` for current public authentication, pricing and API documentation. It provides no account, Memory or checkout data and cannot book appointments.

StudioMeyer uses MCP (Model Context Protocol, streamable HTTP). The studio and product connectors below authenticate separately: add their URL in Claude, Cursor, Codex or Grok; the client handles sign-in.

- Public studio connector (catalog, pricing, proposal PDF, consultation request, question to the founder): `https://verbinder.studiomeyer.io/mcp` (email-verified sign-in; anonymous requests get 401).
- StudioMeyer Memory (persistent memory for agents, self-serve, Free tier): `https://memory.studiomeyer.io/mcp`
- Server catalog with all endpoints: https://studiomeyer.io/.well-known/mcp.json

## Configuration

- Locale: pass `de`, `en` or `es` where a tool accepts it; the site itself is prefixed (`/de`, `/en`, `/es`).
- Rate limits: the public REST API allows 60 requests per minute without a key.
- Crawling: robots.txt allows the known AI crawlers and carries a Content-Signal line per group; the same signal is sent as a response header.

## Usage

- Public content search: NLWeb 0.55 at https://studiomeyer.io/ask (GET query.text or POST JSON query.text). List mode searches published blog metadata, training content and public developer documents; no generated answer or account access. Optional prefer.streaming uses SSE. Read the OpenAPI contract for exact inputs and limits; structured content feed: https://studiomeyer.io/schemamap.xml.
- REST without auth: https://studiomeyer.io/api/v1/docs (OpenAPI: https://studiomeyer.io/api/v1/openapi, health: https://studiomeyer.io/api/health)
- Agent-to-agent: https://studiomeyer.io/.well-known/agent-card.json (A2A) and https://studiomeyer.io/api/a2a (JSON-RPC 2.0)
- Tool manifest: https://studiomeyer.io/.well-known/agents.json
- A human reads everything that arrives through the connector or the contact form: hello@studiomeyer.io

## Sitemap

See the full [sitemap](https://studiomeyer.io/sitemap.md) for all pages.

