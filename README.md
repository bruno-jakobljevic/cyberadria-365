# Cyber Daily

A static cybersecurity quiz with **365** original practice questions covering Security+ and BTL1-related topics.

## Features
- Four choices per question with answer explanations
- Practice mode and a daily question
- Category filtering
- Progress saved locally in your browser
- No backend or external dependencies

## Run Locally
```bash
python3 -m http.server 8000
```
Open http://localhost:8000.

## Deploy
Upload the files to your GitHub repository, then select:

Settings → Pages → Deploy from a branch → main → / (root) → Save

## Customize
Edit `questions.json` to update the questions. Each question includes four choices, a zero-based `correctIndex`, and an explanation.

## Disclaimer
Unofficial, AI-authored study material—not actual exam questions. Review accuracy before relying on it for certification preparation. Answers are visible in the source, so this is a learning game rather than a secure assessment.

## License
MIT — see `LICENSE.txt`.
