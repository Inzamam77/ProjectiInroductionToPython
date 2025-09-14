# German Train Timetable Project

This project is a clean, ready-to-run **data tutorial** for a synthetic German train timetable.

## Files
- `german_train_tutorial.ipynb` — step-by-step notebook with analysis & visualizations. it has GUI end of the code to search train by dastination and day
- `german_train_timetable.csv` — dataset with 300 rows. **All values are valid (no NaNs or empty strings).**
- `requirements.txt` — dependencies.
- `LICENSE` — MIT license (open-source usage).
- `README.md` — this file.

## Installation
Install Python 3.9+ and required dependencies:
```bash
pip install -r requirements.txt
```

## How to Run
Open the notebook in Jupyter/Lab/VS Code:
```bash
jupyter lab
```
or
```bash
jupyter notebook
```

Run cells from top to bottom.

---

## Notebook Tutorial Overview

The notebook walks through:

1. **Loading and verifying data**
   - Uses `pandas.read_csv()` to load the timetable.
   - Checks for NaNs and empty strings with `isna().sum()` and custom checks.

2. **Helper Functions**
   - `parse_hhmm_to_minutes(s)` → converts "HH:MM" into minutes.
   - `add_parsed_time_columns(df)` → adds numeric columns and trip duration.
   - `frequency_by_day(df)` → counts trains per weekday.
   - `avg_duration_by_service(df)` → average duration per service (ICE/IC/RE).
   - `busiest_stations(df)` → busiest hubs (origins + destinations).
   - `filter_trains(df, origin, destination, day, after)` → filters trains.

3. **Analyses**
   - Frequency by day, average durations, busiest stations.

4. **Visualizations**
   - Bar charts and a heatmap (day × hour).

5. **Selection-based Lookup**
   - Choose origin/destination/day/after time, display matching trains.

---

## In-Notebook GUI (ipywidgets)

The GUI notebook (`german_train_tutorial_with_gui.ipynb`) adds an interactive panel with:

- Dropdowns for **Origin**, **Destination**, **Day**.
- Text box for **After (HH:MM)** filter.
- **Search** button and **Clear filters** button.
- A **results table** of trains matching filters (up to 100 rows shown).
- A **Train picker dropdown** listing each result.
- A **details card** showing full train info (route, duration, platform, stops, notes).
- **Export buttons** to save the filtered results as CSV (`filtered_trains.csv`) or Excel (`filtered_trains.xlsx`).

### Example Workflow
1. Select **Origin = Berlin Hbf**, **Destination = München Hbf**, **Day = Mon**, **After = 08:00**.
2. Click **Search** → see all matching trains in a table.
3. Use the **Train** dropdown to pick one → see full details card.
4. Click **Export CSV/Excel** to save results.

### Dependencies for GUI
- `ipywidgets` (for dropdowns and buttons).
- `openpyxl` (for Excel export).

Enable widgets if they don’t appear:
```bash
jupyter nbextension enable --py widgetsnbextension
```

---

## Expected Outputs
- Printed tables with train details.
- Series outputs (counts, averages).
- Bar charts and heatmaps.
- Filtered trains shown in interactive table + details card (GUI notebook).
- Exported CSV/Excel files.

---

## License
This project uses the **MIT License**, meaning:

See `LICENSE` for full text.

---

## Summary
This project is both a **tutorial** (explaining pandas functions and matplotlib visualizations) and a **tool** (filtering trains with a GUI inside the notebook). It is open-source and ready for extension.