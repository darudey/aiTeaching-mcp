aiTeaching Netlify deployment upload bundle v8 — rawHeaders synchronization fix

Replace package.json, netlify.toml, README_UPLOAD.txt, and ALL six payload.partNN files in the ROOT of the existing GitHub repository. Do not mix payload versions.

Root cause found from V6 diagnostics and the SDK's Node adapter: Netlify/serverless-http populated req.headers but left req.rawHeaders without Content-Type. The MCP SDK's Node adapter (@hono/node-server) constructs its Web Request headers from req.rawHeaders, so the transport did not see application/json and returned 415.

V8 synchronizes Content-Type (and missing Accept/Host headers) into req.rawHeaders before calling the MCP transport. It retains V7's Buffer JSON parsing and all question-bank data.

This bundle contains the private answer key. Keep the GitHub repository private. Do not upload the original Excel workbook or Firebase credentials. Authentication and full end-to-end testing are still required before real student use.
