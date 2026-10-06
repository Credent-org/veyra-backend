# Veyra Backend Services

Backend API server, WebSocket signal feeds, Model Context Protocol (MCP) server, and forensic audit bridge services for the Veyra protocol.

## Architecture

```text
veyra-backend/
├── mcp-server/                # Model Context Protocol (MCP) server
└── services/
    ├── express-api/           # Express x402 payment API service
    ├── ws-signals/            # Resilient WebSocket signal stream handler
    ├── audit-forensic-bridge/ # Attestation & forensic audit exporter
    └── sdp-audit-bridge/      # SDP Horizon anchor verification bridge
```

## Services

### 1. Express x402 API (`services/express-api`)
Monetized HTTP service using the Veyra x402 payment protocol.

### 2. WebSocket Signal Stream (`services/ws-signals`)
Resilient WebSocket listener connecting to Veyra signal engine with exponential reconnect backoff.

### 3. MCP Server (`mcp-server`)
Live Model Context Protocol integration for AI agents and LLM tools.

### 4. Audit Bridges (`services/audit-forensic-bridge` & `services/sdp-audit-bridge`)
Cryptographic audit trail and SDP Horizon proof verification services.

## Setup & Running

```bash
# Start MCP server
cd mcp-server && npm install && npm run build

# Run Express API
cd services/express-api && npm install && npm run dev
```

## Environment Variables
Copy `.env.example` in each service subfolder and set:
- `VEYRA_API_KEY`
- `VEYRA_API_URL`
- `STELLAR_SECRET_KEY`

## License
Apache 2.0 — Veyra Protocol
