# Tài liệu Mining Meta Node App

## 1. Active Device

### SMC Functions
#### checkValid
```json
{
    "inputs": [
      {
        "internalType": "address",
        "name": "_address",
        "type": "address"
      }
    ],
    "name": "checkValid",
    "outputs": [
      {
        "internalType": "bool",
        "name": "",
        "type": "bool"
      }
    ],
    "stateMutability": "view",
    "type": "function"
  },
```

### API Endpoints
```http
POST /secured/login-with-referral-code
Request Body:
{
    "deviceInfo": "string[]",
    "phoneNumber": "string",
}
Response:
{
    "pinCode": string,
    "phoneNumber": "string"
}
```

```http
POST /secured/login-with-referral-code/scan-qr
Request Body:
{
    "phoneNumber": "string",
    "pinCode": "string",
    "url": "string",
}
```

## 2. Thêm ví đào ( Mining )

### SMC Functions
#### getListMiningAddressToWallet
```json
{
    "inputs": [
      {
        "internalType": "address",
        "name": "user",
        "type": "address"
      }
    ],
    "name": "getListMiningAddressToWallet",
    "outputs": [
      {
        "internalType": "address[]",
        "name": "",
        "type": "address[]"
      }
    ],
    "stateMutability": "view",
    "type": "function"
  }
```

