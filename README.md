# XRPL Token Studio

A browser-based interface for creating, configuring, distributing, and managing
fungible issued tokens on the XRP Ledger (XRPL), with native XRPL AMM liquidity
features.

> **Status: Prototype / educational software**
>
> This project has not been independently audited. Do not use it with significant
> funds until the transaction construction, signing workflow, dependencies, and
> security model have been independently reviewed and tested.

## Features

### Network
- XRPL Mainnet
- XRPL Testnet
- XRPL Devnet

### Token / Issuer
- Configure an XRPL issuer account
- Currency code
- Transfer fee
- Tick size
- Default Ripple

### Token Operations
- Issue / send issued tokens
- Return issued tokens to issuer ("burn"/return workflow)
- Create/update trust lines

### Issuer Controls
- Require Auth
- Default Ripple
- Disallow XRP
- Global Freeze

Some issuer/account settings have important consequences and may be difficult
or impossible to reverse. Understand the XRPL documentation before changing
them.

### AMM / Liquidity
- Create an XRPL AMM
- Add liquidity
- Withdraw liquidity (prototype workflow)
- Look up AMM information
- XRP/token pools
- Token/token pools

## How XRPL Tokens Work

This application does **not** deploy a new blockchain or create an ERC-20-style
smart contract.

A traditional XRPL fungible token is represented by:
- a currency code; and
- an issuer account.

Balances are held through trust lines, and payments reference the currency and
issuer.

XRPL also provides a native decentralized exchange and automated market maker
(AMM) functionality.

## GitHub Pages

### 1. Create a repository

Create a new GitHub repository and upload:

- `index.html`
- `README.md`
- `LICENSE`
- `.gitignore`

### 2. Enable GitHub Pages

In your repository:

**Settings → Pages → Deploy from a branch**

Select your main branch and the root (`/`) directory.

GitHub will provide the published website address.

## Important Security Warning

This application can construct and sign XRPL transactions in the browser.

### Never

- Commit a seed or private key to GitHub.
- Put a real wallet seed in source code.
- Share a secret key with anyone.
- Paste a funded wallet seed into an untrusted website.
- Use the production site with significant funds without a security review.
- Assume that a token has value merely because it was created.
- Assume that adding liquidity guarantees trading volume or profit.

### Recommended workflow

1. Create a separate test wallet.
2. Use XRPL Testnet first.
3. Test every transaction and setting.
4. Verify transactions on the XRPL ledger.
5. Use a dedicated issuer account for production.
6. Keep significant treasury funds separate from the issuer.
7. Prefer hardware-wallet or secure signing workflows for valuable funds.
8. Audit the application before using it with real assets.

## Secret-Key Handling

The current application accepts the signing seed directly in the browser.

The seed should never be sent to a server or committed to the repository.

For production use, replace this approach with a secure signing architecture,
such as hardware-wallet signing or a carefully designed offline transaction
signing workflow.

## Third-Party Dependencies

The current application loads the XRPL JavaScript library from a CDN.

Because of this:

- The hosted GitHub Pages version requires an internet connection.
- CDN availability can affect the application.
- Dependency versions should be reviewed and pinned before production use.

For a fully offline/air-gapped deployment, vendor the exact dependency files locally
and verify their integrity before using them.

## Disclaimer

This software is provided for educational and development purposes.

Nothing in this project constitutes:
- financial advice;
- investment advice;
- legal advice;
- tax advice;
- a guarantee of token value;
- a guarantee of liquidity;
- a guarantee of transaction success.

Blockchain transactions can be irreversible. You are responsible for verifying
transaction details before signing and submitting them.

Use this software at your own risk.

## License

This project is released under the MIT License. See `LICENSE`.

You are free to use, modify, distribute, and commercially use the software,
subject to the MIT License terms.

## Contributing

Pull requests and improvements are welcome.

Before contributing:
- do not commit secrets;
- test on XRPL Testnet/Devnet;
- document transaction changes;
- avoid introducing dependencies without reviewing their security and license;
- clearly identify any production-risk changes.

## Security Issues

Please do not publish exploitable security vulnerabilities in public issues.

If this project is later deployed with real funds or production signing,
establish a private security-reporting process before launch.

## Useful XRPL Resources

- XRPL documentation: https://xrpl.org/docs/
- XRPL JavaScript library: https://js.xrpl.org/
- XRPL AMM documentation: https://xrpl.org/docs/concepts/tokens/decentralized-exchange/automated-market-makers
- XRPL fungible token documentation: https://xrpl.org/docs/concepts/tokens/fungible-tokens
