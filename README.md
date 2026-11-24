# Fund Grow — Banking Interface Prototype

Fund Grow is a front-end banking dashboard concept built to demonstrate responsive interface design, account screens and common financial-app workflows.

> **Demo only.** This repository is not a bank, payment processor, deposit-taking institution or investment service. It is not approved for real deposits, transfers, cards or financial transactions. Any displayed balance or transaction data is sample/demo data.

## Interface features

- Landing page and product overview
- Email/password and Google sign-in interface
- Account dashboard
- Deposit and transfer screens (workflow demonstrations only)
- Card visual and account statement screens
- Support, privacy and terms pages
- Responsive layouts and interactive UI components

## Technology

- HTML5 and CSS3
- Vanilla JavaScript with ES modules
- Firebase Authentication
- Cloud Firestore integration in the prototype

## Local preview

Serve the repository through a local HTTP server:

```bash
python -m http.server 8000
```

Open `http://localhost:8000/` in a browser. Firebase-backed screens require a configured Firebase project.

## Important implementation limitations

The current deposit flow writes a balance increase from client-side code, which is not an acceptable design for real money. The current transfer flow debits the sender but does not atomically credit the recipient. Firestore security rules were not present in this repository and have not been verified.

Do not use this project with real funds or personal financial data. A production implementation would require trusted server-side transaction processing, strict Firestore rules, atomic ledger entries, idempotency, reconciliation, audit logging, fraud controls and independent security review.

## Portfolio positioning

This project demonstrates front-end design and prototyping of a banking-style application. It does not claim real customers, a live bank, production payment rails, verified balances or regulated financial services.
