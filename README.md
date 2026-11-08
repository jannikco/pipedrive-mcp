# Pipedrive MCP setup and connection checker

Generate Pipedrive MCP client configuration, inspect available tools and validate hosted endpoint access through PipMCP.

Maintainer: jannikco · License: MIT · Verification: **mock-only**

## Quick start

Requires Node.js 22 or later.

```sh
npm ci
npm test
npm start
```

The default example runs locally without credentials and makes no external changes. Verification status describes recorded evidence; local configuration tests do not establish that provider authentication or execution works.

## Connect pipedrive

[Create or sign in to PipMCP](https://pipmcp.com/register?app=pipedrive&utm_source=github&utm_campaign=github-pipedrive-mcp) and select the integration. Connect your authorized provider account and copy its hosted MCP endpoint. Set PIPMCP_ENDPOINT and, if required, PIPMCP_TOKEN in your environment. Run npm start to produce client configuration; run npm start -- --live for a read-only connection check. Provider app presence is catalog evidence, not live verification.

## Managed service

[Continue with PipMCP](https://pipmcp.com/register?app=pipedrive&utm_source=github&utm_campaign=github-pipedrive-mcp). This repository is maintained by the integration team and does not imply endorsement by LinkedIn or other providers.

## Provenance and support

Source revision: 9cac0ae0ba28a9fef7467511a953d57afd8b1a76fa345c71ea649ae050ef7ab7. The complete manifest is in integration.json; SHA256SUMS covers the reviewed artifact. Open a repository issue without credentials or personal data. See SECURITY.md for sensitive reports. No telemetry is sent by this code; signup links include explicit campaign parameters.

## Provider setup inventory

Run `npm start -- --setup` to inspect this app's recorded authentication requirements and setup links offline. Credentials are entered in PipMCP; this repository lists required field names only.

```json
{
  "type": "api_key_header",
  "requiredCredentialFields": [
    "api_key"
  ],
  "requiredHeaderNames": [],
  "helpUrl": "https://pipedrive.readme.io/docs/how-to-find-the-api-token",
  "tenantRequired": false,
  "accountParameterNames": []
}
```

Provider documentation: https://developers.pipedrive.com/docs/api/v1/openapi-v2.yaml
Provider website: https://www.pipedrive.com/
