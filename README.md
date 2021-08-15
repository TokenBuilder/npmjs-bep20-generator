# Binance Smart Chain BEP-20 Token Generator

This packable allows you to either embed a custom token generator on your React web application or supply parameters to programmatically create a new token.

## Installation

```bash
yarn add bep20-generator
```

## Token Creator React Component

You can import the `EmbeddedTokenGenerator` from the `bep20-generator` package to embed a full page token generator in your page while supplying your own ethereum address for affiliate fees, if any.

This embedded tool allows you to create many different types of token.

```jsx
import { EmbeddedTokenGenerator } from "bep20-generator";

const Example = () => {
  return (
    <EmbeddedTokenGenerator affiliate="0x002fd03eeC510cC10Df778ef87a8C6f51FfE3F02" />
  );
};

export default Example;
```

## Programmatic Token Generation

Currently this method only allows creating fixed-supply tokens with no minting capabilities.

```jsx
import { createBep20Token } from "bep20-generator";

await createBep20Token({
  name: "MyToken",
  symbol: "MTK",
  supply: 1000000,
  web3: ethersInstance, // Must be an initialized ethers.js provider on chain 1
});
```

## Credit

This tool utilizes libraries and toolkit from [Create My Token](https://www.createmytoken.com/) and [Metacrypt](https://www.metacrypt.org/).
