# `nft api`
> NFT API that returns resolved metadata and has all information about all NFT collections, users, transactions. Cross-Chain NFT API.


# ⭐️ `Star us`
If this boilerplate helps you build Ethereum dapps faster - please star this project, every star makes us very happy!


# 🤝 `Need help?`
If you need help with setting up the boilerplate or have other questions - don't hesitate to write in our community forum and we will check asap. [Forum link](https://forum.moralis.io/t/ethereum-unity3d-boilerplate-questions/4553). The best thing about this boilerplate is the super active community ready to help at any time! We help each other.


# 🧭 Table of contents
- [`nft-api`](#nft-api)
- [🧭 Table of contents](#-table-of-contents)
- [🖼 NFT API Endpoints](#nft-api-endpoints)
    - [`SearchNFTs`](#searchnfts)
    - [`GetNFTs`](#getnfts)
    - [`GetNFTsForContract`](#getnftsforcontract)
    - [`GetNFTTransfers`](#getnfttransfers)
    - [`GetNFTTransfersByBlock`](#GetNFTTransfersByBlock)
    - [`GetAllTokenIds`](#getalltokenids)
    - [`GetContractNFTTransfers`](#getcontractnfttransfers)
    - [`GetNFTLowestPrice`](#getnftlowestprice)
    - [`GetNFTMetadata`](#getnftmetadata)
    - [`GetNFTOwners`](#getnftowners)
    - [`GetNFTTrades`](#getnfttrades)
    - [`GetNftTransfersFromToBlock`](#getnfttransfersfromtoblock)
    - [`GetTokenAdressTransfers`](#gettokenaddrestransfers)
    - [`GetTokenAllowance`](#gettokenallowance)
    - [`GetTokenIdMetadata`](#gettokenidmetadata)
    - [`GetTokenIdOwners`](#gettokenidowners)
    - [`GetWalletTokenIdTransfers`](#getwallettokenidtransfers)
- [Helpful Tools](#helpful-tools)


# 🖼 NFT API Endpoints

### `SearchNFTs`
NFT API gets the NFT data based on a metadata search.

**Options**:
- `q` *(required)*: The search string parameter
- `filter` *(required)*: What fields the search should match on. To look into the entire metadata set the value to global. To have a better response time you can look into a specific field like name. Available values : name; description; attributes; global; name,description; name,attributes; description,attributes; name,description,attributes
- `chain` *(optional)*: The blockchain to get data from. Valid values are listed on the intro page in the [`Supported Blockchains`](#supported-blockchains). Default value Eth.
- `format` *(optional)*: The format of the token id. Available values : decimal, hex. Default value : decimal.
- `offset` *(optional)*: offset.
- `limit` *(optional)*: limit.

#### Moralis SDK
```js
const options = { q: "Pancake", chain: "bsc", filter: "name" };
const NFTs = await Moralis.Web3API.token.searchNFTs(options);
```

#### CURL
```bash
curl -X 'GET' \
  'https://deep-index.moralis.io/api/v2/nft/search?chain=eth&format=decimal&q=sdsdsdsdsd&filter=name' \
  -H 'accept: application/json'
  -H 'X-API-Key: YOUR_API_KEY'
```

**Example return** (Object)
```json
[
  {
    "token_id": "124436",
    "token_address": "0x3afa102b264b5f79ce80fed29e0724f922ba57c7",
    "token_uri": "https://ipfs.moralis.io:2053/ipfs/QmVAD8v4s2SXF8FgjePqMdQ2GV5hE2isZnzxcrA36XcSDA/metadata.json",
    "metadata": "{\"name\":\"Pancake\",\"description\":\"The dessert series 1\",\"image\":\"ipfs://QmNQFXCZ6LGzvpMW9Q5PWbCrEnLknQrPwr2r8pbQAgzQ9A/4863BD6B-6C92-4B96-BF80-8020B2F7C3A5.jpeg\"}",
    "contract_type": "ERC721",
    "token_hash": "d03fe436e972bf9215d7bb8c64c4c556",
    "synced_at": null,
    "created_at": "2021-09-19T10:36:16.610Z"
  }
]
```


### `GetNFTs`
NFT API gets all NFTs from the current user or address. Supports both ERC721 and ERC1155. Returns an object with the number of NFT objects and the array of NFT objects.

**Options**:
- `chain` *(optional)*: The blockchain to get data from. Valid values are listed on the intro page in the [`Supported Blockchains`](#supported-blockchains). Default value Eth.
- `address` *(optional)*: A user address (i.e. 0x1a2b3x...).
- `format` *(optional)*: The format of the token id. Available values : decimal, hex. Default value : decimal.
- `offset` *(optional)*: offset.
- `limit` *(optional)*: limit.

#### Moralis SDK
```js
onst options = { chain: 'matic', address: '0x...' };
const polygonNFTs = await Moralis.Web3API.account.getNFTs(options);
```

#### CURL
```bash
curl -X 'GET' \
  'https://deep-index.moralis.io/api/v2/0xaddress/nft?chain=eth&format=decimal' \
  -H 'accept: application/json'
  -H 'X-API-Key: YOUR_API_KEY'
```

**Example return** (Object)
```json
[
  {
    "token_address": "0x057Ec652A4F150f7FF94f089A38008f49a0DF88e",
    "token_id": "15",
    "contract_type": "ERC721",
    "owner_of": "0x057Ec652A4F150f7FF94f089A38008f49a0DF88e",
    "block_number": "88256",
    "block_number_minted": "88256",
    "token_uri": "string",
    "metadata": "string",
    "synced_at": "string",
    "amount": "1",
    "name": "CryptoKitties",
    "symbol": "RARI"
  }
]
```


### `GetNFTsForContrac
NFT API gets an object with the NFT count for the specified contract and an NFT array belonging to the given address for the specified contract (asynchronous).

**Options**:
- `chain` *(optional)*: The blockchain to get data from. Valid values are listed on the intro page in the [`Supported Blockchains`](#supported-blockchains). Default value Eth.
- `format` *(optional)*: The format of the token id. Available values : decimal, hex. Default value : decimal.
- `offset` *(optional)*: offset.
- `limit` *(optional)*: limit.

#### Moralis SDK
```js

```

#### CURL
```bash

  -H 'X-API-Key: YOUR_API_KEY'
```

**Example return** (Object)
```json

```


### `GetNFTTransfers`
**Options**:
- `chain` *(optional)*: The blockchain to get data from. Valid values are listed on the intro page in the [`Supported Blockchains`](#supported-blockchains). Default value Eth.
- `format` *(optional)*: The format of the token id. Available values : decimal, hex. Default value : decimal.
- `offset` *(optional)*: offset.
- `limit` *(optional)*: limit.

#### Moralis SDK
```js

```

#### CURL
```bash

  -H 'X-API-Key: YOUR_API_KEY'
```

**Example return** (Object)
```json

```


### `GetNFTTransfersByBlock`
**Options**:
- `chain` *(optional)*: The blockchain to get data from. Valid values are listed on the intro page in the [`Supported Blockchains`](#supported-blockchains). Default value Eth.
- `format` *(optional)*: The format of the token id. Available values : decimal, hex. Default value : decimal.
- `offset` *(optional)*: offset.
- `limit` *(optional)*: limit.

#### Moralis SDK
```js

```

#### CURL
```bash

  -H 'X-API-Key: YOUR_API_KEY'
```

**Example return** (Object)
```json

```


### `GetAllTokenIds`
**Options**:
- `chain` *(optional)*: The blockchain to get data from. Valid values are listed on the intro page in the [`Supported Blockchains`](#supported-blockchains). Default value Eth.
- `format` *(optional)*: The format of the token id. Available values : decimal, hex. Default value : decimal.
- `offset` *(optional)*: offset.
- `limit` *(optional)*: limit.

#### Moralis SDK
```js

```

#### CURL
```bash

  -H 'X-API-Key: YOUR_API_KEY'
```

**Example return** (Object)
```json

```


### `GetContractNFTTransfers`
### `GetNFTLowestPrice`
### `GetNFTMetadata`
### `GetNFTOwners`
### `GetNFTTrades`
### `GetNftTransfersFromToBlock`
### `GetTokenAdressTransfers`
### `GetTokenAllowance`
### `GetTokenIdMetadata`
### `GetTokenIdOwners`
### `GetWalletTokenIdTransfers`
