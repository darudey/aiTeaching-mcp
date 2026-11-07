aiTeaching Netlify deployment upload bundle V2

Upload package.json, netlify.toml, README_UPLOAD.txt, and every payload.partNN file to the ROOT of a NEW PRIVATE GitHub repository (or replace all matching files in a dedicated existing repository). Keep every payload part from this V2 bundle together; do not mix versions.

Netlify build concatenates payload.part* in filename order and extracts the application and private question data. Do not upload the original Excel workbook or Firebase service-account JSON. Keep this repository private: it contains the private answer key.

V2 MCP tools:
- list_chapters
- list_subtopics
- start_exam (exact subtopic match by default; optional contains mode)
- get_current_question
- submit_answer
- submit_answers (batch answers; null means skip)
- skip_question
- get_exam_result
- get_exam_review
- resume_exam
- get_performance_analytics (requires Firestore)

Required Netlify environment variables:
- SESSION_SECRET: long random secret, at least 32 random bytes.
- FIREBASE_PROJECT_ID: Firebase project ID.
- FIREBASE_CLIENT_EMAIL: service-account client_email.
- FIREBASE_PRIVATE_KEY: service-account private_key, with literal \n line breaks (Netlify environment variable supports multiline values; if pasting escaped newlines use \n).
Optional:
- MCP_API_KEY: require Authorization: Bearer <key> on MCP requests.
- FIREBASE_EXAMS_COLLECTION: defaults to exam_sessions.

Without Firebase variables, the function uses temporary in-memory sessions for basic testing only; sessions are not durable across serverless invocations. Firestore persistence and performance analytics require all three FIREBASE_* variables. Public Firestore client rules should remain closed; this backend uses Firebase Admin SDK.

Important: do not use a service-account key that has been shared in a chat or repository. Revoke exposed keys and generate a fresh key before configuring Netlify. Never commit credentials to GitHub.

The existing question images and private answer key are included in the payload. Keep this repository private.
