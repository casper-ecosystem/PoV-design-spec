# Proof-of-Victory NFT Design Specification
This document outlines the metadata schema and modality selections chosen when installing [CEP-78](https://github.com/casper-ecosystem/cep-78-enhanced-nft) Proof-of-Victory NFT contracts.

## Metadata
Casper Association's Proof-of-Victory NFTs use the `CustomValidated` [NFTMetadataKind](https://github.com/casper-ecosystem/cep-78-enhanced-nft#nftmetadatakind) which requires that an NFT's metadata conform to a specified JSON schema. The schema used for PoV NFTs is below.

```json
{
  "properties": {
    "participant": {
      "name": "participant",
      "description": "The full/preferred name of the participant.",
      "required": true,
    },
    "bounty": {
      "name": "bounty",
      "description": "The bounty completed to earn the award.",
      "required": true,
    },
    "project": {
      "name": "project",
      "description": "The name of the project submitted to win the award.",
      "required": true,
    },
    "place": {
      "name": "place",
      "description": "The rank of the award (e.g. \"3rd place\").",
      "required": false,
    },
    "tier": {
      "name": "tier",
      "description": "The tier of the bounty (e.g. \"Advanced\").",
      "required": false,
    },
    "image": {
      "name": "",
      "description": "The IPFS URI of the image associated with the NFT.",
      "required": true,
    },
  }
}
```

## Modalities
A specific selection of [CEP-78 Modalities](https://github.com/casper-ecosystem/cep-78-enhanced-nft#modalities) is chosen for Casper Association's Proof-of-Victory NFTs. This section outlines each modality chosen and the purpose it serves.

### [Ownership](https://github.com/casper-ecosystem/cep-78-enhanced-nft#ownership)
The CEP-78 Ownership mode is set to `Transferable`. This allows for NFTs to be transferrable between accounts.

### [NFTKind](https://github.com/casper-ecosystem/cep-78-enhanced-nft#nftkind)
Casper's Proof-of-Victory NFTs are tokens that represent an award that may influence physical recognition. Because of this, Casper's PoV NFTs are of the `Virtual` NFTKind.

### [NFTHolderMode](https://github.com/casper-ecosystem/cep-78-enhanced-nft#nftholdermode)
NFTHolderMode dictates which entities on a Casper Network can hold NFTs; in the case of Casper's PoV NFTs, `Accounts` are the only entities permissioned to hold them.

### [WhitelistMode](https://github.com/casper-ecosystem/cep-78-enhanced-nft#whitelistmode)
WhitelistMode is ignored as PoV NFTs have no use for a whitelist.

### [Minting](https://github.com/casper-ecosystem/cep-78-enhanced-nft#modalities)
The minting mode defines which entities have the right to mint a PoV NFT. For this use-case, `Installer` is chosen, meaning PoV NFTs can only be minted by the installer of the smart contract.

### [NFTMetadataKind](https://github.com/casper-ecosystem/cep-78-enhanced-nft#nftmetadatakind)
As mentioned in the [first section](#Metadata), the NFTMetadataKind is set to `CustomValidated` and requires its own schema.

### [NFTIdentifierMode](https://github.com/casper-ecosystem/cep-78-enhanced-nft#nftmetadatakind)
The CEP-78 standard allows tokens to be identified either by its hash or by an ordinal, auto-incrementing value. In the case of PoV NFTs, tokens are identified by hash.

### [Metadata Mutability](https://github.com/casper-ecosystem/cep-78-enhanced-nft#metadata-mutability)
Casper Association's PoV NFTs are immutable, meaning the metadata may not be altered once the NFT is minted.

### [BurnMode](https://github.com/casper-ecosystem/cep-78-enhanced-nft#burnmode)
BurnMode is set to `Burnable`, giving winners the ability to destroy their award if they so choose.

## Additional Notes
* Casper's Proof-of-Victory NFTs act as any other CEP-78 NFT does. Holders have the right to do with them as they please within the bounds of the selected modalities.


