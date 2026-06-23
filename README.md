# Jailbreak Viewer

Static GitHub Pages viewer for LLM-LDS jailbreak evaluation results (original vs GCG attack).

The site is self-contained:

- `index.html`
- `app.js`
- `styles.css`
- `data/`
- `assets/`

## Build data from a run

```bash
python3 /home/yifengw3/bubble_sound/llm-lds-project/llm_lds/share_viewer/build_jailbreak_viewer_data.py \
  --run-dir /home/yifengw3/bubble_sound/llm-lds-project/llm_lds/results/20260618_150035/Llama-3.2-1B-Instruct
```

This reads `text/difficulty_{original|gcg}_temp_*.txt`, chunks by prompt, and writes JSON under `data/variants/`.

## Local preview

```bash
cd /home/yifengw3/bubble_sound/jailbreak-viewer
python3 -m http.server 8765
```

Open `http://localhost:8765/`. Do not open `index.html` directly via `file://`.

## GitHub Pages

1. Open **Settings → Pages** on the repo.
2. Set **Source** to **Deploy from a branch**, branch **`main`**, folder **`/ (root)`**.
3. After deploy, open `https://haizailache999.github.io/jailbreak-viewer/`.

## Controls

- **Prompt** — AdvBench prompt index
- **Trial** — generation trial index
- **Attack type** — `Original` or `GCG attack` (replaces checkpoint Step in the checkpoint viewer)
