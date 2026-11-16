# HistorianRCA

90 days of simulated plant historian data from a steam-heated agitated hold tank under cascade temperature and level control, with hidden faults of known root cause, realistic historian artifacts and deliberate distractors, built as a root cause analysis benchmark.

- **Domain:** Chemical and process
- **Asset / Process:** Chemical process units
- **Modality:** Time series
- **Task:** Fault diagnosis; Anomaly detection
- **Source Type:** Simulation
- **Access:** Code repository
- **Size:** 90 tags over 90 days, about 57 MB of Parquet files
- **Year:** 2026
- **License:** CC BY
- **Publisher:** Scott Duncan

## Description

HistorianRCA is a root cause analysis benchmark published by Scott Duncan on GitHub. It contains 90 days of simulated plant historian data, from 1 March to 30 May 2024 UTC, for TK-101, a steam-heated agitated hold tank with a submerged steam coil, a temperature-to-steam-flow cascade and a level control loop. The record holds 90 tags at a 10 second DCS scan: 30 on TK-101 and 60 on four neighbouring units that share only the weather with it. The first 14 days are normal operation and serve as a baseline.

The data is designed to behave like a real historian. Tags are noisy, autocorrelated, quantized, stored at irregular timestamps and compressed with swinging-door compression, and the record includes communication outages, stuck readings, single-sample spikes, slow calibration drift and weather and seasonal effects. The controllers hide many faults, so temperature and level stay at setpoint while the fault shows up elsewhere. Each fault has exactly one root cause and known start and end times, held in a private answer key; deliberate operator actions and data-quality artifacts are included as distractors that are not faults. The task is to report each fault's start, end, root cause and supporting tags, and every root cause can be determined from the historian data and the process description alone using first-principles chemical engineering. Submissions are scored by the author: +1 per detected fault, +2 more for the correct cause, and −1 per false positive.

The repository provides the primary long-format record historian.parquet (about 33 MB), a regular 1-minute grid historian_60s.parquet (about 25 MB), a tag dictionary, a process description, the challenge rules and a submission template. Version 1.0 was released in October 2026 under CC BY 4.0.

## References

- [GitHub repository](https://github.com/ScottDuncanAI/HistorianRCA)
- [Process description](https://github.com/ScottDuncanAI/HistorianRCA/blob/main/PROCESS_DESCRIPTION.md)
- [Public Chemical Manufacturing Datasets (source collection)](https://github.com/redsynapses/public-chemical-manufacturing-datasets)

[⬅️ Back to Index](../README.md)
