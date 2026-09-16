# Famasi Onboarding Flow Prototype

An interactive, wireframe flow prototype for Famasi onboarding.

## Architecture

```
Universal Onboarding (Screens 1–3 only)
  ├── 1. Who do you manage medication for? (+ lightweight family start if needed)
  ├── 2. Goals (Personalises without trapping the user)
  └── 3. What would you like to do first?
        │
        ├── Branch A: Order medication now (Pharmacy basket, rules, destination vs user location, refill hook, order value moment)
        ├── Branch B: Set up a regular refill (Supply replacement cadence, destination, refill value moment)
        ├── Branch C: Add medication to Famasi (Save for later with zero purchase pressure)
        ├── Branch D: Set up medication reminders (Dose schedule, notifications)
        └── Branch E: Track a health number (Clinical metric, neutral baseline)
        │
        ▼
Value Moment Revealed → Deferred Account Creation → Populated Home (Personalisation creating continuity)
```

## Running Locally

Open `index.html` directly in any web browser:
```bash
open index.html
```
No build steps, package managers, or server installations are required.
