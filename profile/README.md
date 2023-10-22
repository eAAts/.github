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

## Used Services & Network
- Tool : SAFE(AA SDK kit), Chainlink(Functions & Automation), Filecoin(IPFS- nftStorage & web3.stroage), PushProtocol, theGraph
- Network : Polygon, Mantle, Scroll, Filecoin
* each tools and network is colored differently in this chart
```mermaid
    graph TD

    subgraph BlockChain Services
    B((SAFE AA SDK))
    C((Chainlink))
    D((FileCoin))
    E((push protocol))
    F((theGraph))
    end

    subgraph BlockChain Networks
      C1((Polygon))
      C2((Mantle))
      C3((Scroll))
      C4((Filecoin))
    end
    style B fill:#90EE90 
    style C fill:#0198E6
    style D fill:#10D8E6
    style E fill:#FFB6C1
    style F fill:#aFB6C1
    style C1 fill:#9F98E6
    style C2 fill:#FF6F64
    style C3 fill:#FF2F64
    style C4 fill:#10D8E6
```

```mermaid
graph TD

    A[eAAts Client]
    B[socialLogin & payments - SAFE AA SDK]
    C[Automated Payments with Cross Cahin Bridge - Chainlink automation & functions]
    D[NFT Comments & Coupons => FileCoin]
    E[Alarm/Notification => push protocol]
    F[Getting On chain data => the graph]

    subgraph eAAts Service
      A --> B
      B --> C
      A --> D
      A --> E
      A --> F
    end

    subgraph BlockChain Networks
      C1((Polygon))
      C2((Mantle))
      C3((Scroll))
      C4((Filecoin))
      C --> C1
      C --> C2
      C --> C3
      C --> C4
    end

    style A fill:#0FB6C1
    style B fill:#90EE90 
    style C fill:#0198E6
    style D fill:#10D8E6
    style E fill:#FFB6C1
    style F fill:#aFB6C1

    style C1 fill:#9F98E6
    style C2 fill:#FF6F64
    style C3 fill:#FF2F64
    style C4 fill:#10D8E6
```
