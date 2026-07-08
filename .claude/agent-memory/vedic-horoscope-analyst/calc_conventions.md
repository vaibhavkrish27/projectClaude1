---
name: calc-conventions
description: Default calculation conventions used for Vedic readings in this project (ayanamsa, house system, confidence tagging)
metadata:
  type: reference
---

Default calculation conventions for readings produced in this project:

- **Ayanamsa**: Lahiri (Chitrapaksha) is the default sidereal ayanamsa unless the user requests otherwise. For late-1980s birth dates, Lahiri ayanamsa is roughly 23.6-23.7 degrees.
- **House system**: Whole-sign houses counted from the Ascendant sign (not degree-based Placidus/Koch cusps), matching traditional Vedic (Parashari) practice.
- **Confidence tagging**: When exact ephemeris software isn't available and planetary degrees are estimated/interpolated, explicitly tag each placement with a confidence level (high/moderate/lower). Sun, Moon, and slow movers (Jupiter, Saturn) near mid-sign are usually high-confidence from date alone. Mercury, Venus, Mars, and the lunar nodes (Rahu/Ketu) can shift sign near sign-boundary dates and need more careful checking — flag these for the user to verify against precise ephemeris before dating specific events off them.
- When the Ascendant degree is very close to a sign boundary (e.g., within ~1 degree), explicitly note this as a "locked" or "borderline" ascendant and state whether the reading holds across common ayanamsa variants.

See [[places-lucknow]] for a worked example (Vaibhav Krishna chart) using these conventions.

**Vimshottari antardasha calculation method** (reusable for any chart): full mahadasha
periods total 120 years across 9 lords - Ketu 7, Venus 20, Sun 6, Moon 10, Mars 7,
Rahu 18, Jupiter 16, Saturn 19, Mercury 17. Antardasha order within any mahadasha
starts at the mahadasha lord itself and proceeds in the same fixed sequence
(Ketu-Venus-Sun-Moon-Mars-Rahu-Jupiter-Saturn-Mercury), wrapping around. Each
antardasha's duration = (antardasha lord's own full years / 120) x mahadasha lord's
full years. Treat computed antardasha date boundaries as moderate confidence
(proportional math, not exact-ephemeris verified) and note that uncertainty compounds
for sub-periods more than ~10 years in the future - flag those as directional/
approximate rather than precise-to-the-month. Used for the detailed career-timing
follow-up in the Vaibhav Krishna file (see [[places-lucknow]]).
