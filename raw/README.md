# Raw data

This directory is intentionally left without synthetic observations.

If original raw files are available, a recommended layout is:

- `timing/`
  - `open_space_trials.csv`
  - `moderate_clutter_trials.csv`
  - `narrow_passage_trials.csv`
- `power/`
  - board-input voltage/current traces from the Monsoon FTA22D
- `flight/`
  - RTK-GNSS/EKF trajectory logs for the 15 repeated flights
- `rtos/`
  - control/EKF period and jitter logs

Do not reconstruct raw trials from reported mean/SD/percentiles; preserve the original logged samples.
