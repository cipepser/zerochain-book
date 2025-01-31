# ZFace: An interface for interacting with Zerochain
(WIP)

ZFace is a low-level wallet core and cryptographic tools for Zerochain.

In this section, we explained the usage of CLI tools powered by ZFace. The CLI tool has mainly four subcommands which is explained later.
- snark: Operations around zk-SNARKs
- wallet: Operations around wallet
- tx: Operatipons around sending transactions to Zerochain
- debug: Debugging and testing commands

### Creating a new wallet
For security reasons, the cryptographic materials are stored encryped by providing a password.

To do this, run:

```
zface wallet init
```

You will then be prompted to enter a password. This password will be used to encrypt your mnemonics of your wallet. Wallet files are stored in zface directory located in the following path.

|Platform | Value | Example |
----|----
| Linux | $XDG_DATA_HOME or $HOME/.local/share/zface | /home/alice/.local/share/zface |
| macOS | $HOME/Library/Application Support/zface | /Users/Alice/Library/Application Support/zface |
| Windows | {FOLDERID_LocalAppData}\zface | C:\Users\Alice\AppData\Local\zface |


### Add a account
You can add a new account into your wallet.

```
zface wallet add-account
```

### Show accounts list
It will show your accounts in your wallet.

```
zface wallet list
```

### Change default account

```
zface wallet change-account -n <ACCOUNT_NAME>
```

### Recover a wallet from mnemonic
(TODO)
```
zface wallet recover
```

You will then be prompted to enter a mnemonic to recover your wallet.

### Get balances
- Getting your current balance from `encrypted-balances` module
```
zface wallet balance
```

- Getting your curernt balance from `encrypted-balances` module
```
zface wallet asset-balance -i <ASSET_ID>
```

### Setup for zk-proving
Generating a proving key and verifying key of zk-SNARKs.
```
zface snark setup
```

### send

```
zface tx transfer -t <RECIPIENT_ADDRESS> -a <AMOUNT>
```

### Manage encrypted assets
- Issue new encrypted assets
```
zface tx asset-issue -a <AMOUNT>
```

- Send encrypted assets
```
zface tx asset-transfer -t <RECIPIENT_ADDRESS> -a <AMOUNT> -i <ASSET_ID>
```

- Burn encrypted assets
```
zface tx asset-burn -i <ASSET_ID>
```

## Test for debugging

### Print key components
```
zface debug key-init
```

### Send tx for debuggin
```
zface debug send -s <SENDER_SEED> -t <RECPIENT_ADDRESS> -a <AMOUNT>
```

### Print transaction components
```
zface debug print-tx
```
