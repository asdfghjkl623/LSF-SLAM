# Dataset Description

This page summarizes the preliminary dataset information reported in the LSF-SLAM paper draft.

## Purpose

The LSF-SLAM dataset is designed for evaluating visual localization on flapping-wing flying robots under outdoor far-field conditions. It focuses on the following coupled challenges:

- limited payload and short physical stereo baseline;
- weak disparity for distant landmarks;
- vibration induced by flapping-wing motion;
- rapid viewpoint change during outdoor flight;
- cross-focal correspondence verification between short- and long-focal cameras.

## Platform

The data were collected using the U-HAWK2.0 flapping-wing platform.

| Parameter | Value |
|---|---:|
| Wingspan | 220 cm |
| Body weight | 2300 g |
| Flight speed | 8-15 m/s |
| Flapping frequency | 3-5 Hz |

## Sensor Setup

The paper draft describes a calibrated trinocular camera rig and an integrated IMU.

| Sensor | Role in the paper |
|---|---|
| `cam0` | Short-focal tracking reference camera |
| `cam1` | Equal-focal stereo camera used with `cam0` for the standard stereo baseline |
| `cam2` | Long-focal camera used with `cam0` for LSF-SLAM |
| IMU | High-rate inertial data used for visual-inertial baseline evaluation |
| RTK/GNSS | Reference trajectory source for trajectory-error evaluation |

The `cam0-cam2` pair forms the long-short focal input used by LSF-SLAM. The `cam0-cam1` pair forms the equal-focal stereo input used by the standard stereo baseline.

## Sequence List

| Sequence | Flight length | Duration | Resolution | Scenario |
|---|---:|---:|---|---|
| FWFR-01 | 225.7 m | 20 s | 640 x 400 | Nearly straight flight with regular vibration |
| FWFR-02 | 345.2 m | 30 s | 640 x 400 | Straight flight with a sharp turn and moderate vibration |
| FWFR-03 | 479.2 m | 40 s | 640 x 400 | Large-turn trajectory under strong vibration |
| FWFR-04 | 357.3 m | 30 s | 640 x 400 | Large-angle turning followed by straight flight with moderate vibration |
| FWFR-05 | 784.8 m | 60 s | 640 x 400 | Long trajectory with continuous turns |
| FWFR-06 | 959.5 m | 80 s | 640 x 400 | Sharp turn followed by a long straight trajectory |

## Planned Data Contents

The first public data package is planned to include:

- synchronized short-focal and long-focal image streams;
- timestamps for image synchronization;
- per-sequence metadata;
- camera calibration files;
- RTK/GNSS reference trajectories;
- evaluation scripts for ATE and RPE.

At the current preliminary stage, the actual downloadable archives are not yet attached.

## Evaluation Context

The paper evaluates LSF-SLAM against monocular, multi-focal, equal-focal stereo, photorealistic-mapping-oriented, visual-inertial, and hybrid visual baselines. The reported baselines include ORB-SLAM3 Mono, MF-SLAM, a standard stereo pipeline, Photo-SLAM stereo, VINS-Fusion, and Rover-SLAM.

All estimated trajectories are aligned to the RTK/GNSS reference trajectory in the East-North-Up frame before error computation in the paper draft. Detailed evaluation code and exact command examples will be added in a later release.
