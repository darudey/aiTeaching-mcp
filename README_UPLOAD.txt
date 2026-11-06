aiTeaching Netlify deployment upload bundle v6 — temporary request diagnostics

Replace package.json, netlify.toml, README_UPLOAD.txt, and ALL six payload.partNN files in the GitHub repository root. Do not mix payload versions.

This diagnostic build adds a temporary POST ?diag=1 response that reports only the Content-Type/Accept headers as seen by Express and whether Express parsed the JSON body. It never returns the request body, question content, images, or answer keys. Use it only to diagnose the persistent MCP 415 response.

After diagnostics, remove this temporary route and deploy the final MCP fix. The payload includes the private answer key. Do not upload the original Excel workbook or Firebase credentials.
