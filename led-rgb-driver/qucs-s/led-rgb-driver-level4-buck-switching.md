# Level 4: Buck/Switching Driver with PWM Dimming

## Status
Not started.

## Planned approach
Replace linear regulation (Levels 1-3, which all waste power as heat) with a switching
buck converter, so the LED is driven efficiently instead of dissipating the voltage
difference as heat. Add PWM dimming capability at this stage, since a switching
topology makes duty-cycle-based brightness control natural.

## What this will demonstrate over Level 3
Efficiency (switching vs linear), inductor/switching design, and dimming, the first
level that resembles how a real commercial LED driver works.