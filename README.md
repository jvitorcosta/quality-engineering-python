# quality-engineering-python

A p-chart in Python for the share of defective samples in a production process.

**Status:** coursework (2022)

## Why I built it

This is a statistical quality control exercise from my Quality Engineering course, done as a
notebook so the chart and the calculations live together.

## Quick start

```sh
uv run --with pandas --with numpy --with seaborn --with plotly --with jupyter jupyter lab carta_de_controle.ipynb
```

The notebook is in Portuguese. It runs top to bottom without errors.

## How it works

The notebook `carta_de_controle.ipynb`:

1. Reads 57 timed measurements from `medicao_dados.txt`. A measurement outside the 30 to 50 limits
   counts as a defect.
2. Simulates a week of measurements every 15 minutes from a normal distribution with the
   measurements' mean and standard deviation.
3. Groups them into samples of one 8-hour shift each (32 measurements) and computes the share of
   defects per sample, the average share and the upper and lower control limits (the lower one
   clamped to 0 when negative).
4. Plots the chart with Plotly and concludes that the process is under statistical control.

The simulation is random, so each run gives slightly different limits.

## About the data

The week of data is simulated, not measured. Only the 57 real measurements in
`medicao_dados.txt` feed it, and that file is not the original: it was missing from my first
upload, so I rebuilt it from the values plotted in the saved notebook. Treat the numbers as a
class exercise, not a real process study.

## License

MIT, see [LICENSE](LICENSE).
