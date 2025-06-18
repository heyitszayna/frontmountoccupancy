# FrontMountOccupancy

This repository contains a modified version of the **Front Mount Occupancy** demo from the **mmWave Automotive Toolbox 3.6**, developed by Texas Instruments as part of the **In-Cabin Sensing Lab**.

## Overview

The original demo provides a front-mounted mmWave radar-based occupancy detection system for in-cabin sensing applications. This project builds upon that baseline by incorporating additional functionalities to support our capstone project requirements.

## Modifications

The following updates have been made to the original code:

- **GUI Enhancements** (`gui/` folder):  
  - Instead of running `od_demo.exe`, we now run the `od_demo.m` file directly in the MATLAB Command Window.
  - Usage format:
    ```matlab
    od_demo(data_port, cli_port, path_to_cfg_file, 2, 1, 0)
    ```
    Replace `data_port`, `cli_port`, and `path_to_cfg_file` with appropriate values for your system and chirp configuration.

- **Frame Saving and Raspberry Pi Communication**:  
  - The GUI has been modified to:
    - Save radar frames (e.g., heatmaps, point clouds) to a local output folder.
    - Send frame data to a Raspberry Pi for further processing.
  - To enable RPi communication, ensure the **MATLAB Raspberry Pi Hardware Support Package** is installed.
  - Connection setup in MATLAB:
    ```matlab
    r = raspi('IP_ADDRESS', 'USERNAME', 'PASSWORD');
    ```

- **Configuration Files**:  
  - Custom chirp configuration files are provided in the `chirp_configs/` directory, tailored for our system requirements.

## Usage

1. **Clone or download** this repository to your local machine.
2. **Connect your mmWave sensor** to the laptop via USB and ensure ports are correctly identified.
3. **Open MATLAB**, navigate to the `gui/` folder, and open `od_demo.m`.
4. In the MATLAB **Command Window**, run:
    ```matlab
    od_demo(data_port, cli_port, path_to_cfg_file, 2, 1, 0)
    ```
    Ensure `data_port`, `cli_port`, and `path_to_cfg_file` match your device and configuration.

5. Make sure all **prerequisites** are satisfied:
   - MATLAB-compatible mmWave sensor connected.
   - All required MATLAB toolboxes and support packages installed (e.g., Instrument Control Toolbox, Raspberry Pi Support Package).
   - Custom configuration file (e.g., from `chirp_configs/`) selected.

## Acknowledgments

This work builds on the original contributions by Texas Instruments through their mmWave Automotive Toolbox and In-Cabin Sensing Lab demos. All original intellectual property remains with Texas Instruments.
