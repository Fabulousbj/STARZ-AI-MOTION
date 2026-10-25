# Nova Motion — Ultimate Kling AI Video Panel

A responsive public-facing Flask website for text-to-video and image-to-video requests through the official Kling AI developer API.

## Included
- Dark, responsive AI studio UI
- Text-to-video form
- Image-to-video form (JPG/PNG upload)
- Duration, resolution and aspect-ratio controls
- API connection indicator
- Task status polling and video preview when returned by the API
- Environment-variable secret configuration
- Render deployment template

## Important
This is a starter project, not a deployed public website. You must deploy it to a hosting provider and configure a valid Kling AI API key. API access and generation may cost money. Do not put the API key in frontend JavaScript or commit it to Git.

The API payloads follow Kling's published documentation, but provider access, model availability, authentication, task response shape, image input rules, and supported settings can vary by account/version. Test with a low-cost request before sharing publicly.

## Run locally
1. Install Python 3.10+.
2. In this folder, run:
   `python -m venv .venv`
3. Activate the environment:
   - Windows PowerShell: `.venv\\Scripts\\Activate.ps1`
   - macOS/Linux: `source .venv/bin/activate`
4. Install packages:
   `pip install -r requirements.txt`
5. Set your API key in the environment (do not paste it into code):
   - Windows PowerShell: `$env:KLING_API_KEY="your-key"`
   - macOS/Linux: `export KLING_API_KEY="your-key"`
6. Start:
   `python app.py`
7. Open `http://127.0.0.1:5000`.

## Deploy publicly with Render
1. Create a private Git repository and upload the project files.
2. Create a new web service on Render from that repository.
3. Render can use `render.yaml`; otherwise set build command `pip install -r requirements.txt` and start command `gunicorn app:app`.
4. Add `KLING_API_KEY` as a secret environment variable in the service dashboard.
5. Deploy and test.

## Before opening it to the public
This starter does not yet include user accounts, per-user quotas, payment handling, a database-backed history, admin authentication, abuse prevention, or usage metering. Add these before inviting public users, otherwise visitors could consume your API credits. Also configure upload limits, rate limiting, authentication, moderation, privacy notice, and retention policy.
