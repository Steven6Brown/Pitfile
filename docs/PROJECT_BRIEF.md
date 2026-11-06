# Pitfile — Project Brief

Use together with the *Aquila Digital — Mobile & Web App Build Standards*. This brief is the product source of truth; anything not listed under Confirmed is not decided.

## 1. Project overview
Pitfile is an application for Aquila Digital LLC. Photograph a car service receipt and the app logs the date, mileage and work done, reminds you when the next service is due, and builds a clean service history you can hand to a buyer.

- **Platform scope:** iOS (assumed: see below).
- **Primary users:** Car owners who forget service intervals and can't find their records when selling.
- **Primary user outcome:** Never miss a service, and hand over a complete service history when the car is sold.

## 2. Confirmed requirements
- Selected from the 2026-10-14 brainstorm; working title "Glovebox" (already an App Store title, so renamed Pitfile).
- Core loop: photograph receipt → on-device reading of date, mileage and work done → reminders → shareable service history.

## 3. Reasonable assumptions (change freely)
- Standalone app, separate from Dockett. (It was raised that this could instead be a Dockett mode; revisit if the two end up sharing most of their code.)
- iOS first, SwiftUI, iOS 17+; Apple Vision for on-device text recognition; local storage; no account.
- OCR output is untrusted: the owner confirms every extracted field before saving.
- Service intervals are set by the owner (editable defaults), not invented by the app.

## 4. Open questions (decide before building the affected part)
- This category is crowded with car-maintenance log apps. What is the clear difference (receipt photo first, privacy, clean buyer-ready history)?
- Reminders by date and by mileage: how does the app know the current mileage (owner updates it, odometer photo, or an estimate from average use)?
- Where do default service intervals come from? Manufacturer schedules are not to be invented; user-entered only, or a vetted source?
- Optional recall lookup by VIN uses a public government API and needs the network: in v1 or later?
- Multiple vehicles in v1?
- Export format for the buyer (PDF) and whether it is branded.
- Backup/sync strategy and pricing model.

## 5. Out of scope
- OBD-II or dongle integration.
- Insurance, loans or valuation.
- Fuel and trip mileage tax logs.
- A marketplace.

## 6. Project context
| Item | Value |
|---|---|
| Project type | Mobile app |
| Platform | Swift / SwiftUI, iPhone (assumed) |
| Backend | NONE |
| Database | LOCAL |
| Authentication | NONE |
| Hosting / deployment | App Store |
| Analytics | NONE |
| AI / ML | LOCAL (OCR). No cloud model. |
| Sensitive data classes | DOCUMENTS and FINANCIAL (service receipts, costs); vehicle identifiers (VIN, plate) if stored. |
| Data processing location | ON-DEVICE |

## 7. Documents to keep (per the build standards)
README.md · SECURITY.md · ARCHITECTURE.md · PRIVACY.md · TESTING.md · CHANGELOG.md · .env.example (names only)
