---
title: "How to get Sushiswap V2 pair reserves"
slug: "../how-to-get-sushiswap-v2-pair-reserves"
description: "Learn how to get the pair reserves of a given pair address from Sushiswap V2 using Moralis DeFi API."
sidebar_label: "Get Sushiswap V2 pair reserves"
---

## Step 1: Setup Moralis

Read the article [Setting Up Moralis: Getting Started](/web3-data-api/evm/get-your-api-key) and make sure to finish all the steps. Only after that you can go ahead to complete this guide.

## Step 2: Get Pair Reserves of A Sushiswap V2 Liquidity Pool

In order to get pair address of a liquidity, Moralis provides you a [getPairAddress](/web3-data-api/evm/reference/get-pair-address) endpoint to do so.

Here you'll need two parameters: `pairAddress` and `address`.

Once you've obtained the `pairAddress` and `address`, you can copy the following code:

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs groupId="programming-language">
  <TabItem value="javascript" label="index.js (JavaScript)" default>

```javascript index.js
const Moralis = require("moralis").default;
const { EvmChain } = require("@moralisweb3/common-evm-utils");

const runApp = async () => {
  await Moralis.start({
    apiKey: "YOUR_API_KEY",
    // ...and any other configuration
  });

  const pairAddress = "0xc40d16476380e4037e6b1a2594caf6a6cc8da967";

  const chain = EvmChain.ETHEREUM;

  const response = await Moralis.EvmApi.defi.getPairReserves({
    pairAddress,
    chain,
  });

  console.log(response.toJSON());
};

runApp();
```

</TabItem>
<TabItem value="typescript" label="index.ts (TypeScript)">

```typescript index.ts
import Moralis from "moralis";
import { EvmChain } from "@moralisweb3/common-evm-utils";

const runApp = async () => {
  await Moralis.start({
    apiKey: "YOUR_API_KEY",
    // ...and any other configuration
  });

  const pairAddress = "0xc40d16476380e4037e6b1a2594caf6a6cc8da967";

  const chain = EvmChain.ETHEREUM;

  const response = await Moralis.EvmApi.defi.getPairReserves({
    pairAddress,
    chain,
  });

  console.log(response.toJSON());
};

runApp();
```

</TabItem>
<TabItem value="python" label="index.py (Python)">

```python index.py
from moralis import evm_api

api_key = "YOUR_API_KEY"
params = {
    "pair_address": "0xc40d16476380e4037e6b1a2594caf6a6cc8da967",
    "chain": "eth",
    # "to_block": "",
    # "to_date": "",
}

result = evm_api.defi.get_pair_reserves(
    api_key=api_key,
    params=params,
)

print(result)

```

</TabItem>
</Tabs>

## Step 3: Run the script

import RunTheScript from '/docs/partials/\_run-the-script.mdx';

<RunTheScript />

In your terminal, you should see the following JSON response:

```json
{
  "reserve0": "164603264012529614075996",
  "reserve1": "854278497345719157300"
}
```

Congratulations 🥳 You just get the pair reserves of a Sushiswap V2 liquidity pool with just a few lines of code using the Moralis DeFi API!

## API Reference

If you want to know more details on the endpoint and optional parameters, check out:

- [getPairReserves](/web3-data-api/evm/reference/get-pair-reserves)

## Support

If you face any trouble following the tutorial, feel free to reach out to our community engineers in our [Discord](https://moralis.io/discord) or [Forum](https://forum.moralis.io) to get 24/7 developer support.
