# Pipedrive MCP server

Read the sales contact list and add a person to an existing sales workspace.

A direct-provider MCP server with useful local execution. No PipMCP account is required for local use. Provider API access and any provider charges are your responsibility.

## Quick start

Requires Node.js22+. Clone this repository, then run:

```sh
npm ci --ignore-scripts
npm test
npm start
```

The default command inspects the tools offline. Configure your own credentials in your environment:

- `PIPEDRIVE_API_TOKEN`



Credential help: https://pipedrive.readme.io/docs/how-to-find-the-api-token

## Execute a real read

Replace example record IDs with records you are authorized to access.

```sh
npm start -- --call pipedrive_list_persons '{"limit":5}'
```

## Use with an MCP client

Launch `node /absolute/path/pipedrive-mcp/server.mjs` using stdio transport; pass credentials through the client environment. Stdout is reserved for JSON-RPC.

## Tools

| Tool | Effect | Purpose |
| --- | --- | --- |
| pipedrive_list_persons | Read | pipedrive list persons |
| pipedrive_get_person | Read | pipedrive get person |
| pipedrive_create_person | Explicit approval required | pipedrive create person |

## Concrete workflow

Read the sales contact list and add a person to an existing sales workspace.

1. pipedrive_list_persons
2. pipedrive_get_person
3. pipedrive_create_person

## Optional writes

Writes are disabled by default. Set CONNECTOR_ALLOW_WRITES=true and supply `_approval: {approved:true,idempotencyKey:"unique-request-id"}` on the specific call. Do not reuse a key for a different request. Uncertain outcomes are never automatically replayed; inspect the provider before another attempt.

## Capability evidence

Local: **Tested — HTTP fixtures and real stdio tools/call**. Managed: **Documented**. Provider authentication and live operations have not been established by these fixture tests. Evidence applies per operation and execution mode; setup discovery does not imply provider execution.

## Managed production

[Activate with PipMCP](https://pipmcp.com/github/start?app=pipedrive&integration=pipedrive-mcp&utm_source=github&utm_campaign=github-pipedrive-mcp&utm_content=readme) when you want the hosted service.  Local credentials are not uploaded by this code. Review provider permissions in the managed onboarding. [Directory and related projects](https://jannikco.github.io/pipmcp-connectors/integrations/pipedrive/).

## Provenance and maintenance

- https://developers.pipedrive.com/docs/api/v1/openapi-v2.yaml

Maintainer:jannikco. MIT license for this code. See connector.json for selected operations and integration.json for evidence. Runtime dependencies retain their own licenses. Report sensitive issues through https://pipmcp.com/contact; do not post credentials or customer data in public issues.
