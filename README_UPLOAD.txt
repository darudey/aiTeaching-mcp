aiTeaching Netlify deployment upload bundle v3

Upload package.json, netlify.toml, README_UPLOAD.txt, and every payload.partNN file to the ROOT of a NEW PRIVATE GitHub repository.
The payload parts are sequential pieces of one ZIP archive. Keep every part together.
Netlify build concatenates payload.part* in filename order and extracts the application and question data.
Do not upload the original Excel workbook or Firebase credentials.
Keep this repository private: the payload includes the private answer key.
This remains a prototype; authentication, durable exam storage, and end-to-end MCP testing are still required before real student use.
