# Home Assistant Automations

Automations from my self-hosted Home Assistant setup.

## Automations

### Gym AC Temperature Control
File: automations/gym-ac-temperature-control.yaml

Keeps the gym comfortable while staying out of the electric utility's time-of-use peak window.

- Turns the AC to cool when the gym temperature (an ESPHome sensor) rises above 75°F.
- Turns the AC off when the temperature drops below 71°F. The gap between the two thresholds prevents short cycling.
- Blocks cooling during peak hours (5-9pm Monday to Saturday). Sundays have no peak window.
- Forces the AC off at 5pm and re-checks at 9pm, so it never runs through peak without a fresh threshold crossing.

## Setup notes
- Requires Home Assistant 2024.10 or later (uses the triggers/actions syntax).
- Replace the entity IDs (sensor.gym_temperature and climate.gym_ac) with your own.
- Adjust the thresholds and the peak window to match your utility rate plan.
