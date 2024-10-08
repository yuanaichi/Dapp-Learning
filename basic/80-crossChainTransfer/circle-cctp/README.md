[中文](./README-cn.md) / English

# Circle CCTP

## Overview

Cross-Chain Transfer Protocol (CCTP) is a permissionless on-chain utility that facilitates USDC transfers securely between blockchains networks via native burning and minting. Circle created it to improve capital efficiency and minimize trust requirements when using USDC across blockchain networks. CCTP enables developers to build multi-chain applications that provide secure, 1:1 transfers of USDC across blockchains for their users.

## How it works

USDC is burned on the source chain: Using an app, a user initiates a transfer of USDC from one blockchain to another, and specifies the recipient wallet address on the destination chain. The app facilitates a burn of the specified amount of USDC on the source chain.
A signed attestation is fetched from Circle: Circle observes and attests to the burn event on the source chain. The app requests the attestation from Circle, which provides authorization to mint the specified amount of USDC on the destination chain.
USDC is minted on the destination chain: The app uses the attestation to trigger the minting of USDC. The specified amount of USDC is minted on the destination chain and sent to the recipient wallet address.

Cross-Chain Transfer Protocol (CCTP) uses generalized message passing to facilitate the native burning and minting of USDC across supported blockchains, also known as domains. Message passing is a three-step process:

1. An on-chain component on source domain emits a message.
2. Circle's off-chain attestation service signs the message.
3. The on-chain component at the destination domain receives the message, and forwards the message body to the specified recipient.

