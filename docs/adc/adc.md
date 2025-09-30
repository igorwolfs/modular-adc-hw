# ADC

The ADC used will be the ad131m04, in a single-ended configuration.

The decision to step away from a differential configuration, comes from the realization that
- Transport of high frequency analog differential signals not meant for communication involves more issues (impedance matching + shielding)
- Differential configurations are harder to test (more expensive test equipment)
- Differential configurations are harder to route (2 wires vs 1)

Which is why we'll change the configuration.

