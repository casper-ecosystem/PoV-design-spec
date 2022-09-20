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
