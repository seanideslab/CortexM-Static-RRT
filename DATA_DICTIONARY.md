# Data Dictionary

All numeric values are transcribed from the manuscript and its reported supporting measurements.

## Timing fields
- `mean_ms`, `sd_ms`, `max_ms`, `p99_ms`, `p99_9_ms`: planning latency statistics in milliseconds.
- `trials`: number of trials used for the reported distribution.
- `max_jitter_us`: maximum observed task-period jitter in microseconds.

## Memory fields
- `size_bytes`, `size_kib`, `share_percent`: design-time SRAM accounting.
- `allocated_stack_bytes`: statically allocated FreeRTOS task stack.
- `N_max`: hard RRT node-pool limit.

## Planning fields
- `planning_success_percent`: fraction of trials in which a path was found within the resource guards.
- `avg_nodes_used`, `sd_nodes_used`: reported node-count mean and standard deviation.
- `path_optimization_ratio`: pruned/smoothed path length divided by raw RRT path length.

## Power/energy fields
- `idle_power_w`: measured board-level active-idle power.
- `active_power_w`: measured board-level power during planning.
- `energy_per_plan_j`: reported per-plan energy for the moderate-clutter comparison.
- Measurement point: DC board input.
- Instrument: Monsoon High Voltage Power Monitor (FTA22D), 5,000 Hz.

## Benchmark fields
- Map: 100 m × 100 m continuous 2D search space.
- Occupancy definition: geometric obstacle area divided by total map area.
- `occupancy_relation` distinguishes strict (`<`) from approximate (`approximately`) reported occupancy.

## Flight fields
- Flight validation: 15 repetitions.
- Commanded altitude: 1.5 m.
- Reference speed: 0.5 m/s.
- Position reference: u-blox ZED-F9P RTK-GNSS fused with IMU in the onboard EKF.

## Provenance limitation
This package contains processed manuscript-supporting data only. Per-trial raw timing samples, 5,000-Hz power waveforms, and raw flight logs are not reconstructed from aggregate statistics.
