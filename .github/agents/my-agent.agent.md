---
# Fill in the fields below to create a basic custom agent for your repository.
# The Copilot CLI can be used for local testing: https://gh.io/customagents/cli
# To make this agent available, merge this file into the default repository branch.
# For format details, see: https://gh.io/customagents/config

name:
description:
---

# My Agent

Describe what your Act as a Principal Web3 Core Architect. Build a Node.js TypeScript application that acts as a "Factory Agent" for creating x402 Session Management Middleware, explicitly featuring native integration with the official x402 Bazaar Discovery Extension (`@x402/extensions/bazaar`).

The goal is to provide a session layer that prevents repetitive wallet signatures while automatically indexing the generated endpoints to the open agent directory.

Implement the following modular architecture:

1. Package Configuration & Imports:
   - Import necessary core modules from `@x402/express`, `@x402/core`, `@x402/evm`, and `@x402/extensions/bazaar`.

2. The Session Registry Database Structure:
   - Define a strongly typed session cache (in-memory map) tracking `sessionId`, `clientWalletAddress`, `maxBudgetLimit` (USDC), `currentSpentAmount`, and `expirationTimestamp`.

3. Endpoint 1: The Session Handshake with Bazaar Metadata (`POST /api/x402/session/init`):
   - Intercept this route using standard x402 402 challenges if payment headers are absent.
   - Configure the Bazaar metadata block for this route inside the route configuration, specifying:
     * title: "x402 Pre-Authorized Session Factory"
     * description: "Exchange an initial bulk USDC payment on Base for a temporary cryptographically signed session token to enable frictionless micro-payments."
     * schema.properties.input: A JSON schema declaring an optional parameter for initial session funding limit request.
     * schema.properties.output: A JSON schema declaring fields for `sessionId`, `expiresAt`, and `allottedBudget`.
   - Ensure that upon successful transaction settlement, the paymentPayload.resource is accurately bound so the CDP Facilitator catalogs the service.

4. The Session-Checking Middleware Logic:
   - Create `verifyX402Session(req, res, next)`.
   - Extract the `X-X402-Session-Token` custom header.
   - If missing or exhausted, return a single-use standard fallback HTTP 402 challenge.
   - If a valid session token is found, compare the endpoint costs locally, deduct the fractional amount from the session cache, attach validation flags, and call `next()` immediately without sending an on-chain verification prompt.

5. Dynamic Marketplace Routing Example:
   - Set up an Express application instance demonstrating two protected utility routes (e.g., `/api/v1/fast-scan` and `/api/v1/deep-analyze`).
   - For each route, explicitly map its own unique Bazaar metadata schemas describing the payload inputs and structured JSON responses so it registers as a separate, distinct Bazaar entry upon its first settlement.

Provide a production-ready, fully commented TypeScript code architecture, showing clean error handling and semantic schema shapes.
agent does here.
