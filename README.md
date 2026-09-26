![enter image description here](https://files.catbox.moe/t88jye.png)
# WIF converter (offline)

A single-page tool that converts a private key in hex to WIF, compressed and uncompressed, and shows the matching
public key and addresses for **Bitcoin, Bitcoin testnet, Litecoin, Dogecoin and Dash**:

- legacy (P2PKH: `1…`, `L…`, `D…`, `X…`)
- native SegWit (P2WPKH: `bc1q…`, `tb1q…`, `ltc1q…`) where the coin supports it
- nested SegWit (P2SH-P2WPKH: `3…`, `2…`, `M…`) where the coin supports it

**Use it:** https://rycpot.github.io/wif-converter/, or better, download `index.html` and open it with the network off.

- Everything runs in the page: SHA-256, RIPEMD-160, Base58Check, Bech32 and secp256k1 are written out in plain
  JavaScript. No libraries, no network requests. The only thing stored is which coin you picked (in your browser).
- Prefixes come from each coin's own `chainparams.cpp`.
- Checked against bitcoinjs-lib (every output, 5 coins, about 1,000 random keys), Node.js's crypto (hashes), and
  published vectors (BIP173, the Bitcoin wiki WIF example, puzzle #66's address).

**For a real key:** use a saved copy of `index.html` with Wi-Fi off, check that an address matches the one holding the
coins, import the WIF from the same group (compressed or uncompressed), then close the tab. Don't paste a real key into
any website, including this one.
