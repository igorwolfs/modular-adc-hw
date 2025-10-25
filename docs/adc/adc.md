# ADC

The ADC used will be the ad131m04, in a single-ended configuration.

The decision to step away from a differential configuration, comes from the realization that
- Transport of high frequency analog differential signals not meant for communication involves more issues (impedance matching + shielding)
- Differential configurations are harder to test (more expensive test equipment)
- Differential configurations are harder to route (2 wires vs 1)

Which is why we'll change the configuration.

## Pinout
- 

## Signal output
Data becomes valid at positive clock-edge + tdata_valid

- At 35 MHz (t = 28.57 ns)
	- tdata_valid: 25 ns
	- thigh: 10 ns
	- tlow: 10 ns
	- Latency: 3 cycles


Source impedance:
- Unknown, likely high impedance

## Processing chips
- If we attach 2 ADC's to a CPU, each with a 30 MHz signal it would get complicated
- Better to have an FPGA (small one) in between to switch in-betweeen
	- The only one that seems to have the relevant specs and be relatively cheap is a lattice CPLD / FPGA.
	- So use that one, combined with perhaps an QSPI / OCSTPI interface to the FPGA
	- If the OCTSPI interface is fast enough, we can even simply use 2 of them instead of the 
