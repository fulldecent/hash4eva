# hash4eva

An idealistic demonstration of what a blockchain explorer could look like if it prioritized actionable security information over raw data. This is a static HTML prototype — all data is fictional.

## See it live

https://fulldecent.github.io/hash4eva/

Or serve locally:

```sh
python3 -m http.server 5000
```

Then visit http://localhost:5000.

## Pages

- **Home** (`index.html`) — search for addresses, tokens, or contracts. Shows recently viewed accounts and the latest security incidents.
- **Account** (`account.html`) — view an address's identity, KYC trail, token holdings, NFTs, signatures, and love letters (on-chain messages).
- **Contract** (`contract.html`) — inspect a smart contract's ownership, upgrade status, audit history, and interact with its functions.
- **Transaction** (`transaction.html`) — full transaction breakdown with decoded function calls, event logs, gas analysis, and replay protection status.
- **Incidents** (`incidents.html`) — security incident tracker with timelines, affected addresses, fund flow diagrams, and aggregate loss statistics.
- **Weekly market** (`ads.html`) — sponsored project listings and token advertisements with disclosed sponsorship.
- **Followed accounts** (`following.html`) — monitor specific addresses and get notified of activity.
- **Demo scenarios** (`demos.html`) — URL parameter guide for toggling different demo states (KYC-linked, unknown, leaked key, etc.).

## What's different here

### KYC identity trail

When an account has received transfers from exchanges that require identity verification (Coinbase, Kraken, Binance), the explorer surfaces this prominently. Rather than displaying a name, it shows *which exchange knows the identity* and provides a direct "subpoena identity" button with guidance for law enforcement.

### Rug pull and asset theft buttons

For tokens held on upgradeable contracts or contracts with admin seizure functions, the explorer shows an actionable button directly on each vulnerable token. Clicking it prepares the actual blockchain transaction needed to seize or steal that asset. The transaction only succeeds if signed by the authorized account (e.g. the proxy admin or the contract owner), but anyone can click to preview the transaction data or simulate it on a forked chain.

### Liquidation value

Instead of just showing a total balance, the account page frames holdings as "liquidation value" with a one-click button to prepare a bulk transfer of all assets, broken down by category (ETH, stablecoins, NFTs, other tokens).

### On-chain messages with provenance

Love letters (zero-value transactions with calldata) are displayed with the sender, the decoded message, the chain it was sent on, and a link to the specific transaction. Hovering the timestamp shows the full ISO 8601 datetime.

### Source provenance on every data point

Every piece of displayed data includes a tooltip showing exactly where it came from — which RPC call, which event log, which API. Nothing is presented without attribution.
