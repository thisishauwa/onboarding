# Famasi Onboarding Flow Prototype (Figma Hi-Fi & Lo-Fi Iteration)

An interactive, high-fidelity and lo-fi prototype for the Famasi onboarding experience implementing Figma designs and UX decisions.

## Key UX Principles & Decisions Implemented

1. **One Action / Question Per Screen**:
   - Replaced multi-field long forms with focused, single-question screens (Sex, Date of Birth, Location, Goals, Who do you manage for).
   - Prevents cognitive overwhelm and drop-off while speeding up user completion time.

2. **Account Manager Profile Framing (Screens 4, 5, 7)**:
   - Clarifies why the primary user's details are collected even when managing for a loved one.
   - Sets up the primary account coordinator records, assigns the local pharmacy network, and ensures clinical safety if medications are added for themselves.

3. **Contextual Cart Payment & HMO Alpha Checkout (Screen 16)**:
   - Payment and insurance selection are relocated from upfront profile setup directly into the Cart Review (Screen 16).
   - Users choose how to pay (Card/Transfer vs. HMO Reimbursement with itemized claims receipts) in context when viewing their order total and 10% welcome discount.

4. **Actionable Goal Configuration (Screen 8D)**:
   - Redesigned with clean, high-utility feature cards that activate platform capabilities:
     - Medication delivery & refills (`Enables 3-Day Refill Alerts`)
     - Chronic condition management (`Enables Health Vitals Log`)
     - Family care management (`Enables Multi-City Family Cabinets`)
     - Pharmacist consultations (`Enables 1-on-1 WhatsApp Clinical Desk`)
   - Selections dynamically customize the user's dashboard widgets on Screen 21.

5. **Streamlined Family Setup (No Redundant Priority Screen)**:
   - When users select family members on Screen 10 (e.g. Dad, Mum), clicking Continue drops them directly into setting up the first person in order.
   - Eliminates the redundant care plan priority screen.

6. **Medication Addition Flow with Integrated Figma Design (Screen 15)**:
   - Seamlessly blends the standard onboarding page structure with Figma design tokens (`Node 24133:15811`):
     - Question & eyebrow: **"What is Dad getting?"** / **"What are you getting?"**
     - Focused search box with `#5da5f6` border & `0 0 0 4px #e7f2fe` primary-50 glow effect and clear button.
     - Interactive filter pills: **💡 Suggested** and **📋 Plans**.
     - Curated plan items with `🪄 Curated Plan` badges and acute medication items.

7. **Whole-Cart Decision (Convert to Order vs. Order Later)**:
   - When reviewing medications (Screen 16), the decision applies to the entire cart as a whole rather than configuring each medication individually.
   - Users view a single consolidated cart summary (items, dosages, delivery destination, 10% welcome discount breakdown, and automated refill reminder enrollment).

8. **Returning User History Fast-Track & Unified Summary (Screens 2C, 2D, 18)**:
   - Entering a phone number with existing pharmacy orders offers 1-tap import on Screen 2C and family attribution on Screen 2D.
   - Bypasses redundant clinical loops: on Screen 18, imported family members (Dad and Mum) are presented in a unified summary, leading straight to account security without forcing a redundant 7-step questionnaire for Mum.

9. **Loop Fatigue Prevention for New Multi-Member Accounts (Screen 18)**:
   - For new users setting up multiple family members, the primary CTA is **Complete & Secure Account**, with an optional secondary action to set up the next person now. Users can secure their account immediately and configure other family members later from their dashboard.

10. **Clean, Focused SMS Verification (Screen 20)**:
    - Simplified to a pure 4-digit SMS OTP screen with auto-advancing inputs and demo quick-fill, removing distracting secondary inputs and ambiguous buttons.

11. **Fixed Desktop Phone Mockup & Edge-to-Edge Mobile Prototype**:
    - **Desktop**: Fixed phone mock-up (`390px × 844px`), scrolling content body (`.screen-body`), permanently fixed bottom action buttons (`.screen-footer-pinned`).
    - **Mobile Breakpoint (`<= 640px`)**: The phone mockup chrome is removed; the prototype fills 100vw × 100dvh edge-to-edge as a native mobile app directly on the screen with a discreet bottom-sheet screen switcher accessible by tapping the progress bar.

---

## Screen Flow Architecture

```
Account & Household Setup
  ├── 1. Welcome & Value Proposition (Figma 24192:19137)
  ├── 2. What should we call you? (Name only)
  ├── 2B. Can we have your phone number? (Phone only + Persona Toggle)
  │     ├── [Returning User Path]
  │     │     ├── 2C. Order History Found (5 Orders & Personalization Consent)
  │     │     └── 2D. Family Attribution (Multi-Person Caregiver Edge Case)
  │     └── [New User Path] (Direct to Account Manager Profile)
  ├── 4. Account Manager Profile Intro (Securing family dashboard)
  ├── 5. What is your sex? (Account Manager Records)
  ├── 6. When were you born? (Smooth iOS Wheel Picker)
  ├── 6B. Full-Page Insight: Caring Across Distance (Noom pattern)
  ├── 7. Where do you live? (Account Manager Location)
  ├── 8D. What do you want Famasi to help you do? (Actionable Feature Config)
  ├── 9. Who do you manage medication for? (Figma 24197:19891)
  ├── 10. Let's add the people you manage (Figma 24198:19984)
  └── 10B. Member Accordion Details (Mama / DOB) (Figma 24199:20069)

Direct Person Clinical & Medication Setup (Dad)
  ├── 12. Allergies Safety Check
  ├── 13. Chronic Conditions Check
  ├── 14. Delivery Address Check (Kaduna)
  ├── 15. What are you getting? (Figma 24133:15811 & Curated Plans)
  ├── 16. Cart Review + Contextual Payment/HMO + Auto-Refill Enrollment
  ├── 17. Suggested Health Goals (Profile-tailored)
  └── 18. Unified Family Summary (Fast-track to OTP)

Verification & Home Dashboard
  ├── 20. Confirm Account & SMS OTP Verification (Clean 4-digit code)
  └── 21. Populated Home (Dashboard — Active Features, Tracking, Family Cabinets)
```

## Running Locally

Open `index.html` directly in any web browser:
```bash
open index.html
```
No build steps, node servers, or external bundlers required. All interactions, search filters, modal sheets, and transitions run natively in vanilla HTML/CSS/JS.
