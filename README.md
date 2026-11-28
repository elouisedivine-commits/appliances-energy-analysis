# What Drives Appliance Energy Use in a Home?

Final project for Introduction to Data Analytics.
Dataset: Appliances Energy Prediction (UCI Machine Learning Repository), https://doi.org/10.24432/C5VC8G

## Files
- energydata_complete.csv: original data
- energydata_clean.csv: cleaned data
- cleaning.ipynb: data cleaning and exploration

## Summary of cleaning decisions
- Converted the 'date' from text to datetime.
- Created 'hour' and 'day_night' (Day = 6 am to 10 pm, Night = 10 pm to 6 am).
- Dropped 'rv1' and 'rv2' (those random columns with no real meaning)
- No missing Values or duplicate rows were found, so nothing was removed.
- Kept all the outliers (2,138 readings above 175Wh, 10.8%) because they look like real high-use events.

## What This Project Is
We study what is linked to electricity use by household appliances in one low-energy house. The data has a reading every 10 minutes, with appliance energy use (Wh), lighting use, temperature and humidity in nine indoor locations, and outdoor weather. Our questions:

1. Does appliance energy use differ between daytime and night-time?
2. Which conditions (indoor temperature, indoor humidity, outdoor weather, time of day) are most linked to higher appliance energy use?
3. Can we predict appliance energy use from these conditions, and how much better is it than guessing the average?

**Dataset:** Appliances Energy Prediction, UCI Machine Learning Repository. 19,735 rows and 29 columns, 11 Jan to 27 May 2016. One row is one 10-minute reading.
Candanedo, L. (2017). *Appliances Energy Prediction* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5VC8G

## Repository contents

```
.
├── README.md
├── requirements.txt
├── energydata_complete.csv   # original (raw) dataset from UCI
├── energydata_clean.csv      # cleaned dataset, created by cleaning.ipynb
└── cleaning.ipynb            # look at, clean and explore the data
```

## Set up the environment

You need Python 3.10 or newer.

```
bash
git clone [repository URL]
cd [repository folder]

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

pip install -r requirements.txt
```

`requirements.txt` contains:

```
pandas
numpy
matplotlib
seaborn
jupyter
```


## Run everything from raw data to results

1. Make sure `energydata_complete.csv` is in the same folder as `cleaning.ipynb`.
2. Start Jupyter: `jupyter notebook`
3. Open `cleaning.ipynb` and choose **Kernel → Restart & Run All**.

The notebook:

- loads the raw data and checks size, column types, missing values and duplicates (none of the last two were found);
- converts `date` to a datetime and creates `hour` and `day_night` (Day = 6:00 am to 9:59 pm);
- drops `rv1` and `rv2` (random-number columns with no real meaning);
- finds outliers with the 1.5 × IQR rule and keeps them (2,138 readings above 175 Wh, 10.8%);
- saves the result as `energydata_clean.csv`;
- draws the exploration charts: appliance use histogram, day vs night boxplot, average use by hour, and a correlation heatmap.