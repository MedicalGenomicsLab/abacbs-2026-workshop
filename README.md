# Swarm in the Lab: workshop materials

BiocAsia 2026 satellite workshop at ABACBS 2026, RMIT University.

Unzip this in your home folder (`cd ~ && python3 -m zipfile -e swarm-in-the-lab.zip .`) on the organiser instance. Everything lands in `~/workshop`, which is where the notebooks expect it. Then follow **`ORGANISER_SETUP.md`** from the top.

## What's here

| File | What it is | Who runs it |
|---|---|---|
| `00_preflight.ipynb` | Self-test, plus **Step 0**, where workshop keys are entered into a hidden box | Everyone, at 13:00 (you: before imaging and on one clone) |
| `01_virtual_lab.ipynb` | Module 1 · Virtual Lab: question to research strategy (13:35–14:25) | Participants |
| `02_paper2agent.ipynb` | Module 2 · Paper2Agent: papers to tools (14:40–15:30) | Participants |
| `03_virtual_biotech.ipynb` | Module 3 · Virtual Biotech: team to evidence (15:40–16:30) | Participants |
| `tools/vbt_workshop.py` | Launcher that Module 3 uses to run the Virtual Biotech with a small team, a time limit and credential guards | Module 3 (automatically) |
| `ORGANISER_SETUP.md` | Step-by-step instance setup, and what to do before and after cloning | You |
| `environment.yml` | The workshop conda environment (`swarm-lab`, Python 3.12) | You, once |
| `claude_settings.json` | Claude Code permissions: copy to `~/workshop/.claude/settings.json` | You, once |
| `prepare_image.py` | Finds and removes your keys, sign-ins and test outputs before the image is made | You, last thing before imaging |

## Not included (download during setup)

- The Paper2Agent and Virtual Biotech repositories, and the Paper2Agent builds and servers
- The Open Targets 25.09 data (about 40 GB)
- The workshop datasets
- Pre-run copies in `cache/`, which your own test runs create

## Placeholders to fill in

Search for `[PLACEHOLDER` in each notebook's **Settings** or **Setup** cell:

- `00_preflight.ipynb`: dataset path, Virtual Biotech folder, Open Targets folder, the Paper2Agent servers to check. Also keep `VBT_MODEL` the same as `MODEL` in `03_virtual_biotech.ipynb`.
- `01_virtual_lab.ipynb`: one-line descriptions of the single-cell and spatial datasets, in `AVAILABLE_TOOLS`
- `02_paper2agent.ipynb`: dataset paths, the recorded build folder, and each paper agent's start-up command (from its `USAGE.md`)
- `03_virtual_biotech.ipynb`: Open Targets folder, and `EXPECTED_COST` (measure it on your test run)

## Hand-offs between modules

Module 1 writes `outputs/module1/research_strategy.json`. Module 2 reads it and writes `outputs/module2/analysis_log.json` and `paper_agents.json`. Module 3 reads all three and writes `outputs/module3/run_summary.json` for Module 4. Each module has `USE_CACHE = True` for anyone who falls behind; it reads the pre-run copies you put in `cache/`.
