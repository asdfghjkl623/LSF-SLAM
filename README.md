# LSF-SLAM

**Long-Short Focal Stereo Visual SLAM for Vibration-Affected Far-Field Localization of Flapping-Wing Robots**

This repository is the public entry point for the LSF-SLAM project and its accompanying long-short focal flapping-wing flying robot (FWFR) dataset. The project studies far-field visual localization under short-baseline, weak-disparity, and vibration-affected outdoor flight conditions.

> Status: preliminary release page. Dataset files, calibration files, RTK/GNSS reference trajectories, and evaluation scripts are being prepared and will be added progressively.

## Overview

LSF-SLAM is a heterogeneous stereo visual SLAM framework for coarse far-field localization of flapping-wing flying robots. The short-focal camera maintains wide-field tracking, while the long-focal camera contributes higher-resolution observations inside the calibrated overlap region after cross-focal association and weak-stereo verification. The backend uses a residual-calibrated heterogeneous local bundle adjustment formulation for vibration-affected reprojection residuals.

The accompanying benchmark is designed for evaluating:

- long-short focal stereo visual SLAM;
- weak-disparity far-field localization;
- cross-focal feature association and verification;
- vibration-affected visual localization on FWFR platforms;
- outdoor trajectory evaluation against RTK/GNSS reference trajectories.

## Dataset Status

| Component | Current status |
|---|---|
| Short-focal and long-focal synchronized images | Preparing |
| Timestamps | Preparing |
| Camera intrinsic/extrinsic calibration | Planned |
| RTK/GNSS reference trajectories | Planned |
| ATE/RPE evaluation scripts | Planned |
| Google Drive download link | Coming soon |

## Dataset Summary

The current paper draft reports six real outdoor FWFR trajectories collected with the U-HAWK2.0 platform and a calibrated trinocular camera rig. All image sequences use a resolution of `640 x 400` pixels.

| Sequence | Flight length | Duration | Resolution | Scenario |
|---|---:|---:|---|---|
| FWFR-01 | 225.7 m | 20 s | 640 x 400 | Outdoor, nearly straight flight with regular vibration |
| FWFR-02 | 345.2 m | 30 s | 640 x 400 | Outdoor, straight flight with a sharp turn and moderate vibration |
| FWFR-03 | 479.2 m | 40 s | 640 x 400 | Outdoor, large-turn trajectory under strong vibration |
| FWFR-04 | 357.3 m | 30 s | 640 x 400 | Outdoor, large-angle turn followed by straight flight |
| FWFR-05 | 784.8 m | 60 s | 640 x 400 | Outdoor, long trajectory with continuous turns |
| FWFR-06 | 959.5 m | 80 s | 640 x 400 | Outdoor, sharp turn followed by a long straight trajectory |

## Sensor Configuration

The dataset was collected on the U-HAWK2.0 flapping-wing platform. According to the paper draft, the platform has a 220 cm wingspan, a body weight of 2300 g, a flight speed of 8-15 m/s, and a flapping frequency of 3-5 Hz.

The sensing setup contains a trinocular camera rig:

- `cam0`: short-focal camera used as the main tracking reference;
- `cam1`: equal-focal stereo partner for standard stereo baseline comparison;
- `cam2`: long-focal camera used with `cam0` for LSF-SLAM;
- IMU: integrated high-rate IMU used for visual-inertial baseline evaluation in the paper.

The paper uses the `cam0-cam2` long-short focal pair as the input to LSF-SLAM. The `cam0-cam1` equal-focal pair is used for the standard stereo baseline.

## Download

Dataset download links will be added after packaging.

| Package | Link | Notes |
|---|---|---|
| Full dataset | Coming soon | Google Drive link will be added here |
| Sample sequence | Coming soon | Optional lightweight sample for format checking |
| Calibration and reference files | Coming soon | To be released with dataset packages |

See [docs/download.md](docs/download.md) for the planned package layout.

## Planned Repository Layout

```text
LSF-SLAM/
  README.md
  docs/
    dataset.md
    download.md
    release_plan.md
  data/
    FWFR-01/
    FWFR-02/
    FWFR-03/
    FWFR-04/
    FWFR-05/
    FWFR-06/
  config/
  scripts/
```

Large data files will not be stored directly in GitHub. GitHub will host documentation, metadata, configuration examples, and evaluation code; the dataset archives will be provided through external download links.

## Citation

The paper is currently in draft/preprint preparation. A BibTeX entry will be updated after the final citation information is available.

```bibtex
@misc{lsfslam2026,
  title  = {Long-Short Focal Stereo Visual SLAM for Vibration-Affected Far-Field Localization of Flapping-Wing Robots},
  author = {Zhong, Zheng and Chen, Shuo and Fu, Qiang and Wu, Xiaoyang and Zhang, Xulong and He, Wei},
  year   = {2026},
  note   = {Dataset and code repository: https://github.com/asdfghjkl623/LSF-SLAM}
}
```

## License

The dataset and code licenses will be specified before the public data release. Please do not redistribute unpacked dataset files until the final license is attached.

## Contact

For questions about the dataset or the LSF-SLAM paper, please open a GitHub issue in this repository.
