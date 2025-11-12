# MCP Agent Demo

This demo is built with Java 25, Spring Boot 3.5.6, Spring AI MCP (1.1.0-M3) and WebFlux, exposing two independent MCP servers and a single agent that connects to them.

The agent exposes a REST API with two endpoints: one that lists all available tools from each MCP, and another that accepts a prompt, selects the most relevant tool automatically, executes it, and returns the result.

On top of that, it includes a frontend in Angular 20.3.10 that consumes the agent API and renders dynamic visualizations using Chart.js and Angular Material CDK Table.

---

## 🐳 Run with Docker

```bash
docker compose up --build
```

---

Frontend url:

```
http://localhost
```

Exposed Endpoints:

```
GET http://localhost:8086/health
POST http://localhost:8086/agent - Body: { "prompt": "..." }
```

---

VS Code Configuration for both MCP servers:

```json
{
  "servers": {
    "sales-mcp": {
      "type": "sse",
      "url": "http://localhost:8084/mcp"
    },
    "stock-mcp": {
      "type": "sse",
      "url": "http://localhost:8085/mcp"
    }
  }
}
```

---

## 🪪 License

MIT
