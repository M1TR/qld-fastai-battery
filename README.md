# qld-fastai-battery

This repo will serve as the primary location for all code and data related to this project.

Our goal: To predict **remaining useful life (RUL)** of Li-Ion batteries. We aim to try two approaches: a seq2seq model and a novel approach where we transform the charge/discharge characteristic data into image form and apply self-supervised learning to make the prediction, effectively making this an **image inpainting** problem.

Understanding the data: Using the `mat_to_json.ipynb` notebook, we decompose the individual `.mat` files into separate JSONs for charging, discharging, and impedance operations. To simplify, the `filename_impedance.json` represents the internal impedance of the battery as it goes through ~600 cycles of use while `filename_charge.json` and `filename_discharge.json` represent the voltage per cycle over time during charging and discharging operations respectively.

A battery is declared to be at **end of life (EOL)** when a 30% fade in rated capacity is observed. Each `.mat` file represents one battery cycled continuously till it reached EOL. Specific details can be found at (README-battery.md)

The `mat_to_json.ipynb` notebook also contains code to plot each individual JSON file, viz. charging, discharging, and impedance.
