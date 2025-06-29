# NeuroWing – OpenAI-to-Z Challenge Submission  
*Dual-gate AI pipeline for Amazonian archaeological discovery*

> **TL;DR** - Seven previously unrecorded earthworks in the Tapajós basin, Brazil, discovered with a live-data Walker filter (≥ 0.45) **plus** YOLO-SAM morphologic validation.

[![License: CC0](https://img.shields.io/badge/License-CC0-blue.svg)](LICENSE)
[![Python 3.9+](https://img.shields.io/badge/python-3.9%2B-blue.svg)](https://www.python.org/downloads/)

---

## 🏆 Competition Highlights
| Metric | Value |
|--------|-------|
| **New sites** | **7** high-confidence (mask ≥ 0.80) |
| Grid coverage | 3 km Amazon-wide (6 700 000 km²) |
| Walker cut-off | 0.45 (aligned across modules) |
| False-positive drop | 78 % vs. spectral-only pipeline |
| Re-run time | **< 15 min** (quick notebook, CPU) |

---

## 🚀 Quick Reproduce (≤ 15 min, CPU-only)

```bash
git clone --depth 1 --branch v1.0-competition \
  https://github.com/uks25/neuroWing-openai-to-z.git
cd neuroWing-openai-to-z
conda env create -f environment.yml
conda activate neurowing

# Set your creds (Earth-Engine & OpenAI)
export OPENAI_API_KEY="sk-···"
earthengine authenticate --quiet

# Run the 3-tile demo
jupyter nbconvert --execute notebooks/00_quick_reproduce.ipynb \
                  --to notebook --output run_log.ipynb
open results/high_conf_map.html          # interactive
