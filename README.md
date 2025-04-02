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
Input:
- address: địa chỉ của ví phone

Output:
- bool: true nếu đã được active

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
Input:
- user: Địa chỉ ví phone

Output:
- trả ra một mảng ví đã được thêm vào ví đào

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
Input:

Output:
- trả ra thông tin.

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
Input:
- list: danh sách địa chỉ ví user

Output: không có output

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
Input:
- removedAddress: địa chỉ ví cần xoá

Output:
- success: true nếu xoá thành công

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
Input: địa chỉ ví phone

Output: trả thông tin

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
Input: không truyền

Output: claimAmount tốc độ đào

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
Input:
- target: địa chỉ ví phone

Output: số lượng code đã được active từ ví phone

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
Input: bytes32 hash của codeFE từ po5

Output: trả ra thông tin để tính boostSpeed và boostTime

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
Input: codeHash: lấy codeFE po5 đi hash

Output: trả ra thông tin của code

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
Input: codeFE: codeFE từ po5

Output: true nếu code được active thành công

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
Input: 
- target: địa chỉ ví phone

Output: 
- isMore: true nếu danh sách vẫn còn
- listCode: danh sách code đã active

## 5. Quản lý Ví Wallet và Code

### SMC Functions

### API Endpoints


## 6. Hoàn Tiền Deposit

### SMC Functions

### API Endpoints
