# Famasi Onboarding Flow Prototype

An interactive, pure wireframe prototype for the Famasi onboarding experience.

## Complete 16-Step Architecture

```
Household Setup (Who exists & baseline)
  ├── 1. Welcome — Value proposition ("Order medications, stay ahead of refills, and manage medication for yourself or your family.")
  ├── 2. Basic profile — Grouped fields: DOB, Sex, Location, How you usually pay (Self-pay / Insurance / Employer / Someone else)
  ├── 3. Who do you manage medication for? — Myself / Someone else / Both (+ Add Mum/Dad/Partner/Child with name, sex, age)
  ├── 4. Goals — Multi-select priorities (Refills, Family, Reminders, Health tracking)
  └── 5. Who would you like to set up today? — Choose Me, Dad, Mum (Processed one person at a time)

Person-Level Setup & Medication Loop (e.g. Dad)
  ├── 6. Person-level health basics — Known allergies (Penicillin, Sulfa, etc.) & Long-term conditions (Hypertension, Diabetes)
  ├── 7. Add Dad's medications — Search or Prescription upload simulation + 🎁 10% first-order incentive
  ├── 8. Configure each medication — Multi-action co-existence (Order now + Refill + Reminder can all be selected together)
  ├── 9. Action details — Fine-tune Order (quantity, address, price discount), Refill (cadence), and Reminder (frequency, time)
  ├── 10. Repeat for Dad's other medications — Summary review of Dad's active meds
  ├── 11. Person-level goals with contextual education — "Since Dad manages hypertension, tracking blood pressure makes changes easier to spot"
  ├── 12. Dad setup summary — Clear reflection of created care plan
  └── 13. Next selected person — Transition to Mum (Mum's setup can be completely different)

Account, Research Insights & Populated Home
  ├── 14. Account creation / save — Create account to preserve setup and lock in the 10% discount
  ├── 15. Optional personalisation / insight gathering — Family history, pharmacy pain points, missed refill causes (skippable)
  └── 16. Populated Home (Dashboard) — Live reflection of configured household; unconfigured members show "Not set up yet"
```

## Running Locally

Open `index.html` directly in any web browser:
```bash
open index.html
```
No build steps, dependencies, or server installations are required.
