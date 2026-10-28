# quality-engineering-python

Statistical quality control in Python (2022): a **p-chart** for the share of defective samples
in a production process.

The notebook `carta_de_controle.ipynb` (in Portuguese):

1. Reads 57 timed measurements from `medicao_dados.txt`. A measurement outside the 30 to 50 limits
   counts as a defect.
2. Simulates a week of measurements every 15 minutes from a normal distribution with the
   measurements' mean and standard deviation.
3. Groups them into samples of one 8-hour shift each (32 measurements) and computes the share of
   defects per sample, the average share and the upper and lower control limits (the lower one
   clamped to 0 when negative).
4. Plots the chart with Plotly and concludes that the process is under statistical control.

The simulation is random, so each run gives slightly different limits.

## Run it

```sh
uv run --with pandas --with numpy --with seaborn --with plotly --with jupyter jupyter lab carta_de_controle.ipynb
```

`medicao_dados.txt` was missing from the first upload; it was rebuilt from the measurements
plotted in the saved notebook.
