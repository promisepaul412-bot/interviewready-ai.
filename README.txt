INTERVIEWREADY AI — GEMINI + NETLIFY

1. You have already set GEMINI_API_KEY in your existing Netlify project under Project configuration > Environment variables, with Functions scope. Never add your key to these files.
2. Extract this ZIP. The project folder contains public/index.html, netlify/functions/interview.mjs, and netlify.toml.
3. RECOMMENDED: upload the contents of this project to a GitHub repository, then connect that repository to your existing Netlify site under Project configuration > Build & deploy > Continuous deployment. Set publish directory to public. Deploy.
4. ALTERNATIVE: install Node.js and Netlify CLI, open a terminal inside the extracted folder, run: npm install -g netlify-cli ; netlify login ; netlify link (choose existing InterviewReady site) ; netlify deploy --prod. This sends both website and functions.
5. Verify https://YOUR-SITE.netlify.app/.netlify/functions/interview in a browser. It should reply with JSON error Use POST and status 405. A 404 means the function has not been deployed.
6. Open your site and start an interview, answer with something specific, and test a follow-up.
7. Optional: set GEMINI_MODEL to a model available to your Gemini account if the default gemini-2.5-flash is unavailable.

IMPORTANT: Client-facing interface remains a single HTML file, but the secure Gemini gateway must be a separate server-side function. The HTML cannot safely contain an API key.

SAFETY: The backend includes input limits, origin check and a simple best-effort per-instance rate cap. This is not production-grade protection; Netlify functions run across multiple instances, so before inviting the public, configure durable/distributed rate limiting and abuse controls. Gemini may process responses; don't enter secrets or sensitive personal details.

ASSESSMENT: Interview follow-up questions are AI-generated, but the existing scores and targeted practice scoring are still heuristic/rule-based. Do not use them for hiring decisions.
