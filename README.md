# Frontier Research Roadmaps

Self-study syllabi that take a university student from zero to following frontier research — currently **AI**, **computer science**, **semiconductors** and **bio** — each with a frontier section refreshed every week. English by default, with a Korean toggle.

대학생이 처음부터 최전선 연구를 따라갈 수 있는 수준까지 가는 자기주도 학습 노선도입니다. 현재 AI, 컴퓨터 과학, 반도체, 바이오 네 분야가 있고, 분야마다 최전선 구간이 매주 갱신됩니다. 영어(기본)와 한국어를 전환할 수 있습니다.

## Structure (AI route)

| Stage | Content |
|---|---|
| 0–4 (core) | Tools → Math → Machine learning → Deep learning → Transformers & foundation models |
| 5 (tracks) | A Post-training & reasoning · B Vision, audio & multimodal · C Generative models · D RL, agents & robotics · E Interpretability & safety · F ML systems & efficiency · G AI for science & graph learning · H Theory of learning |
| 6 | Entering research |
| Frontier | 6–8 new papers, talks and reports across AI, updated every Monday (KST) |

Each stage and track lists key concepts, the exact scope of each resource with estimated hours, a hands-on project, an exit criterion and common mistakes.

The computer science route runs programming → discrete math & probability → algorithms & data structures → computer systems (Nand2Tetris, CS:APP, OSTEP, xv6, CS144, Crafting Interpreters, CMU 15-445) → 9 tracks (distributed systems, security & cryptography, PL & compilers, databases, theory, networking, graphics/vision/HCI, quantum computing, software engineering) → research.

The semiconductor route runs tools → math → physics & materials → devices, circuits & digital systems → 5 tracks (devices & materials, fabrication & lithography, chip design & EDA, architecture & AI hardware, packaging & industry) → research. The bio route runs tools → math & statistics → chemistry → molecular & cell biology → 5 tracks (genomics, protein structure & design, gene editing & synthetic biology, drug discovery, neuroscience) → research.

## Files

- `index.html` — the page (no build step); switch fields with the tabs or `#f-ai`, `#f-cs`, `#f-semiconductors`, `#f-bio`
- `data/fields.json` — list of fields and their data files
- `data/curriculum.json` — AI route: stages, tracks, resources, coverage, sources and experience pathways
- `data/fields/cs.json`, `data/fields/semiconductors.json`, `data/fields/bio.json` — other routes, same format
- `data/frontier.json`, `data/frontier-cs.json`, `data/frontier-semiconductors.json`, `data/frontier-bio.json` — weekly frontier items (`weeks[0]` is the current week; the last 8 weeks are kept)

Each route also includes a reality check: listed study hours, and what the roadmap does and does not give you.

Checkmarks are stored in your browser only (`localStorage`).

## Run locally

The page loads its data with `fetch`, so serve the folder instead of opening the file directly:

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Data format

Resource entry in `curriculum.json`:

```
[title, url, kind, scope_en, scope_ko, hours, note_en, note_ko, url_ko?]
```

`kind` is one of `course`, `book`, `paper`, `code`, `article`, `video`, `practice`.

Frontier item in `frontier.json`:

```json
{"type_en": "Paper", "type_ko": "논문", "stage": 5, "title": "...", "url": "...", "why_en": "...", "why_ko": "..."}
```

`stage`: 0 = any stage, 4 = after stage 4, 5 = while in the matching track, 6 = research stage.
