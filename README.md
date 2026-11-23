# AI Research Roadmap

A self-study syllabus that takes a university student from zero to doing AI research — with a frontier section refreshed every week. English by default, with a Korean toggle.

대학생이 처음부터 AI 연구를 할 수 있는 수준까지 가는 자기주도 학습 노선도입니다. 최전선 구간은 매주 갱신되며, 영어(기본)와 한국어를 전환할 수 있습니다.

## Structure

| Stage | Content |
|---|---|
| 0–4 (core) | Tools → Math → Machine learning → Deep learning → Transformers & foundation models |
| 5 (tracks) | A Post-training & reasoning · B Vision, audio & multimodal · C Generative models · D RL, agents & robotics · E Interpretability & safety · F ML systems & efficiency · G AI for science & graph learning |
| 6 | Entering research |
| Frontier | 6–8 new papers, talks and reports across AI, updated every Monday (KST) |

Each stage and track lists key concepts, the exact scope of each resource with estimated hours, a hands-on project, an exit criterion and common mistakes.

## Files

- `index.html` — the page (no build step)
- `data/curriculum.json` — stages, tracks and resources
- `data/frontier.json` — weekly frontier items (`weeks[0]` is the current week; the last 8 weeks are kept)

The page also includes a reality check: listed study hours, and what the roadmap does and does not give you.

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
