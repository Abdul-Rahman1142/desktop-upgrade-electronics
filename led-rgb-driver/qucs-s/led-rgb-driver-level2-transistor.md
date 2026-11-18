# Level 2: BJT Current Source

## Status
Not started.

## Planned approach
Replace the passive resistor with a discrete BJT-based constant-current source. A
sense resistor sets the base-emitter voltage reference, and the transistor actively
regulates collector current to stay constant even if the supply voltage drifts,
something Level 1's resistor cannot do (its current changes if Vsupply changes).

## What this will demonstrate over Level 1
Active regulation instead of passive, better current stability, first step toward
power-efficient control.