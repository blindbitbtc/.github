# BlindBit


BlindBit is a suite of software for (almost) all things Silent Payments.
Blindbit covers an Indexer, a remote scanner, several kinds of wallets and a couple of libraries.

### Components
#### Programs
- [BlindBit Oracle (Indexer)](https://github.com/setavenger/blindbit-oracle)
- [BlindBit Scan (Remote Scanner)](https://github.com/setavenger/blindbit-scan)
- [BlindBit Desktop (Wallet)](https://github.com/setavenger/blindbit-desktop)
- [BlindBit React Native App (Wallet)](https://github.com/setavenger/blindbit-spend)
- [BlindBit PWA (Wallet; forked)](https://github.com/setavenger/blindbit-pwa)
- [BlindBit Wallet CLI (Wallet)](https://github.com/setavenger/blindbit-wallet-cli)

#### Libraries
- [go-bip352](https://github.com/setavenger/go-bip352)
- [go-libsecp256k1](https://github.com/setavenger/go-libsecp256k1)
- [blindbit-lib](https://github.com/setavenger/blindbit-lib)

### General

#### Indexer
The Indexer is tailored to Silent Payments and to enable wallets and scanners to efficiently process data of blocks.

#### Scanner
The remote scanner is a very lightweight application which can be dockerised. 
It can be hosted on small home servers (Umbrel, Start9, etc.) or hosted by a third party.
It contains 

#### Wallets
Several wallets exist with different trade-offs and performance differences.

- Desktop (connects to Oracle; Internal scanning)
- CLI (Connects to remote scanner)
- Mobile Application (Connects to remote scanner)
- Progressive Web App (connects to remote scanner)

In future the Desktop wallet can be enhanced to work with a remote scanner. 
Vice verse the cli can be enhanced to do local scanning.
BlindBit Lib is the center of this change. 
It standardises logical components for handling silent payments.
Indexing, scanning, communication and spending will defined in a central place so different programs can be bootstrapped.

The PWA was forked from to enable integration with a remote scanner [(Silentium)](https://github.com/louisinger/silentium).

#### Notes
A client using Oracle does not leak any material information to the server.
The server will only know that someone is generally interested in Silent Payments data. Different trade-off models can be chosen. 
For example by querying shortened data the scanning performance increases a lot. 
But to verify the client has to pull a full block which could reveal interest for a specific block.
The interest for a specific block can be easily mitigated by always pulling full blocks or by pulling full blocks from a different source.

<img width="800" height="537" alt="blindbit-suite-overview" src="https://github.com/user-attachments/assets/00a0cd6d-ee6a-480c-8cc4-4453c0702ff7" />

