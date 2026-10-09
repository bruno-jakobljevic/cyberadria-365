# CyberAdria

A daily cybersecurity challenge with 365 original questions inspired by Security+ and BTL1 topics.

## Features
- One daily question, changing at local midnight
- Four answer choices with correct/incorrect visual feedback
- An explanation of at most three sentences after answering
- Monospace typography and a responsive dark interface
- No practice mode, category selector, score counters, or progress storage
- No backend, external fonts, or libraries

## Update an existing installation
Replace `index.html` and `README.md` with the files in this update.
Keep your existing `questions.json`, `manifest.json`, `LICENSE.txt`, and any `CNAME` file.
The update archive intentionally does not include the question bank or domain configuration.

## Run locally
```bash
python3 -m http.server 8000
```
Open http://localhost:8000.

## Deploy
Keep `index.html` and `questions.json` together in your GitHub Pages publishing folder.
Commit the updated files to your existing publishing branch. Keep the existing custom-domain configuration for cyberadria.eu.

## Question behavior
The question uses the same deterministic local-calendar-day selection as the previous demo, cycling through the bank every 365 days. The visible label is `Question-296`, for example, while the original JSON ID stays unchanged. After an answer, the correct choice has a green border and check mark; an incorrect selected choice has a red border and cross. Only the explanation appears below the choices, without a repeated answer or verdict.

Answers are not saved. Refreshing lets you retry the same daily question. Different local time zones can be on different daily questions. An open tab refreshes its challenge shortly after midnight or when it becomes visible again.

## Customize
Edit the existing `questions.json` to change questions and explanations. Keep explanations to three sentences or fewer; the page also limits the displayed explanation to its first three detected sentences. Edit the CSS in `index.html` to change the appearance.

## Disclaimer
Unofficial, AI-authored practice material, not actual exam questions or certification-provider-endorsed training. Review accuracy before relying on it. Answers are visible in the JSON, so this is a learning game rather than a secure assessment.

## License
MIT — see the existing `LICENSE.txt`.
