# MEMS-PN
Phase noise and frequency noise extraction and analysis tools for MEMS systems

## Background

MEMS-PN is an application designed to extract and analyse phase and frequency noise in MEMS systems. The goals for this application are:

- The application offers a more efficient alternative to traditional transient simulations with Simulink model for extracting the phase noise of the MEMS system.

- The parameters in the model used for this application can be adjusted to accommodate different circuit configurations.

The application contains the MEMS system architecture shown below.

<img src="https://github.com/refuliar/ImageBed/blob/main/MEMS-PN/System.png" alt="model"  />

## Installation

The MATLAB application needs your version of MATLAB higher than 2021b.

Please ensure that you have installed [SIMULINK](https://ww2.mathworks.cn/products/simulink.html) before running the application.

[Get the latest release of MEMS-PN (MATLABapp)](https://github.com/refuliar/MEMS-PN/releases/tag/matlabapp)

## Usage

Once you have installed and run the application, you can see the following interface.

![图片1](https://github.com/refuliar/ImageBed/blob/main/MEMS-PN/MainInterface.png)

|   Parameter   |     Units      |                 Interpretation                 |
| :-----------: | :------------: | :--------------------------------------------: |
|    `Q_d`      |      \         |         Quality factor                         |
|    `m_d`      |      kg        |         Resonator equivalent mass              |
|    `Omega_d`  |      rad/s     |         Intrinsic frequency                    |
|    `k_d`      |      \         |         Zero-order stiffness                   |
|    `c_d`      |      \         |         Damping coefficient                    |
|    `k2`       |      \         |   2nd-order stiffness (typical value = 1000)   |

|   Parameter   |     Units      |                 Interpretation                 |
| :-----------: | :------------: | :--------------------------------------------: |
|    `K_bd`     |      V         |         Drive bias voltage                     |
|    `K_bs`     |      V         |         Sense bias voltage                     |
|    `K_amp`    |      \         |         20M, 40M, 80M transimpedance gain      |
|    `K_ref`    |      \         |         Reference Voltage                      |
|    `K_cd`     |      F/m       |         dC/dx-drive                            |
|    `K_cs`     |      F/m       |         dC/dx-sense                            |
|    `Km`       |     m/s/N      |  Mechanical gain, from drive force to velocity |
|    `Wc`       |      \         |         Low-order System pole coefficient      |
|    `K_gm`     |      \         |         Active Loop Filter Gm                  |
|    `K_mul`    |      \         |         Gain of the mul                        |
|    `V_dd`     |      V         |         Supply Voltage                         |

## Maintainers

[@Zhihang Zhang](https://github.com/refuliar).

## Contributors

This project exists thanks to all the people who contribute.

<a href="https://github.com/refuliar/MEMS-PN/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=refuliar/MEMS-PN" />
</a>

## License

[MIT](https://github.com/RichardLitt/standard-readme/blob/main/LICENSE) © Zhihang Zhang
