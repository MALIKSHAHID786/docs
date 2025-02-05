---
title: "Streams API"
sidebar_label: "Overview"
slug: "/streams-api/evm"
description: "Stream blockchain data into your backend via webhooks. Ethereum, Polygon, Avalanche, BNB Chain, Fantom, Cronos, Arbitrum, Ronin and testnets are supported. More networks to be added soon."
sidebar_position: 1
image: "/img/content/e1ac10a-d06bbe5-Moralis-Streams-API.webp"
sidebar_class_name: "sidebar-overview"
---

![](/img/content/d06bbe5-Moralis-Streams-API.webp)

:::tip
You can learn by [watching the Streams API Demo](#demos).
:::

## What is the Streams API?

With Streams API you can listen for real time events on chain, you can listen for when a new event is emitted in your contract or for when a walltet address does an NFT transfer or a transaction. You can also get notifications for native and internal transactions. You will receive webhook requests for those events specific to your stream configuration.

```mermaid
graph TD;
    A[ETH Node] -- New Block --> D(Streams API);
    B[Polygon Node] -- New Block --> D;
    C[BNB Node] -- New Block --> D;
    D --> E{Your Stream};
    E -- Webhook --> F[Your Server];
```

## Working With Webhooks

Webhooks allow you to receive real-time notifications for events that are happening in relation to your application. When a supported event occurs, a real-time notification is posted, including a data payload, via HTTP POST method to a custom URL you provide.

## Streams API features

- Get blockchain events streamed to your backend directly in real-time
- Listen to wallets or contract events, or both with multiple streams
- Track one address or millions with just one stream, it is up to you
- Fully customize your streams using filters, you want to only want to listen to transactions over 1000 USDT, no problem
- Listen for events from all contract addresses
- Add your custom ABI and choose which events you want to listen too
- and much more...

## Popular use cases

- Realtime Wallet notifications (monitor when an address sends, receives, stakes, swaps, or burns assets)
- Monitor assets (get notifications when an asset is being sent, received, staked, swapped, or burned)
- In game specific events, for example when a battle starts in your web3 game
- Token sales (get notifications for when someone participates in your token sale)
- Any other smart contract event fires on-chain based on your filters

### Listen to all addresses use cases

- Listen to all NFT contract transfers [tutorial](/streams-api/evm/how-to-listen-all-nft-transfers)
- Listen to all events from new contracts specific to a contract factory [tutorial](/streams-api/evm/how-to-listen-all-events-from-a-contract-factory)
- Listen to all NFT contracts transfers where sender is a specific address [tutorial](/streams-api/evm/how-to-listen-to-all-nft-transfers-sent-from-a-specific-address)
- Listen to all ERC20 contract transfers where sender is a specific address and number of coins transferred is over 1000 [tutorial](/streams-api/evm/how-to-listen-to-all-erc20-contract-transfers-over-certain-amount-sent-by-specific-address)

## Run Smart Contract Functions

- Run smart contract functions against Events [Read more here!](/streams-api/evm/triggers)

## Get Native Balances

- Get Native Balances for addresses! [Read more here!](/streams-api/evm/get-native-balances)

## High reliability

- Moralis guarantees 100% delivery of Webhooks
- If your service is down Moralis will retry to send the webhook in intervals
- If your service fails to receive the webhooks you can manually replay

## Supported chains

import { EVMStreamChainData } from '@site/src/components/SupportedChains';

<EVMStreamChainData/>

:::info Reorgnization Before Confirmation
Until a block is confirmed, it is possible that a re-organization of the chain may occur, invalidating some information. If a re-organization does occur before a block is confirmed, the information associated with the block is deleted and the updated block is inserted in its place.
:::

## To get started, check the following tutorials:

- [Your First Stream using NodeJS SDK](/streams-api/evm/using-node-js-sdk)
- [Your First Stream using WebUI](/streams-api/evm/using-webui)
- You can also use the [Swagger Interface](https://api.moralis-streams.com/api-docs/) directly.

## How Streams are priced

See [Records and pricing](/streams-api/evm/records-and-pricing)

## Learn more advanced applications of Streams

- [Monitor specific NFTs](/streams-api/evm/how-to-monitor-specific-nfts)
- [Monitor for Burn/Mint Tokens](/streams-api/evm/how-to-monitor-for-erc20-token-burns-or-mints)
- [Monitor ENS Name Registrations](/streams-api/evm/how-to-monitor-ens-domain-registrations)

## Demos

https://www.youtube.com/watch?v=pnmVhxdUBao
