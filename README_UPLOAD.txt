aiTeaching Netlify deployment upload bundle v4 — runtime path fix

Upload package.json, netlify.toml, README_UPLOAD.txt, and every payload.partNN file to the ROOT of the existing GitHub repository. Replace the previous payload.part00 through payload.part05 files with the matching files from this bundle; do not mix old and new parts.
The payload parts are sequential pieces of one ZIP archive. Keep every part together. Netlify build concatenates payload.part* in filename order and extracts the application and question data.
This v4 fixes the Netlify CommonJS bundle crash by removing import.meta.url from the MCP function's data-directory resolution.
Do not upload the original Excel workbook or Firebase credentials.
The answer key remains inside the payload. Authentication, durable exam storage, and end-to-end MCP testing are still required before real student use.
