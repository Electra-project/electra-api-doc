---
title: Authentication Background
position: 4.1

parameters:
  - name:
    content:

content_markdown: |-
  In the EIP-0001, we take advantage of the Hierarchical Deterministic Wallet addresses generation to define 4 accounts category:
  - Purse
  - Checking Account
  - Savings Account
  - Seller Account

  In short, our HD wallet addresses are generated with a 5-steps derivation process of a Master Node private key:
  1. The first derivation level uses an index representing the "purpose" for this chain. We always use the index `44'`.
  2. The second derivation level uses an index representing the "coin type" for this chain. We always use the index `0'`.
  3. The third derivation level uses an index representing the "account" for this chain. We use these indexes like this:
    - `0`: Purse
    - `1`: Checking Account
    - `2`: Savings Account
    - `3`: Seller Account
  4. The fourth derivation level uses an index as a boolean to know if this chain is reserved for change addresses or not. We use `0` for an external addresses chain and `1` for a change addresses chain.
  5. The fifth derivation level uses the address index to generate an infinite pre-determined number of addresses for this specific chain.

  To give you an example, the 5th external (= public) address of a Seller Account and its corresponding change address will be generated like this:

left_code_blocks:
  - code_block: |-
      const bip39 = require('bip39')
      const bitcoinJs = require('bitcoinjs-lib')

      const ECA_NETWORK = {
        bip32: { public: 0, private: 0 },
        messagePrefix: '\x18Electra very Signed Message:\n',
        pubKeyHash: 0x21,
        scriptHash: 0x28,
        wif: 0xA1
      }

      // Do not use this seed for anything else than development purposes !
      const MNEMONIC = 'noise pluck salad violin bounce occur season genius wage tool beyond arrive seven evidence logic erupt siren stadium sister observe upper detect juice transfer'
      const MNEMONIC_EXTENSION = undefined

      const seed = bip39.mnemonicToSeed(MNEMONIC, undefined)
      const masterNode = bitcoinJs.HDNode.fromSeedBuffer(seed, ECA_NETWORK)

      // 5th external (= public) address of a Seller Account:
      const sellerAccountFifthAddressExternal = masterNode.derivePath("m/$44'/0'/3/0/5")
      console.log('Hash', sellerAccountFifthAddressExternal.getAddress())
      console.log('Private Key', sellerAccountFifthAddressExternal.keyPair.toWIF())

      // Corresponding 5th change address of a Seller Account:
      const sellerAccountFifthAddressChange = masterNode.derivePath("m/$44'/0'/3/1/5")
      console.log('Hash', sellerAccountFifthAddressChange.getAddress())
      console.log('Private Key', sellerAccountFifthAddressChange.keyPair.toWIF())
    title: bitcoinjs-lib
    language: javascript

right_code_blocks:
  - code_block:
    title:
    language:
---
