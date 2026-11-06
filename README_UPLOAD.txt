aiTeaching Netlify deployment upload bundle v7 — explicit JSON Buffer parsing

Upload/replace package.json, netlify.toml, README_UPLOAD.txt, and ALL six payload.partNN files in the ROOT of the existing GitHub repository. Do not mix payload versions.

V7 fixes the diagnostic finding from V6: Netlify/serverless-http exposed the POST body as a Buffer despite Content-Type being application/json. The function now explicitly decodes the Buffer as UTF-8 JSON, returns HTTP 400 for malformed JSON, and passes the parsed object to the MCP Streamable HTTP transport.

This bundle contains the private answer key. Keep the GitHub repository private. Do not upload the original Excel workbook or Firebase credentials. Authentication and full end-to-end testing are still required before real student use.
