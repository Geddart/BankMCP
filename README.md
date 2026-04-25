# BankMCP

A personal **Model Context Protocol** (MCP) server providing read-only access to my own bank accounts. Built for a single user — me. The source code is kept private; this repository hosts only the privacy notice and project description, which Enable Banking requires for production-app registration.

## Privacy Notice

This application is a personal tool used solely by **Sascha Geddert** (`sascha@geddart.de`) to read his own bank-account information through Enable Banking's Open Banking API.

- **Single-user, single-tenant.** No third-party users are onboarded. The application accesses only the developer's own bank accounts, authenticated by the developer.
- **No data collection or sharing.** No bank data, transaction data, account identifiers, or credentials are transmitted to, collected by, or shared with any third party. All data flows directly from the user's bank, through Enable Banking's licensed AISP service, to the user's local machine.
- **Local-only storage.** Account data is stored exclusively in an SQLite database on the developer's local machine. The database never leaves the device.
- **No analytics, telemetry, or remote logging.** There are no servers, hosted endpoints, or cloud components.
- **Credentials in OS-managed vaults.** RSA private keys, bank PINs, OAuth refresh tokens, and similar secrets are stored in the operating system's native credential manager (Windows Credential Manager via the `keyring` library). They are never written to plaintext files, source code, or logs.
- **Logs redact secrets.** Application logs strip IBANs (partial-mask), PINs, and authentication tokens before any disk write.

## Scope

The application supports:

- Reading account balances
- Listing and searching transaction history
- Aggregating transactions for personal bookkeeping

The application does **not** initiate payments or write to any bank account in version 1. Future versions may add payment initiation strictly on the developer's own accounts, with per-transfer strong customer authentication (SCA) — never against accounts of any third party.

## Compliance

This project does not act as a Third-Party Provider (TPP) under PSD2. The developer accesses only his own accounts via licensed Open Banking interfaces (Enable Banking Oy as registered AISP) and his banks' own customer interfaces. No BaFin license is required for individual access to one's own accounts.

## Contact

Privacy questions, security concerns, takedown requests:
**sascha@geddart.de**

## Source Code

The application's source code is kept in a private repository. This public repository exists solely to host the privacy notice URL required by Enable Banking for production-application registration.

---

*Last updated: 2026-04-25*
