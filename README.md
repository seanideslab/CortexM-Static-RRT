# Deterministic Static-Memory RRT Planning on Cortex-M — Supporting Data

This repository package contains the **processed data and configuration values reported in the JSA manuscript**:

> *Deterministic Static-Memory RRT Planning on Cortex-M: Bounded Memory, Timing Predictability, and Energy Trade-offs for SWaP-Constrained UAVs*

## Contents

- `data/01_sram_allocation.csv` — byte-level 20,480-byte SRAM accounting.
- `data/02_platform_configuration.csv` — STM32F103, Raspberry Pi 4, and Jetson Orin Nano configurations.
- `data/03_timing_tail_summary.csv` — 1,000-trial mean/SD/max/p99/p99.9 timing summaries.
- `data/04_stage_profile_summary.csv` — 50-trial stage-level timing profile.
- `data/05_node_utilization.csv` — planning success, node use, path length, and optimization ratio.
- `data/06_cross_platform_latency.csv` — moderate-clutter planning latency comparison.
- `data/07_power_energy.csv` — board-level idle/active power and energy per plan.
- `data/08_swap_characteristics.csv` — board weight, cooling, TDP, and physical volume.
- `data/09_flight_tracking_summary.csv` — flight-validation summary for 15 repeated flights.
- `data/10_rtos_timing_stack.csv` — task priorities, timing/jitter, and static stack allocation.
- `data/11_benchmark_scenarios.csv` — benchmark map dimensions, obstacle counts, and occupancy.
- `data/12_nearest_neighbor_cycle_analysis.csv` — DWT_CYCCNT cycle-model parameters and guards.
- `DATA_DICTIONARY.md` — field definitions and provenance notes.
- `metadata.json` — machine-readable dataset metadata.
- `raw/README.md` — recommended layout for raw logs if they are added later.
- `SHA256SUMS.txt` — checksums for integrity verification.

## Important scope note

The CSV files in this package reproduce **processed/aggregate values reported in the manuscript**.  
No synthetic per-trial observations, power waveforms, or flight logs have been generated. If the original raw logs are available, add them under `raw/` before public release to improve reproducibility.

## Measurement/configuration summary

- MCU: STM32F103C8T6, Cortex-M3, 72 MHz, 20 KB SRAM.
- Timing: ARM DWT_CYCCNT; 1,000 trials per benchmark scenario for tail statistics.
- Power: Monsoon High Voltage Power Monitor (FTA22D), 5,000 Hz, board-input measurement.
- SBC baselines: GCC 10.3 `-O3`, single-threaded.
- Raspberry Pi 4: `ondemand` governor, Wi-Fi/Bluetooth disabled.
- Jetson Orin Nano: 10 W `nvpmodel`, `schedutil` governor.
- Flight validation: 15 repetitions, 1.5 m commanded altitude, 0.5 m/s reference speed, RTK-GNSS/EKF position reference.

## Suggested GitHub release steps

1. Create a public repository.
2. Upload the contents of this package.
3. Add an explicit data license suitable for your intended reuse policy.
4. If available, add raw timing logs, power traces, and flight logs under `raw/`.
5. Create a GitHub Release (e.g., `v1.0`) and use its URL in the manuscript Data Availability statement.
6. For stronger archival persistence, optionally archive the GitHub release with Zenodo and use the resulting DOI.

## Citation

See `CITATION.cff`. Update the repository URL and release version after publication.
