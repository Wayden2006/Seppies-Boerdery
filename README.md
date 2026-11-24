# Seppies Boerdery

Private, mobile-friendly farm management web application for **Seppies Boerdery**, built with vanilla HTML, CSS, and JavaScript backed by Firebase Authentication and Cloud Firestore.

## Features

- **Private authentication**: Email/password sign-in via Firebase Authentication for administrator-created farm accounts (no public sign-up).
- **Farm overview**: Live active animal counts (total animals, Boer goats, pigs, and sheep & chickens).
- **8 record modules** stored in Cloud Firestore (`farmRecords`):
  - **Animals**: Animal register (ID/tag, species, name, sex, breed, date of birth, lineage, source, purchase price, status, notes).
  - **Breeding**: Mating dates, expected birth dates, outcomes, and offspring counts.
  - **Health**: Vaccinations, deworming, medication, illnesses, vet visits, next due dates, and costs.
  - **Purchases & sales**: Livestock purchase and sale transactions.
  - **Weights**: Animal weight tracking (kg).
  - **Expenses**: Categorized farm expenses.
  - **Deaths & losses**: Mortality/loss tracking with reasons and estimated value.
  - **Feed stock**: Feed inventory movements (received, used, adjustments).
- **Search & filter**: Instant per-tab search across records.
- **Admin-restricted deletion in UI**: Only the configured administrator UID (`ADMIN_UID` in `index.html`) can trigger record deletion from the interface.

## Project structure

- `index.html` — Application markup, Firebase SDK setup, and client-side logic.
- `styles.css` — Responsive application styling and layout rules.
- `firestore.rules` — Cloud Firestore security rules requiring authentication for `/farmRecords/{recordId}`.
- `SETUP.md` — Step-by-step Firebase setup, hosting, and access-control guide.
- `CHANGELOG.md` — Summary of project changes.

## Getting started

See [SETUP.md](SETUP.md) for instructions on configuring Firebase Authentication, deploying `firestore.rules`, setting `firebaseConfig` in `index.html`, and hosting the static files.

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for the full history of changes.
