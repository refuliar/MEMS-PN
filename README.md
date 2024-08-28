# MEMS-PN
Phase noise and frequency noise extraction and analysis tool for MEMS systems

## Background

MEMS-PN is an application designed to extract and analyse phase and frequency noise in MEMS systems. The goals for this application are:

- The application offers a more efficient alternative to traditional transient simulations with Simulink model for extracting the phase noise of the MEMS system.

- The parameters in the model used for this application can be adjusted to accommodate different circuit.

The application contains the MEMS system architecture shown below. It consists of 4 modules, namely MEMS resonator, TIA, active loop filter and PGA. The system includes 6 noise source inputs and 3 signal source outputs.

<img src="https://github.com/refuliar/ImageBed/blob/main/MEMS-PN/System.png" alt="model"/>

## Installation

The MATLAB application needs your version of MATLAB higher than 2021b.

Please ensure that you have installed [SIMULINK](https://ww2.mathworks.cn/products/simulink.html) before running the application.

[Get the latest release of MEMS-PN (MATLABapp)](https://github.com/refuliar/MEMS-PN/releases/tag/matlabapp)

## Usage

Once you have installed and run the application, you can see the following interface.

![图片1](https://github.com/refuliar/ImageBed/blob/main/MEMS-PN/MainInterface.png)

On the left hand side, you can set the parameters of the system and carry out system stability analysis, calibration with low-order model transient simulation and phase noise extraction analysis.

On the right hand side, you can visualise the system structure and see the description of the parameters.

Mechanical parameters are responsible for describing the mechanical performance of the MEMS resonant.

|   Parameter   |     Units      |                 Description                    |
| :-----------: | :------------: | :--------------------------------------------: |
|    `Q_d`      |      \         |         Quality factor                         |
|    `m_d`      |      kg        |         Resonator equivalent mass              |
|    `Omega_d`  |      rad/s     |         Intrinsic frequency                    |
|    `k_d`      |      \         |   Zero-order stiffness (=m_d*Omega_d^2)        |
|    `c_d`      |      \         |   Damping coefficient  (=m_d*Omega_d/Q_d)      |
|    `k2`       |      \         |   2nd-order stiffness (typical value = 1000)   |

Electric parameters are responsible for describing the specific details of each module.

|   Parameter   |     Units      |                 Description                    |
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

"Equivalent Input Noise" corresponds to 6 different noise sources, supports flicker noise and white noise mixing inputs.

|   Parameter   |     Units      |                Description                     |
| :-----------: | :------------: | :--------------------------------------------: |
|  `Mechanial`  |  N/sqrt(Hz)    |     mechanical input noise                     |
|  `Front-end`  |  A/sqrt(Hz)    |     front-end input noise                      |
|  `PGA`        |  V/sqrt(Hz)    |     PGA output noise                           |
|  `Rectifier`  |  V/sqrt(Hz)    |     rectifier output & subtracter input noise  |
|  `PI quantify`|  V/sqrt(Hz)    |     PI output quantization noise               |
|  `Reference`  |  V/sqrt(Hz)    |     reference source noise                     |

The process of running the application is shown below.

1. Complete input of system parameters
2. Run “stability analysis” and “trans. calibration”
3. Check if the system can stabilise oscillations based on the results
4. If the system fails to stabilise in step 3, revert back to step 1
5. Complete input of noise source parameters
6. Run “PN noise”

In the stability analysis, the application will give the zero-pole analysis of the system and the specific values of the RC filter.

The application supports interconversion between phase and frequency noise, and can query the frequency noise as well as calculate the total in-band noise.

![图片2](https://github.com/refuliar/ImageBed/blob/main/MEMS-PN/Process.gif)

## Maintainers

[@Zhihang Zhang](https://github.com/refuliar).

## Contributors

This project exists thanks to all the people who contribute.

<a href="https://github.com/refuliar/MEMS-PN/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=refuliar/MEMS-PN" />
</a>

## License

[MIT](https://github.com/RichardLitt/standard-readme/blob/main/LICENSE) © Zhihang Zhang
