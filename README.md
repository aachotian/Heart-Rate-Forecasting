# Heart Rate Forecasting

This project studies **one-step-ahead heart rate forecasting** using classical time series models, machine learning, and Markov switching models.

## Models

* Naive baseline
* AR(3)
* ARIMA(3,1,0)
* XGBoost
* MS-AR(3)
* MS-AR(3) with switching variance

## Setup

```bash id="c3m8zv"
pip install -r requirements.txt
```

Run the notebook to reproduce the results.

## Data

The raw data is not included in this repository.

Download the datasets from the following sources and place them at the repository root:

```text id="xjq1lz"
sensors-22-00034-s001/
PPG_FieldStudy/
WildPPG.mat
```

* **Japanese Lifestyle Study (Staffini et al., 2022)**
  https://www.mdpi.com/1424-8220/22/1/34/s1
  → Download the supplementary files and use the folder `sensors-22-00034-s001`

* **PPG-DaLiA**
  https://archive.ics.uci.edu/dataset/495/ppg+dalia
  → Extract into `PPG_FieldStudy/`

* **WildPPG (Meier et al., 2024)**
  https://huggingface.co/datasets/eth-siplab/WildPPG
  → Download the `.mat` file and place it as `WildPPG.mat`

## Notes

* Models are trained **per subject**
* Forecasting is **one-step ahead**
* True observations are fed sequentially (no refitting)

## Results (summary)

* Markov switching models perform best on higher-resolution datasets (DaLiA, WildPPG)
* Differences are small on the Japanese dataset, where the naive baseline is competitive
* XGBoost underperforms compared to linear models

## Author

Alex Achotian — ETH Zürich, Semester Thesis (Spring 2026)
