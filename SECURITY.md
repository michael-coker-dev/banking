# Fund Grow — Security and demo status

> **Prototype only.** This project is not a bank or payment service. Do not use it for real deposits, transfers, card payments or personal financial information.

## Repository review findings

- Firebase web configuration, including the Firebase API key, is included in the frontend. Firebase web API keys are generally identifiers, not server secrets; access must be protected by Firebase Security Rules, Authentication and API restrictions.
- Firestore Security Rules are not included in this repository, so access control for the live Firebase project cannot be verified from this source.
- The deposit page currently increases a user's balance from client-side code. A browser must never be trusted to create money or credit balances.
- The transfer page currently debits the sender but does not atomically credit the recipient. It also records a transfer history item separately from the balance update.
- The homepage previously contained unsupported claims about a large member count, bank-grade security, biometric login, encryption and fraud monitoring. Those claims have been removed from the public-facing copy.
- The `about.html` file is empty and needs a proper project/about page.

## Required before any real financial use

1. Remove all client-side authority to change balances.
2. Process deposits only after a trusted payment provider confirms settlement through a verified server-side webhook.
3. Process transfers in a trusted backend using a single atomic transaction that debits and credits both accounts and writes immutable ledger entries.
4. Add strict Firestore Security Rules denying clients direct writes to balances, ledger entries and transaction status.
5. Add idempotency keys, server-side validation, audit logs, reconciliation, rate limits and fraud monitoring.
6. Review Firebase Auth settings, API-key restrictions, Firestore rules and any deployed Cloud Functions.
7. Obtain an independent security and compliance review before handling real funds or personal financial information.

## Scope

This review inspected repository source files only. It did not access or validate the live Firebase project, deployed Firestore rules, Cloud Functions, payment integrations or user data.
