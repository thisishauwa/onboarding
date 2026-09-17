# Famasi Onboarding Flow Prototype

An interactive, pure wireframe prototype for the Famasi onboarding experience.

## Architecture

```
Layer 1: Household Structure & Priorities
  ├── Step 1 · Welcome (Value proposition)
  ├── Step 2 · Who do you manage medication for? (Myself / Someone else / Both)
  ├── Step 3 · Add the people you manage (Lightweight label/names: Dad, Mum, etc.)
  └── Step 4 · Goals (What would you like Famasi to help with?)

Layer 2: Person Setup Selection
  └── Step 5 · Who would you like to set up today? (Me / Dad / Mum)
        └── Configure one person at a time to keep momentum

Layer 3: Person-Level Grouped Setup & Medication Divergence
  ├── Step 6 · Grouped setup for selected person (Search or Prescription extraction simulation)
  ├── Step 7 · What should Famasi do with [Medication]?
  │     ├── 7A: Order it now (Fulfillment, destination, refill bridge)
  │     ├── 7B: Set up refills (Supply cadence, destination, recurring schedule)
  │     ├── 7C: Add to medications (Save for later without purchase friction)
  │     └── 7D: Set up reminders (Dose schedule, time, notifications)
  ├── Step 8 · Complete that person & attach operational goals (BP tracker, glucose, etc.)
  └── Step 9 · Next person in queue (Dad is done → Mum)

Completion & Continuity
  ├── Step 10 · Save your Famasi (Summary of configured care → Account creation)
  └── Step 11 · Populated Home (Dashboard reflecting real setup; unconfigured profiles marked "Not set up yet")
```

## Running Locally

Open `index.html` directly in any web browser:
```bash
open index.html
```
No build steps, dependencies, or server installations are required.
