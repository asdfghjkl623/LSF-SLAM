# LSF-SLAM Dataset

The LSF-SLAM benchmark is designed for long-distance visual localization on flapping-wing flying robots under short-baseline, weak-disparity, vibration-affected outdoor flight.

## Platform

Data were collected using the U-HAWK 2.0 flapping-wing platform.

| Parameter | Value |
|---|---:|
| Wingspan | 220 cm |
| Body weight | 2300 g |
| Flight speed | 8–15 m/s |
| Flapping frequency | 3–5 Hz |
| Nominal flight altitude | 50–60 m |

## Sensor Rig

| Sensor | Configuration | Role |
|---|---|---|
| cam0 | 1.4 mm short focal | Full-image tracking reference |
| cam1 | 1.4 mm short focal | Equal-focal Standard Stereo partner |
| cam2 | 2.0 mm long focal | Magnified observations inside the calibrated overlap |
| IMU | Integrated 1 kHz unit | Visual–inertial baseline input |
| RTK-GNSS | Centimeter-level positioning | Reference trajectory in the East-North-Up frame |

The cam0–cam2 pair has a 4 cm physical baseline and forms the heterogeneous input used by LSF-SLAM. The cam0–cam1 pair has an 8 cm physical baseline and is used for the same-pipeline Standard Stereo comparison.

## Sequence List

All images have a resolution of 640 × 400 pixels.

| Sequence | Nominal altitude | Flight length | Duration |
|---|---:|---:|---:|
| FWFR-01 | 50 m | 225.7 m | 20 s |
| FWFR-02 | 50 m | 345.2 m | 30 s |
| FWFR-03 | 50 m | 479.2 m | 40 s |
| FWFR-04 | 50 m | 357.3 m | 30 s |
| FWFR-05 | 50 m | 784.8 m | 60 s |
| FWFR-06 | 50 m | 959.5 m | 80 s |
| FWFR-07 | 60 m | 127.9 m | 10 s |
| FWFR-08 | 60 m | 96.6 m | 10 s |

The first six trajectories were recorded at a nominal altitude of approximately 50 m. FWFR-07 and FWFR-08 are additional same-site trajectories recorded at approximately 60 m with the same platform and 2.0/1.4 mm long-to-short focal configuration.

## Planned Public Package

The external release is expected to contain:

- synchronized cam0 and cam2 image streams;
- image timestamps and per-sequence metadata;
- camera intrinsic and extrinsic calibration files;
- RTK-GNSS reference trajectories;
- coordinate-frame documentation;
- ATE and RPE evaluation scripts.

The dataset and camera-parameter archives are already stored on Google Drive. The public URL will be inserted after link confirmation.

## Evaluation Protocol

The paper evaluates trajectory accuracy using absolute trajectory error (ATE) and relative pose error (RPE). Estimated trajectories are aligned with the RTK-GNSS reference in the East-North-Up frame before error computation. Reported ATE RMSE values use ten runs per sequence; a missing result indicates tracking failure.

The tested references include MF-SLAM, Standard Stereo, Photo-SLAM, ORB-SLAM3 Mono, and VINS-Fusion. LSF-SLAM completes all eight trajectories and records the lowest mean ATE RMSE on every sequence among these tested baselines.

## Data Availability

See [download.md](download.md) for the release status and future Google Drive links.