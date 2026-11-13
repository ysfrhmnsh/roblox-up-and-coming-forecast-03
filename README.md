# Roblox Up-and-Coming Forecaster v4

Forecasts the Up-and-Coming top 10 per hour for the 72h after the
competition closes, as a place-probability table plus a top-10 list.

Method: a fixed-weight stack of three forecasters, blended in
probability space — 0.80 Monte Carlo rank simulation (the v2 engine),
0.18 fitted Gaussian place-occupancy table, 0.02 fitted practice
table (empirical occupancy with place-kernel smoothing and a drift
shift). See BUILD_NOTES.md for the method, the experiments, and the
scores on three validation windows.

Run: `python3 main.py` with `$MAKEFUN_INPUT_DIR` (default `/input`)
holding `history.ndjson` + `task.json`; writes `forecast.json` to
`$MAKEFUN_OUTPUT_DIR` (default `/output`). Python 3.13 standard
library only, no network, deterministic (fixed seed).
