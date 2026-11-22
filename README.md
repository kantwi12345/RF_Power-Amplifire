# 714 MHz class-AB LDMOS power amplifier

A class-AB RF power amplifier designed and simulated in Keysight ADS around the BLP0408H9S30 LDMOS transistor. At 714 MHz it delivers 44.5 dBm (about 28 W) of output power with 20.5 dB of gain and about 57 % power-added efficiency (PAE).

## Results

| Parameter | Value |
|---|---|
| Operating frequency | 714 MHz |
| Class | AB |
| Output power | 44.5 dBm (about 28 W) |
| Large-signal gain | 20.5 dB |
| PAE | about 57 % |
| Available input power | 24 dBm |
| Drain supply | 50 V |
| Gate bias | 2.2 V |
| Transistor | BLP0408H9S30 (LDMOS) |
| Substrate | Rogers RO4003, 20 mil |

Gain is output power minus input power at the 24 dBm drive level (44.5 dBm − 24 dBm). PAE is (P_out − P_in) / P_DC.

All figures are simulation results from ADS harmonic balance and Momentum RF EM co-simulation. They are not measurements.

## Design workflow

1. **Bias.** A gate-voltage sweep from 0 to 10 V sets the class-AB operating point. The design uses a 2.2 V gate bias with a 50 V drain supply.
2. **Stability.** Gain circles and source-stability circles confirm the amplifier is stable.
3. **Load pull.** A one-tone harmonic-balance load pull sweeps the load from 1 to 30 Ω (real) and ±30 Ω (imaginary), with 2nd and 3rd harmonic terminations, to find the impedance for output power and efficiency.
4. **Matching.** Input and output matching networks are designed on the Smith chart over 500 MHz to 1.5 GHz.
5. **EM co-simulation.** The matching layouts are simulated in Momentum RF on 20 mil Rogers RO4003 and co-simulated with the transistor model.
6. **Final sweeps.** Power and frequency sweeps on the final layout give the results above.

## Project files

- ADS workspace: `RF_PA_wrk`
- ADS library: `RF_PA_lib` (schematics and layouts)

To reproduce the results, open `RF_PA_wrk` in Keysight ADS and run the power and frequency sweeps on the final layout.

## Requirements

- Keysight ADS with Momentum RF
- The BLP0408H9S30 large-signal model

## Author

Michael Antwi, Telecommunication Engineering, KNUST
