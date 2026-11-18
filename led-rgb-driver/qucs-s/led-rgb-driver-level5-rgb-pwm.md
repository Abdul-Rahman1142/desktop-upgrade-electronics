# Level 5: 3-Channel Independent PWM RGB Driver

## Status
Not started.

## Planned approach
Three independent instances of the Level 4 buck/PWM driver, one per color channel,
each with its own duty cycle control, so red, green and blue can be mixed to any
color and brightness independently. This matches the function of a commercial
RGB LED driver IC (e.g. the class of chips used in addressable RGB strips).

## What this will demonstrate over Level 4
Multi-channel independent control, the complete, market-comparable version of this
project.