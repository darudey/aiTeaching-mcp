aiTeaching Netlify deployment upload bundle v5 — MCP JSON content-type compatibility fix

Upload package.json, netlify.toml, README_UPLOAD.txt, and every payload.partNN file to the ROOT of the existing GitHub repository. Replace all six previous payload parts with the matching v5 files; do not mix versions.

The payload parts are sequential pieces of one ZIP archive. Keep every part together. Netlify concatenates payload.part* in filename order and extracts the application and question data.

v5 preserves the v4 CommonJS-safe data path resolution and restores the exact application/json request header after Express JSON parsing before forwarding POST requests to the MCP Streamable HTTP transport.

The payload contains the private answer key. Do not upload the original Excel workbook or Firebase credentials. Authentication, durable exam storage, and full end-to-end testing are still required before real student use.