#### viewMiningWallet
```json
{
    "inputs": [],
    "name": "viewMiningWallet",
    "outputs": [
      {
        "components": [
          {
            "internalType": "address",
            "name": "user",
            "type": "address"
          },
          {
            "internalType": "uint256",
            "name": "joinDate",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "balanceMTD",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lastestMint",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "claimVelSto",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "totalMember",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "maxStake",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "currentStake",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "currentDepositUSDM",
            "type": "uint256"
          },
          {
            "internalType": "address",
            "name": "byReferrer",
            "type": "address"
          },
          {
            "internalType": "uint256",
            "name": "releasePercentage",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lockTime",
            "type": "uint256"
          },
          {
            "internalType": "bytes32",
            "name": "keyHash",
            "type": "bytes32"
          }
        ],
        "internalType": "struct MiningStorage.UserData[]",
        "name": "users",
        "type": "tuple[]"
      },
      {
        "internalType": "uint256[]",
        "name": "amounts",
        "type": "uint256[]"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### addVisibleAddress
```json
{
    "inputs": [
      {
        "internalType": "address[]",
        "name": "list",
        "type": "address[]"
      }
    ],
    "name": "addVisibleAddress",
    "outputs": [],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### removeVisibleAddress
```json
{
    "inputs": [
      {
        "internalType": "address",
        "name": "removedAddress",
        "type": "address"
      }
    ],
    "name": "removeVisibleAddress",
    "outputs": [
      {
        "internalType": "bool",
        "name": "success",
        "type": "bool"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

### API Endpoints
```http
POST /secured/replace
Request Body:
{
    "oldAddress": "string",
    "newAddress": "string"
}
Response:
{
    "success": boolean,
}
```

## 3. Quá trình Mining

### SMC Functions
#### userDataStorage
```json
{
    "inputs": [
      {
        "internalType": "address",
        "name": "",
        "type": "address"
      }
    ],
    "name": "userDataStorage",
    "outputs": [
      {
        "internalType": "address",
        "name": "user",
        "type": "address"
      },
      {
        "internalType": "uint256",
        "name": "joinDate",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "balanceMTD",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "lastestMint",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "claimVelSto",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "totalMember",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "maxStake",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "currentStake",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "currentDepositUSDM",
        "type": "uint256"
      },
      {
        "internalType": "address",
        "name": "byReferrer",
        "type": "address"
      },
      {
        "internalType": "uint256",
        "name": "releasePercentage",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "lockTime",
        "type": "uint256"
      },
      {
        "internalType": "bytes32",
        "name": "keyHash",
        "type": "bytes32"
      }
    ],
    "stateMutability": "view",
    "type": "function"
  }
```

#### claimAmount
```json
{
    "inputs": [],
    "name": "getClaimSpeed",
    "outputs": [
      {
        "internalType": "uint256",
        "name": "claimAmount",
        "type": "uint256"
      }
    ],
    "stateMutability": "view",
    "type": "function"
  }
```

## 4. Active Code từ PO5

### SMC Functions
#### GetTotalCode
```json
{
    "inputs": [
      {
        "internalType": "address",
        "name": "target",
        "type": "address"
      }
    ],
    "name": "GetTotalCode",
    "outputs": [
      {
        "internalType": "uint256",
        "name": "",
        "type": "uint256"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### mCodeHasToDiscountInfo
```json
  {
    "inputs": [
      {
        "internalType": "bytes32",
        "name": "",
        "type": "bytes32"
      }
    ],
    "name": "mCodeHasToDiscountInfo",
    "outputs": [
      {
        "internalType": "uint256",
        "name": "MultipleBoostingTime",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "MultipleBoostingRate",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "BeginRequireActivateDate",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "EndRequireActivateDate",
        "type": "uint256"
      }
    ],
    "stateMutability": "view",
    "type": "function"
  }
```

#### getCodeInfo
```json
    {
    "inputs": [
      {
        "internalType": "bytes32",
        "name": "codeHash",
        "type": "bytes32"
      }
    ],
    "name": "getCodeInfo",
    "outputs": [
      {
        "components": [
          {
            "internalType": "address",
            "name": "owner",
            "type": "address"
          },
          {
            "internalType": "bytes32",
            "name": "codeHash",
            "type": "bytes32"
          },
          {
            "internalType": "uint256",
            "name": "activeTime",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "expirationActiveTime",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "boostSpeed",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "boostTime",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "rateBoost",
            "type": "uint256"
          },
          {
            "internalType": "address",
            "name": "delegate",
            "type": "address"
          },
          {
            "internalType": "enum Status",
            "name": "status",
            "type": "uint8"
          },
          {
            "internalType": "string",
            "name": "origin",
            "type": "string"
          },
          {
            "internalType": "uint256",
            "name": "mintedAmount",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "releasePercentage",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lockTime",
            "type": "uint256"
          },
          {
            "internalType": "bytes32",
            "name": "keyHash",
            "type": "bytes32"
          },
          {
            "internalType": "uint256",
            "name": "currentDeposit",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lastestClaim",
            "type": "uint256"
          }
        ],
        "internalType": "struct Code",
        "name": "",
        "type": "tuple"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### activeCode
```json
{
    "inputs": [
      {
        "internalType": "string",
        "name": "codeFE",
        "type": "string"
      }
    ],
    "name": "activeCode",
    "outputs": [
      {
        "internalType": "bool",
        "name": "",
        "type": "bool"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### GetSubmittedCodes
```json
 {
    "inputs": [
      {
        "internalType": "address",
        "name": "target",
        "type": "address"
      },
      {
        "internalType": "uint32",
        "name": "page",
        "type": "uint32"
      }
    ],
    "name": "GetSubmittedCodes",
    "outputs": [
      {
        "internalType": "bool",
        "name": "isMore",
        "type": "bool"
      },
      {
        "components": [
          {
            "internalType": "address",
            "name": "owner",
            "type": "address"
          },
          {
            "internalType": "bytes32",
            "name": "codeHash",
            "type": "bytes32"
          },
          {
            "internalType": "uint256",
            "name": "activeTime",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "expirationActiveTime",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "boostSpeed",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "boostTime",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "rateBoost",
            "type": "uint256"
          },
          {
            "internalType": "address",
            "name": "delegate",
            "type": "address"
          },
          {
            "internalType": "enum Status",
            "name": "status",
            "type": "uint8"
          },
          {
            "internalType": "string",
            "name": "origin",
            "type": "string"
          },
          {
            "internalType": "uint256",
            "name": "mintedAmount",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "releasePercentage",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lockTime",
            "type": "uint256"
          },
          {
            "internalType": "bytes32",
            "name": "keyHash",
            "type": "bytes32"
          },
          {
            "internalType": "uint256",
            "name": "currentDeposit",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lastestClaim",
            "type": "uint256"
          }
        ],
        "internalType": "struct Code[]",
        "name": "listCode",
        "type": "tuple[]"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

## 5. Quản lý Ví Wallet và Code

### SMC Functions
#### setPhoneWalletLockTime

```json
{
    "inputs": [
      {
        "internalType": "address",
        "name": "miningAddress",
        "type": "address"
      },
      {
        "internalType": "uint256",
        "name": "newLockTime",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "lockRate",
        "type": "uint256"
      }
    ],
    "name": "setPhoneWalletLockTime",
    "outputs": [
      {
        "internalType": "bool",
        "name": "",
        "type": "bool"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### setCodeLockTime

```json
  {
    "inputs": [
      {
        "internalType": "bytes32",
        "name": "codeHash",
        "type": "bytes32"
      },
      {
        "internalType": "uint256",
        "name": "newLockTime",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "lockRate",
        "type": "uint256"
      }
    ],
    "name": "setCodeLockTime",
    "outputs": [
      {
        "internalType": "bool",
        "name": "",
        "type": "bool"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### viewMiningWalletBalance

```json
{
    "inputs": [
      {
        "internalType": "address",
        "name": "miningAddress",
        "type": "address"
      }
    ],
    "name": "viewMiningWalletBalance",
    "outputs": [
      {
        "components": [
          {
            "internalType": "address",
            "name": "user",
            "type": "address"
          },
          {
            "internalType": "uint256",
            "name": "joinDate",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "balanceMTD",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lastestMint",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "claimVelSto",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "totalMember",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "maxStake",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "currentStake",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "currentDepositUSDM",
            "type": "uint256"
          },
          {
            "internalType": "address",
            "name": "byReferrer",
            "type": "address"
          },
          {
            "internalType": "uint256",
            "name": "releasePercentage",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lockTime",
            "type": "uint256"
          },
          {
            "internalType": "bytes32",
            "name": "keyHash",
            "type": "bytes32"
          }
        ],
        "internalType": "struct MiningStorage.UserData",
        "name": "user",
        "type": "tuple"
      },
      {
        "components": [
          {
            "internalType": "address",
            "name": "owner",
            "type": "address"
          },
          {
            "internalType": "bytes32",
            "name": "codeHash",
            "type": "bytes32"
          },
          {
            "internalType": "uint256",
            "name": "activeTime",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "expirationActiveTime",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "boostSpeed",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "boostTime",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "rateBoost",
            "type": "uint256"
          },
          {
            "internalType": "address",
            "name": "delegate",
            "type": "address"
          },
          {
            "internalType": "enum Status",
            "name": "status",
            "type": "uint8"
          },
          {
            "internalType": "string",
            "name": "origin",
            "type": "string"
          },
          {
            "internalType": "uint256",
            "name": "mintedAmount",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "releasePercentage",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lockTime",
            "type": "uint256"
          },
          {
            "internalType": "bytes32",
            "name": "keyHash",
            "type": "bytes32"
          },
          {
            "internalType": "uint256",
            "name": "currentDeposit",
            "type": "uint256"
          },
          {
            "internalType": "uint256",
            "name": "lastestClaim",
            "type": "uint256"
          }
        ],
        "internalType": "struct Code[]",
        "name": "codes",
        "type": "tuple[]"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### updateCodeWalletKey

```json
  {
    "inputs": [
      {
        "internalType": "bytes32",
        "name": "codeHash",
        "type": "bytes32"
      },
      {
        "internalType": "string",
        "name": "rawKey",
        "type": "string"
      },
      {
        "internalType": "bytes32",
        "name": "newKeyHash",
        "type": "bytes32"
      }
    ],
    "name": "updateCodeWalletKey",
    "outputs": [
      {
        "internalType": "bool",
        "name": "",
        "type": "bool"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### updateWalletKey

```json
  {
    "inputs": [
      {
        "internalType": "address",
        "name": "miningAddress",
        "type": "address"
      },
      {
        "internalType": "string",
        "name": "rawKey",
        "type": "string"
      },
      {
        "internalType": "bytes32",
        "name": "newKeyHash",
        "type": "bytes32"
      }
    ],
    "name": "updateWalletKey",
    "outputs": [],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### toUSD

```json
    {
    "inputs": [
      {
        "internalType": "uint256",
        "name": "amountME",
        "type": "uint256"
      }
    ],
    "name": "toUSD",
    "outputs": [
      {
        "internalType": "uint256",
        "name": "amountUSDM",
        "type": "uint256"
      }
    ],
    "stateMutability": "view",
    "type": "function"
  }
```

#### withdraw

```json
      {
    "inputs": [
      {
        "internalType": "address",
        "name": "miningAddress",
        "type": "address"
      },
      {
        "internalType": "uint256",
        "name": "amountMTD",
        "type": "uint256"
      },
      {
        "internalType": "string",
        "name": "rawKey",
        "type": "string"
      },
      {
        "internalType": "bytes32",
        "name": "newKeyHash",
        "type": "bytes32"
      }
    ],
    "name": "withdraw",
    "outputs": [
      {
        "internalType": "bytes32",
        "name": "historyhash",
        "type": "bytes32"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

#### withdrawFromCode

```json
{
    "inputs": [
      {
        "internalType": "address",
        "name": "miningAddress",
        "type": "address"
      },
      {
        "internalType": "bytes32",
        "name": "codeHash",
        "type": "bytes32"
      },
      {
        "internalType": "uint256",
        "name": "amountMTD",
        "type": "uint256"
      },
      {
        "internalType": "string",
        "name": "rawKey",
        "type": "string"
      },
      {
        "internalType": "bytes32",
        "name": "newKeyHash",
        "type": "bytes32"
      }
    ],
    "name": "withdrawFromCode",
    "outputs": [
      {
        "internalType": "bytes32",
        "name": "historyhash",
        "type": "bytes32"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```

## 6. Hoàn Tiền Deposit

### SMC Functions

#### getHash

```json
{
    "inputs": [
        {
            "internalType": "bytes32",
            "name": "key",
            "type": "bytes32"
        },
        {
            "internalType": "address",
            "name": "to",
            "type": "address"
        }
    ],
    "name": "getHash",
    "outputs": [
        {
            "internalType": "bool",
            "name": "isMore",
            "type": "bool"
        },
        {
            "components": [
                {
                    "internalType": "bytes32",
                    "name": "hash",
                    "type": "bytes32"
                },
                {
                    "internalType": "uint256",
                    "name": "rate",
                    "type": "uint256"
                },
                {
                    "internalType": "uint256",
                    "name": "amountNative",
                    "type": "uint256"
                },
                {
                    "internalType": "uint256",
                    "name": "amountUsdt",
                    "type": "uint256"
                },
                {
                    "internalType": "uint256",
                    "name": "timestamp",
                    "type": "uint256"
                }
            ],
            "internalType": "struct DepositHistory[]",
            "name": "arrayHashInfo",
            "type": "tuple[]"
        }
    ],
    "stateMutability": "view",
    "type": "function"
}
```

#### withdrawUsdt

```json
{
    "inputs": [
        {
            "internalType": "bytes32",
            "name": "key",
            "type": "bytes32"
        }
    ],
    "name": "withdrawUsdt",
    "outputs": [
        {
            "internalType": "bool",
            "name": "",
            "type": "bool"
        }
    ],
    "stateMutability": "payable",
    "type": "function"
}
```
## 7. Referral Team

### SMC Functions
#### getReferralReport

```json
  {
    "inputs": [],
    "name": "getReferralReport",
    "outputs": [
      {
        "internalType": "uint256",
        "name": "cycle",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "totalMemberRef",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "totalReward",
        "type": "uint256"
      },
      {
        "internalType": "uint256[]",
        "name": "commssion",
        "type": "uint256[]"
      },
      {
        "internalType": "uint256[8]",
        "name": "reward",
        "type": "uint256[8]"
      },
      {
        "internalType": "uint256[8]",
        "name": "member",
        "type": "uint256[8]"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```
#### getReferralReportWeekly

```json
{
    "inputs": [
      {
        "internalType": "uint256",
        "name": "level",
        "type": "uint256"
      }
    ],
    "name": "getReferralReportWeekly",
    "outputs": [
      {
        "internalType": "uint256",
        "name": "cycle",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "memberAtLevelCurrent",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "rewardAtLevelCurrent",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "memberAtLevelPast",
        "type": "uint256"
      },
      {
        "internalType": "uint256",
        "name": "rewardAtLevelPast",
        "type": "uint256"
      }
    ],
    "stateMutability": "nonpayable",
    "type": "function"
  }
```
### API Endpoints
```http
GET /secured/referral
Response:
{
    "rows": string,
}
```

```http
POST /secured/contact
Request Body:
{
    "contactList": "{ phoneNumber: string; name: string }[]",
}
```

```http
GET /secured/get-contact
Response:
{
    "rows": "{ phoneNumber: string; name: string }[]",
}
```
