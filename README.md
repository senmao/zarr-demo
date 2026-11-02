# zarr-demo

Jupyter notebooks that demonstrate the Zarr format to users who already know netCDF.

## Setup

The environment is managed with [uv](https://docs.astral.sh/uv/). Install it if you don't have it yet:

```bash
# Linux / macOS
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows (PowerShell)
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# or with pip
pip install uv
```

Then create the environment and start JupyterLab:

```bash
uv sync              # creates .venv from pyproject.toml / uv.lock
uv run jupyter lab   # start JupyterLab
```

## Notebooks

| Notebook | Content |
|---|---|
| `notebooks/zarr_demo_noteook.ipynb` | Zarr for C3S/CCI users: store layout, metadata, reading only the chunks you need, parallel write/read vs netCDF, chunking |

The demo data is the C3S/CCI Satellite Soil Moisture COMBINED product (daily, 1978–2025, 0.25° global, Zarr v3),
streamed over HTTPS from EODC.

You need internet access. A full run takes about 2 minutes and downloads a few hundred MB (only the chunks it needs).
The parallel read/write demo uses 8 threads (`N_WORKERS` in the notebook) and about 1 GB of RAM.
Local outputs of the notebook go to `notebooks/data/` (git-ignored).
