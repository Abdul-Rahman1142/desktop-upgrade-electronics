# Level 1: Resistor-Limited Driver

## Status
In progress. Requirement and R-channel calculation done, schematic built in Qucs-S,
diode orientation corrected, simulation pending. G/B channel resistor values pending
datasheet lookup.

## Requirement
- Supply voltage: 12V (chosen to match a real PC 12V rail, same supply used across all
  5 circuits in this repo)
- 3 independent channels: Red, Green, Blue, each on its own resistor
- Target forward current: 20mA per channel (standard LED rating, adjust per actual
  part datasheet)

## Component choices and why
- **Resistor per channel**, not one shared resistor: each LED color has a different
  forward voltage, so each needs its own resistor value to hit the same 20mA target.
- **Generic SPICE diode model** (Is=1e-15A, N=1, Cj0=10fF) in Qucs-S in place of an
  LED-specific model, since Level 1 only needs to confirm the resistor's current-setting
  behavior, not exact LED nonlinearity.

## Thought process
A single resistor is the simplest possible current limiter: Ohm's law sets the current
once Vf is known. The trade-off, made explicit here on purpose, is that at 12V most of
the supply voltage is wasted as heat in the resistor rather than doing useful work in
the LED. That inefficiency is exactly why Levels 2 through 5 exist, each trades added
complexity for better efficiency, dimming capability, or both.

## Hand calculation (Red channel, Vf = 2.0V)
R = (Vsupply - Vf) / If = (12 - 2.0) / 0.02 = 500 ohm
P = I^2 x R = (0.02)^2 x 500 = 0.2W -> use a 0.5W resistor for margin

## Hand calculation (Green channel)
Pending: look up actual LED part's Vf at 20mA, typical range 2.0-3.2V depending on part.

## Hand calculation (Blue channel)
Pending: look up actual LED part's Vf at 20mA, typical range 3.0-3.4V depending on part.

## Simulation and result
Pending. Diode was initially placed backwards (cathode facing the supply), corrected
by mirroring the component. DC operating point simulation to confirm ~20mA through the
resistor is the next step.

## What you'd change
Efficiency is poor at 12V since most voltage drops across the resistor as heat. No
dimming capability. Level 2 replaces the resistor with a BJT current source for better
regulation against supply variation.