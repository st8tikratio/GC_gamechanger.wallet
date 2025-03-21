
# Cardano Example Dapp

## **DAO Demo**

This script will create a workspace to import addresses, scripts, manage funds and signatures from a DAO where you are a powerful member, you have full control when you use 2 of your keys. 


## Try it online: 

-  Visit [HTML5 Dapp](https://gamechangerfinance.github.io/gamechanger.wallet/examples/DAO%20Demo.html)
-  Run [Standalone URL dapp connection](https://beta-wallet.gamechanger.finance/api/2/run/1-H4sIAAAAAAAAA51V227bSAz9lYFeugt4Y10tOW9Bursx2rRFk0UfgqCgRMoSIs1oZ0ZxjMD_Xo58i-MERfJkDzlzeMhDUo-eXXbknXqm0HVnvZFna9s4w8ezr-IjtYpNSGtvrSQ7rqvaiLVBLOqmEYUmsCRALJS-Mx0UJKwSddspbQUgajKGzGjzhv-0IGFOouwlGgEShannEmzPF0WpVctQLvqiIk1iqXoB2sF3akG67BvRUpuTHg2uCu4dkqOhpNWqcc_k4OoNiVCo0h20uKOlOeFkNP3f15ozfPSksu5nAU1D9prrMOP8bjx6sCSNS_Z2tRrx0SVyZtY12ZREE9OV7nWr0JVLKkneauv47_vnb2AtuSteZW13Oh43qoCmUsaeRr7vj5GBxtDVY4Suc4j9AKcsZ305JPiJlhdgKjLOvpEJwQJfvoemH1KYfb34xOaIijyNkCgIMZpilmZpMc2zlNKAsiQtJohxlmJcUlokQRqRn-dZkcYM9Xfb67lijADjSRklWQ7hNAjjBPN0CpN8mkSpH0EQBTTJMshDP4lpAlmSp3GIkzBgjHPQCFL9o1hR2LQJoA8-FWUGNAkgh2meJhhFKfOMM4gBEwxgGgIg8wWC0o_zMMPQczVfS3LFteyeJN8owHMly3rOMfuOQ9EMD2RpYEma63Wze_Nj25PsrS21a6eElvYCzQsEtW39vflfJ9Z5BbV07Xg4B_tbPwaqwpC1tZwbMSdJmpmhyJfctE7m7bTwVOxmhRFPvNXtarRjynJzjN0MzdBR3XC7fZ286UjiX6ZT0ijNAHe1xK2Zj1AUrIqdSaQH79Rnw3ogtwZH4BmghTt6AdCZ3wV4Dkzm7dSCY6Srpm7fgRQeI10qkCzX5VK7bfdWwOhAuC_c8vd0tV2gryr4QtP93K3dvbxgPxMY3kzhyFPlNc8_Dfauzzcb4cJx8B7nZP_4UEBR0clLW-PE7YYPf648R_XNj9dr4d3PjzbCIdIXLsW-M47sG52P7IeqsQhPZThbS_SeGbri78_QV4P-356GfD5ewxgc3jiYlxeatuLPF17z4JteL7dBnjbNBuhZRwy4v7s21GC1-gWoGcUvxwcAAA)

## Source code:

- dapp connection code: [GCScript DSL](DAO%20Demo.gcscript)
- frontend (using @gamechanger-finance/gc): [HTML5 dapp](DAO%20Demo.html)
- frontend (without official library): [Native HTML5 dapp](DAO%20Demo_nolib.html)

Dapp code was autogenerated by [Playground IDE in GameChanger Wallet ](https://beta-wallet.gamechanger.finance/playground)

## GCScript code (dapp connection):
```json
{
  "type": "script",
  "title": "DAO Demo",
  "description": "This script will create a workspace to import addresses, scripts, manage funds and signatures from a DAO where you are a powerful member, you have full control when you use 2 of your keys.",
  "require": {
    "not": {
      "walletTypeIn": [
        "extension"
      ]
    }
  },
  "exportAs": "DAODemo",
  "return": {
    "mode": "none"
  },
  "returnURLPattern": "http://localhost:3000/demo/api/dapp",
  "run": {
    "otherMemberKeyHashes": {
      "type": "data",
      "value": {
        "IOHK": "3ecb73dee12d39d8787c9b87e71e857c6dd487d4fe7c5173e0bb8c74",
        "Emurgo": "1d46f358ba291245db79a6b953703a131e688ab2054e6a85b742d621",
        "CardanoFoundation": "ad0a0ecf8ae61aba9b75d337b7348a4ad5d1a92aad9d8aeaf04b28d2"
      }
    },
    "walletSetup": {
      "type": "loadConfig",
      "updateId": "DAODemo",
      "layers": [
        {
          "type": "Workspace",
          "items": [
            {
              "namePattern": "gcdao",
              "titlePattern": "GhostChain DAO",
              "descriptionPattern": "Wallet settings generated by a demo script to create a DAO."
            }
          ]
        },
        {
          "type": "Key",
          "workspaceIds": [
            "gcdao"
          ],
          "items": [
            {
              "namePattern": "spend-sponsor",
              "kind": "spend",
              "accountIndex": 0,
              "addressIndex": 0
            },
            {
              "namePattern": "stake-sponsor",
              "kind": "stake",
              "accountIndex": 0,
              "addressIndex": 0
            },
            {
              "namePattern": "Casper",
              "kind": "spend",
              "accountIndex": 0,
              "addressIndex": 1
            },
            {
              "namePattern": "Slimer",
              "kind": "spend",
              "accountIndex": 0,
              "addressIndex": 2
            },
            {
              "namePattern": "MoaningMyrtle",
              "kind": "spend",
              "accountIndex": 0,
              "addressIndex": 3
            }
          ]
        },
        {
          "type": "NativeScript",
          "workspaceIds": [
            "gcdao"
          ],
          "namePattern": "gcdao_script",
          "items": [
            {
              "atLeast": 2,
              "ofThese": [
                {
                  "pubKeyHashHex": "{get('cache.otherMemberKeyHashes.IOHK')}"
                },
                {
                  "pubKeyHashHex": "{get('cache.otherMemberKeyHashes.Emurgo')}"
                },
                {
                  "pubKeyHashHex": "{get('cache.otherMemberKeyHashes.CardanoFoundation')}"
                },
                {
                  "pubKeyName": "Casper"
                },
                {
                  "pubKeyName": "Slimer"
                },
                {
                  "pubKeyName": "MoaningMyrtle"
                }
              ]
            }
          ]
        },
        {
          "type": "Address",
          "workspaceIds": [
            "gcdao"
          ],
          "items": [
            {
              "namePattern": "Signer",
              "spendPubKeyName": "spend-sponsor",
              "stakePubKeyName": "stake-sponsor"
            },
            {
              "namePattern": "SharedTreasury",
              "spendNativeScriptName": "gcdao_script",
              "stakeNativeScriptName": "gcdao_script"
            }
          ]
        }
      ]
    }
  }
}
```

## Run standalone QR dapp connection: 

You can use [Playground IDE in GameChanger Wallet ](https://beta-wallet.gamechanger.finance/playground) in `QR URL Transport` mode to capture results

[![This GCScript/URL is too large! make it shorter uploading parts to GCFS. Unable to generate QR code](DAO%20Demo.png)](https://gamechangerfinance.github.io/gamechanger.wallet/examples/DAO%20Demo.png)

## Resources
- [How to connect?](https://www.npmjs.com/package/@gamechanger-finance/gc)
- [Docs and examples on Github](https://github.com/GameChangerFinance/gamechanger.wallet/)
- [GCScript documentation](https://beta-wallet.gamechanger.finance/doc/api/v2)
- [Playground IDE in GameChanger Wallet ](https://beta-wallet.gamechanger.finance/playground)
- [Tutorials on Youtube](https://www.youtube.com/@gamechanger.finance)
- [Support on Discord](https://discord.gg/vpbfyRaDKG)
- [News on Twitter](https://twitter.com/GameChangerOk)
- [Website](https://gamechanger.finance)

## License
MIT 
    
