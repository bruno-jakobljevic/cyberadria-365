# 365 Cybersecurity Questions

A dependency-free static quiz and 365 original English-language practice questions.

## Included files
- `index.html`: responsive practice and daily-question game.
- `questions.json`: an array of 365 question objects.
- `manifest.json`: scope, public topic references, counts, and limitations.
- `LICENSE.txt`: permission to reuse the original content and demo.

## GitHub Pages deployment
1. Extract the archive.
2. Put all included files in the repository root (or together in your chosen Pages publishing folder).
3. In repository Settings → Pages, select an available branch-based publishing source and the folder containing these files. If the repository already deploys with Actions, include the files in that deployment instead.
4. Open the resulting Pages site. All asset paths are relative, so the demo works under a project subpath.

For local testing, run `python3 -m http.server 8000` in the extracted folder and open the local HTTP server in your browser. Do not rely on opening index.html directly from disk.

## Integrate with an existing game
```js
const response = await fetch('./questions.json');
if (!response.ok) throw new Error(`HTTP ${response.status}`);
const questions = await response.json();
const q = questions[0];
// Render q.question and q.choices using textContent.
// Compare the player's selected zero-based index with q.correctIndex.
// Reveal q.explanation only after answering.
```

Schema:
- `id`: stable ID within this bank.
- `category`: broad study category.
- `topic`: narrower study topic.
- `tracks`: broad topic relevance labels, not formal certification objective mappings.
- `question`: question text.
- `choices`: exactly four unique strings in stored display order.
- `correctIndex`: zero-based index, from 0 to 3.
- `explanation`: rationale for the correct answer.

If you shuffle choices, preserve the original answer association; do not keep the old correctIndex without remapping it.

## Game behavior
Practice uses shuffled queues within the chosen category. The next button appears after answering. Daily mode selects one question from the complete bank using the viewer's local calendar date, cycling every 365 days, not resetting each calendar year. Daily mode ignores the category filter. Progress is saved locally in the browser when localStorage is available; the first attempt for each question counts. Clear the `cyber365-results-v1` localStorage key to reset progress. There is no account, server, shared leaderboard, or cross-device synchronization.

## Editorial and certification limitations
These are newly authored practice items based on public topic coverage, not copies of paid questions or recalled certification exam items. The reference Security+ coverage is SY0-701 / V7, with supplementary AI-security questions. The bank is not weighted like an official exam and does not claim exhaustive objective coverage. BTL1 has a practical incident-response exam; multiple-choice practice is not a substitute for labs. Track labels describe relevance, not certification-provider endorsement. See manifest.json for the public topic references.

Each topic contributes four or five different prompts, so concepts recur intentionally. Distractors come from related topic pools. Some questions are straightforward recall, others use short operational scenarios. Some numeric event-ID and protocol questions are intentionally precise. IDs, total count, unique stems, choices, valid answer indices, and answer-position balance were checked programmatically. Subject accuracy and distractor quality have not received independent expert review. Review the content before publishing it as authoritative study material, and maintain it as tools and standards change.

This is a client-side learning game: anyone can inspect correct answers in the downloaded JSON. Obfuscation cannot make a static quiz a secure scored assessment.
