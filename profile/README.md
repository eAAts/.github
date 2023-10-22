# eAAts Delivery Platform

eAAts maintains the user experience of traditional delivery platforms while utilizing blockchain technology to reduce delivery costs and support a variety of cryptocurrency payments, providing an innovative service.

## Core Features

### 1. Social Login & Gas Fee Delegation

- Utilizes Safe AA SDK’s `Auth` feature to offer easy login through social network accounts.
- `Protocol`, `Onramp`, and `Relay` features allow users to receive gas fee delegation, so they won't feel the burden of transaction costs.

### 2. Support for Various Cryptocurrency Payments

- Users can deposit cryptocurrencies into their `SafeWallet` and make payments with various cryptocurrencies.

### 3. Bridge

- The application is based on the Polygon mainnet and implements bridges to utilize assets from Mantle, Scroll, and Filecoin chains.

### 4. Automated Payments

- `AbstractedWallet` is deployed on Mantle, Scroll, and Filecoin chains. Each user has their own `AbstractedWallet` to facilitate automated payments.
- Leverages Chainlink’s `Automation` feature to detect order completion events and utilize the `Functions` feature to proceed with automated payments via contracts on the Polygon chain.

### 5. NFT Comments & Coupons

- Users can leave comments after payment, which will be converted into NFTs.
- These NFTs can be verified on OpenSea and may be used as coupons in the future.

## Flow Chart
- Tool : SAFE, Chainlink, Filecoin(IPFS- nftStorage & web3.stroage), PushProtocol, theGraph
- Network : Polygon, Mantle, Scroll, Filecoin

```mermaid
graph TD

    A[Social Login & Gas Fee Delegation => SAFE AA SDK]
    B[Support for Various Cryptocurrency Payments => SAFE AA SDK]
    C[Bridge - Polygon, Mantle, Scroll, Filecoin => Chainlink automation & functions]
    D[Automated Payments => Chainlink automation & functions]
    E[NFT Comments & Coupons => FileCoin]
    F[Alarm/Notification => push protocol]
    G[Client => the graph]

    A --> B
    B -->|Deposit in SafeWallet| C
    C -->|Bridge to other chains| D
    D --> E
    E -->|Push Protocol| F
    F --> G

    subgraph Main Features
      A --> B
      B --> C
      C --> D
      D --> E
      E --> F
    end

    subgraph Chain Support
      C1((Polygon))
      C2((Mantle))
      C3((Scroll))
      C4((Filecoin))
      C --> C1
      C --> C2
      C --> C3
      C --> C4
    end

    subgraph NFT Utilities
      E1[Comments as NFTs]
      E2[Verified on OpenSea]
      E3[Coupons in future]
      E4[stored in Filecoin IPFS]
      E --> E1
      E1 --> E2
      E1 --> E3
      E2 --> E4
      E3 --> E4
    end

    style A fill:#ADD8E6
    style B fill:#ADD8E6
    style C fill:#90EE90
    style D fill:#90EE90
    style E fill:#FFFF64
    style F fill:#FFB6C1
    style G fill:#C0C0C0
    style E4 fill:#FFFF64

    style C1 fill:#C0C0C0, fontColor: #fff
    style C2 fill:#FF6F64, fontColor:#fff
    style C3 fill:#FF2F64, fontColor:#fff
    style C4 fill:#FFFF64
```
