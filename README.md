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