![CCTP_Smart_Contract_Flow](https://files.readme.io/fcb147b-Smart_Contract_Flow.png)

## Get-Started

Transfer USDC on testnet from Ethereum to Avalanche

- install

```sh
pnpm install
```

- run script

```sh
pnpm start
```

### Script Output

```sh
Ethereum Sepolia testnet Wallet address: 0xe45d43FEb3F65B4587510A68722450b629154e6f
Avalache Fuji testnet Wallet address: 0xe45d43FEb3F65B4587510A68722450b629154e6f
sepolia test USDC balanceOf     9900000
Amount that will be transferred 100000

STEP 1: Approve messenger contract to withdraw from our active eth address
ApproveTx 0x3a6e906cfd6d6af92ae0520662dd40d126f6e8cb1e76c0b98904d2e3e5739a4f
ApproveTxReceipt:  {
  ...
}

STEP 2: Burn USDC
BurnTx 0x95d6a57ce1c4cc35e50cf7561dcbe6bc1df0924912a13d5c293d23472cad6616
BurnTxReceipt:  {
  blockHash: '0x895655d141bc5d34c49d9bf47b3678bedfd43f6f1450a9547653a4196ca3b456',
  blockNumber: 5334096n,
  contractAddress: null,
  cumulativeGasUsed: 10852617n,
  effectiveGasPrice: 5774590432n,
  from: '0xe45d43feb3f65b4587510a68722450b629154e6f',
  gasUsed: 103504n,
  logs: [
    {
      address: '0x1c7d4b196cb0c7b01d743fbc6116a902379c7238',
      topics: [Array],
      data: '0x00000000000000000000000000000000000000000000000000000000000186a0',
      blockNumber: 5334096n,
      transactionHash: '0x95d6a57ce1c4cc35e50cf7561dcbe6bc1df0924912a13d5c293d23472cad6616',
      transactionIndex: 106,
      blockHash: '0x895655d141bc5d34c49d9bf47b3678bedfd43f6f1450a9547653a4196ca3b456',
      logIndex: 171,
      removed: false
    },
    {
      address: '0x1c7d4b196cb0c7b01d743fbc6116a902379c7238',
      topics: [Array],
      data: '0x00000000000000000000000000000000000000000000000000000000000186a0',
      blockNumber: 5334096n,
      transactionHash: '0x95d6a57ce1c4cc35e50cf7561dcbe6bc1df0924912a13d5c293d23472cad6616',
      transactionIndex: 106,
      blockHash: '0x895655d141bc5d34c49d9bf47b3678bedfd43f6f1450a9547653a4196ca3b456',
      logIndex: 172,
      removed: false
    },
    {
      address: '0x1c7d4b196cb0c7b01d743fbc6116a902379c7238',
      topics: [Array],
      data: '0x00000000000000000000000000000000000000000000000000000000000186a0',
      blockNumber: 5334096n,
      transactionHash: '0x95d6a57ce1c4cc35e50cf7561dcbe6bc1df0924912a13d5c293d23472cad6616',
      transactionIndex: 106,
      blockHash: '0x895655d141bc5d34c49d9bf47b3678bedfd43f6f1450a9547653a4196ca3b456',
      logIndex: 173,
      removed: false
    },
    {
      address: '0x7865fafc2db2093669d92c0f33aeef291086befd',
      topics: [Array],
      data: '0x000000000000000000000000000000000000000000000000000000000000002000000000000000000000000000000000000000000000000000000000000000f8000000000000000000000001000000000003ec700000000000000000000000009f3b8679c73c2fef8b59b4f3444d4e156fb70aa5000000000000000000000000eb08f243e5d3fcff26a9e38ae5520a669f4019d00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001c7d4b196cb0c7b01d743fbc6116a902379c7238000000000000000000000000e45d43feb3f65b4587510a68722450b629154e6f00000000000000000000000000000000000000000000000000000000000186a0000000000000000000000000e45d43feb3f65b4587510a68722450b629154e6f0000000000000000',
      blockNumber: 5334096n,
      transactionHash: '0x95d6a57ce1c4cc35e50cf7561dcbe6bc1df0924912a13d5c293d23472cad6616',
      transactionIndex: 106,
      blockHash: '0x895655d141bc5d34c49d9bf47b3678bedfd43f6f1450a9547653a4196ca3b456',
      logIndex: 174,
      removed: false
    },
    {
      address: '0x9f3b8679c73c2fef8b59b4f3444d4e156fb70aa5',
      topics: [Array],
      data: '0x00000000000000000000000000000000000000000000000000000000000186a0000000000000000000000000e45d43feb3f65b4587510a68722450b629154e6f0000000000000000000000000000000000000000000000000000000000000001000000000000000000000000eb08f243e5d3fcff26a9e38ae5520a669f4019d00000000000000000000000000000000000000000000000000000000000000000',
      blockNumber: 5334096n,
      transactionHash: '0x95d6a57ce1c4cc35e50cf7561dcbe6bc1df0924912a13d5c293d23472cad6616',
      transactionIndex: 106,
      blockHash: '0x895655d141bc5d34c49d9bf47b3678bedfd43f6f1450a9547653a4196ca3b456',
      logIndex: 175,
      removed: false
    }
  ],
  logsBloom: '0x00000000000000000000000000000000000000000000001000000000000200002000000000000200000000000000000000002010000004000000000000000000100000000000000000000008000000000000000000000000000200020000000001000000022000400000000000000800080000000040000000100010100000000000000000101004000000000000000000000000000000000000000000200000000000000000000000000000000000040000008000000000000000000000000000000002000000000480000000000000000000000000000000000000020020000000000400000020000010000000000000080000000000000000000000000000',
  status: 'success',
  to: '0x9f3b8679c73c2fef8b59b4f3444d4e156fb70aa5',
  transactionHash: '0x95d6a57ce1c4cc35e50cf7561dcbe6bc1df0924912a13d5c293d23472cad6616',
  transactionIndex: 106,
  type: 'eip1559'
}

STEP 3: Retrieve message bytes from logs

message
0x000000000000000000000001000000000003ec700000000000000000000000009f3b8679c73c2fef8b59b4f3444d4e156fb70aa5000000000000000000000000eb08f243e5d3fcff26a9e38ae5520a669f4019d00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001c7d4b196cb0c7b01d743fbc6116a902379c7238000000000000000000000000e45d43feb3f65b4587510a68722450b629154e6f00000000000000000000000000000000000000000000000000000000000186a0000000000000000000000000e45d43feb3f65b4587510a68722450b629154e6f

messageHash 0x921854a0cc7746e05082591412747ffa0c497e6c4785504b29061c5d36b0e1b0

STEP 4: Fetch attestation signature
Signature: 0x5c515abc1964dfe1e46a4a4daacb897a24d586e15d0ff93617e8f22793ed6192565957db1dc55b4011409f4b7dbb4e072a8365fa11071b393c41a6e2527a1b421c6d49f035e9665c55568afea143e3490fa8a1d5f6409fbc94956a9a95cfe258f6236e0805e96080d8347153d64d8823983e9cdfbdb08140d1933b3d8f874356551c

STEP 5: Using the message bytes and signature recieve the funds on destination chain and address
ReceiveTx 0xa4960f3caad924ffd6982bde512dff930cc1276e4d2ea92b7ab2f1f81bf17bc4

ReceiveTxReceipt:  {
  blockHash: '0xc7635b7727dd31d44f7b75edfb7298cfe661da5c8910fda8eaa1638a98b9fc68',
  blockNumber: 30168739n,
  contractAddress: null,
  cumulativeGasUsed: 325719n,
  effectiveGasPrice: 25000000000n,
  from: '0xe45d43feb3f65b4587510a68722450b629154e6f',
  gasUsed: 143755n,
  logs: [
    {
      address: '0x5425890298aed601595a70ab815c96711a31bc65',
      topics: [Array],
      data: '0x00000000000000000000000000000000000000000000000000000000000186a0',
      blockNumber: 30168739n,
      transactionHash: '0xa4960f3caad924ffd6982bde512dff930cc1276e4d2ea92b7ab2f1f81bf17bc4',
      transactionIndex: 1,
      blockHash: '0xc7635b7727dd31d44f7b75edfb7298cfe661da5c8910fda8eaa1638a98b9fc68',
      logIndex: 2,
      removed: false
    },
    {
      address: '0x5425890298aed601595a70ab815c96711a31bc65',
      topics: [Array],
      data: '0x00000000000000000000000000000000000000000000000000000000000186a0',
      blockNumber: 30168739n,
      transactionHash: '0xa4960f3caad924ffd6982bde512dff930cc1276e4d2ea92b7ab2f1f81bf17bc4',
      transactionIndex: 1,
      blockHash: '0xc7635b7727dd31d44f7b75edfb7298cfe661da5c8910fda8eaa1638a98b9fc68',
      logIndex: 3,
      removed: false
    },
    {
      address: '0xeb08f243e5d3fcff26a9e38ae5520a669f4019d0',
      topics: [Array],
      data: '0x00000000000000000000000000000000000000000000000000000000000186a0',
      blockNumber: 30168739n,
      transactionHash: '0xa4960f3caad924ffd6982bde512dff930cc1276e4d2ea92b7ab2f1f81bf17bc4',
      transactionIndex: 1,
      blockHash: '0xc7635b7727dd31d44f7b75edfb7298cfe661da5c8910fda8eaa1638a98b9fc68',
      logIndex: 4,
      removed: false
    },
    {
      address: '0xa9fb1b3009dcb79e2fe346c16a604b8fa8ae0a79',
      topics: [Array],
      data: '0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000009f3b8679c73c2fef8b59b4f3444d4e156fb70aa500000000000000000000000000000000000000000000000000000000000000600000000000000000000000000000000000000000000000000000000000000084000000000000000000000000000000001c7d4b196cb0c7b01d743fbc6116a902379c7238000000000000000000000000e45d43feb3f65b4587510a68722450b629154e6f00000000000000000000000000000000000000000000000000000000000186a0000000000000000000000000e45d43feb3f65b4587510a68722450b629154e6f00000000000000000000000000000000000000000000000000000000',
      blockNumber: 30168739n,
      transactionHash: '0xa4960f3caad924ffd6982bde512dff930cc1276e4d2ea92b7ab2f1f81bf17bc4',
      transactionIndex: 1,
      blockHash: '0xc7635b7727dd31d44f7b75edfb7298cfe661da5c8910fda8eaa1638a98b9fc68',
      logIndex: 5,
      removed: false
    }
  ],
  logsBloom: '0x0000000000000000008000000000000100004000000000000000010000200000200000000400000000000000000002000000a000000000000000000000000000000000000000000000000008000000000080000000000000000000200000000001020000020000000000000000012800000000000000000000400010000000000000000000000400000000001000000000000000000002000000000000010400000000000000000004100000000000040000000000000000000000000000000000000002000010000080000000000000000000000000000000000000020020000000000000000000000000000000004000000000000800000000000000000000',
  status: 'success',
  to: '0xa9fb1b3009dcb79e2fe346c16a604b8fa8ae0a79',
  transactionHash: '0xa4960f3caad924ffd6982bde512dff930cc1276e4d2ea92b7ab2f1f81bf17bc4',
  transactionIndex: 1,
  type: 'eip1559'
}
Check USDC on Avax testnet balanceOf 10000
```

## Referrence

- doc <https://developers.circle.com/stablecoins/docs/transfer-usdc-on-testnet-from-ethereum-to-avalanche>

- contract deployment <https://developers.circle.com/stablecoins/docs/evm-smart-contracts>

- USDC Testnet faucet <https://faucet.circle.com/?_gl=1*ouhs7l*_ga_GJDVPCQNRV*MTcwODUwNDQ1OC4zLjEuMTcwODUwNDQ5MS4yNy4wLjA>
