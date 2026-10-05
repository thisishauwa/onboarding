# Famasi Onboarding Flow Prototype (Figma Hi-Fi & Lo-Fi Iteration)

An interactive, high-fidelity and lo-fi prototype for the Famasi onboarding experience implementing Figma designs and UX decisions.

## Key UX Principles & Decisions Implemented

1. **One Action / Question Per Screen**:
   - Replaced multi-field long forms with focused, single-question screens (Sex, Date of Birth, Location, Payment Method, Goals, Who do you manage for).
   - Prevents cognitive overwhelm and drop-off while speeding up user completion time.

2. **Upfront Account Creation (Lightweight Contact)**:
   - Screen 2 collects Name only; Screen 2B collects Phone only.
   - Preserves full profile creation and password-free OTP verification until after the care plan is organized.

3. **"What Do You Want Famasi to Help You Do?" (Screen 8D)**:
   - Dedicated customization screen prior to family setup allowing users to choose their primary health objectives (Medication delivery & refills, Chronic condition management, Family care management, Pharmacist consultations).
   - Minimalist, emoji-free card options aligned with the Figma family design language.

4. **Multi-Select Payment & HMO Alpha Flow**:
   - Allows multi-selection of payment methods (Self-pay, HMO, Employer, Someone else).
   - If HMO is selected, transitions to HMO provider selection (Reliance, AXA Mansard, Hygeia, etc.) followed by the **Alpha Early Access notice** informing users of pre-formatted reimbursement sheets.

5. **Streamlined Family Setup (No Redundant Priority Screen)**:
   - When users select family members on Screen 10 (e.g. Dad, Mum), clicking Continue drops them directly into setting up the first person in order (Dad's clinical checks and medication order).
   - Eliminates the redundant care plan priority screen.

6. **Medication Addition Flow with Integrated Figma Design (Screen 15)**:
   - Seamlessly blends the standard onboarding page structure with Figma design tokens (`Node 24133:15811`):
     - Question & eyebrow: **"What is Dad getting?"** / **"What are you getting?"**
     - Focused search box with `#5da5f6` border & `0 0 0 4px #e7f2fe` primary-50 glow effect and clear button.
     - Interactive filter pills: **💡 Suggested** and **📋 Plans**.
     - Curated plan items with `🪄 Curated Plan` badges (PMOS, Pregnancy Care, Hypertension Care Plan, etc.) and acute medication items.
     - Preserves the standard onboarding footer navigation (`Review Dad’s Medications (count)` and `Skip medication entry for now`).

7. **Whole-Cart Decision (Convert to Order vs. Order Later)**:
   - When reviewing medications (Screen 16), the decision applies to the entire cart as a whole rather than configuring each medication individually.
   - Users view a single consolidated cart summary (items, dosages, delivery destination, 10% welcome discount breakdown, and automated refill reminder enrollment).
   - The user selects between **Convert to Order** (dispatch immediately) and **Order Later** (save to digital cabinet with smart refill alerts), with the footer button adapting directly (`Convert to Order` or `Confirm & Continue (Order Later)`).

8. **Fixed Desktop Phone Mockup & Edge-to-Edge Mobile Prototype**:
   - **Desktop**: Fixed phone mock-up (`390px × 844px`), scrolling content body (`.screen-body`), permanently fixed bottom action buttons (`.screen-footer-pinned`).
   - **Mobile Breakpoint (`<= 640px`)**: The phone mockup chrome (bezels, box-shadows, fake status bar, home bar) is completely removed; the prototype fills 100vw × 100dvh edge-to-edge as a native mobile app directly on the screen with a discreet bottom-sheet screen switcher accessible by tapping the progress bar.

9. **Returning Pharmacy Customer Personalization (Screens 2C & 2D)**:
   - **New to App ≠ New to Pharmacy**: Customers who previously purchased through Famasi's retail branches, website, or concierge WhatsApp have established clinical records. Forcing them through generic onboarding creates friction and breaks trust.
   - **Dynamic Recognition**: Entering their phone number on Screen 2B matches existing pharmacy records and displays Screen 2C: *"We found 5 orders attached to this number. Would you like to import and personalize?"*
   - **Multi-Person Caregiver Attribution Edge Case**: Solves the critical edge case where an account holder (e.g. adult daughter) manages orders for multiple family members across cities. Famasi auto-groups past orders by recipient (Dad in Kaduna with Amlodipine/Metformin, Mum in Lagos with Losartan, Self in Lagos) on Screen 2D so medications are never clinically misattributed.
   - **"It Just Works"**: Pre-fills known fields (medications, delivery locations, payment preferences) while leaving unknowns (exact DOB, safety flags) for quick confirmation. Bypasses 12 repetitive screens and fast-tracks the user directly to medication review and smart refills.

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
  │     └── [New User Path]
  │           └── 3. Trust & 300k Community Reviews (Figma 24186:18430)
  ├── 4. Personalisation Intro — "Now it's your turn" (Figma 24192:19394)
  ├── 5. What is your sex? (Figma 24195:19532)
  ├── 6. When were you born? (Figma 24195:19608 — Smooth iOS Wheel Picker)
  ├── 6B. Full-Page Insight: Caring Across Distance (Noom pattern)
  ├── 7. Where do you live? (Delivery Address only) (Figma 24197:19705)
  ├── 8. How will you pay? Multi-select (Figma 24197:19791)
  ├── 8B. HMO Provider Selection (Reliance, AXA Mansard, Hygeia...)
  ├── 8C. HMO Alpha Early Access Notice
  ├── 8D. What do you want Famasi to help you do?
  ├── 9. Who do you manage medication for? (Figma 24197:19891)
  ├── 10. Let's add the people you manage (Figma 24198:19984)
  └── 10B. Member Accordion Details (Mama / DOB) (Figma 24199:20069)

Direct Person Clinical & Medication Setup (Dad)
  ├── 12. Allergies Safety Check
  ├── 13. Chronic Conditions Check
  ├── 14. Delivery Address Check (Kaduna)
  ├── 15. What are you getting? (Figma 24133:15811 & 24133:15809 — Curated Plans & Order Modal)
  ├── 16. Convert to Order / Order Later (Auto-Refills)
  ├── 17. Suggested Health Goals (Profile-tailored)
  └── 18. Person Setup Summary & Loop (Mum next or finish)

Verification & Home Dashboard
  ├── 19. Caregiver Cohort Evidence
  ├── 20. Confirm Account & OTP Verification (Skippable Email)
  └── 21. Populated Home (Dashboard — Circle, Orders, Cabinet)
```

## Running Locally

Open `index.html` directly in any web browser:
```bash
open index.html
```
No build steps, node servers, or external bundlers required. All interactions, search filters, modal sheets, and transitions run natively in vanilla HTML/CSS/JS.
