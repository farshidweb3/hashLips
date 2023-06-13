# Creating NFTs with Hashlips Library - Readme

## Introduction

This guide will walk you through the process of creating NFTs using the Hashlips library in a Solidity smart contract. The Hashlips library provides an easy and customizable way to generate unique NFTs with multiple layers. This readme will cover the following sections:

1. Technologies Used
2. Deployment
3. How to Use the Smart Contract


[![Watch the video](news-thumbnail-youtube-1020x620-c-default.jpg)](https://www.youtube.com/watch?v=qggXQUV-0T0&t=973s)

## Technologies Used

To create NFTs using the Hashlips library, you will need the following technologies:

- Solidity: The smart contract language used to define and deploy the NFT collection.
- OpenZeppelin: A library for secure and community-audited smart contracts. We will use it for ERC721 implementation and additional functionalities.
- Hashlips Library: A library that provides a framework for generating unique NFTs with layered designs.

## Deployment

To deploy the smart contract and create your NFT collection, follow these steps:

1. Set up a Solidity development environment.
2. Install the required dependencies:
   - OpenZeppelin Contracts: `npm install @openzeppelin/contracts`
3. Import the necessary Solidity files from the Hashlips library:
   - `ERC721Enumerable.sol`
   - `Ownable.sol`
4. Define your smart contract, which should inherit from `ERC721Enumerable` and `Ownable`.
5. Inside the contract's constructor, set the initial values for the NFT collection:
   - `_name`: The name of your NFT collection.
   - `_symbol`: The symbol or ticker of your NFT collection.
   - `_initBaseURI`: The base URI for your NFT metadata. This will be used to generate the token URIs for each NFT.
6. Implement the `_baseURI` function to return the base URI.
7. Implement the `mint` function to mint NFTs:
   - `mint` should take in the address to mint the NFTs to (`_to`) and the number of NFTs to mint (`_mintAmount`).
   - It should use a loop to mint the specified number of NFTs to the given address.
8. Implement the `tokenURI` function to generate the token URI for each NFT:
   - `tokenURI` should take in the `tokenId` and return the full token URI.
   - It should concatenate the base URI, tokenId, and base extension to form the complete URI.
   - If the base URI is not set, it should return an empty string.
9. Implement the `setBaseURI` function to update the base URI.
   - This function should only be accessible to the contract owner.
10. Deploy the smart contract to your desired blockchain network.

## How to Use the Smart Contract

Once the smart contract is deployed, you can interact with it using the following steps:

1. Access the deployed smart contract on the blockchain network.
2. Use the `mint` function to mint NFTs:
   - Provide the address you want to mint the NFTs to (`_to`).
   - Specify the number of NFTs to mint (`_mintAmount`).
   - Pay attention to any required fees for minting.
3. Use the `tokenURI` function to retrieve the token URI for a specific tokenId.
   - Pass the `tokenId` of the desired NFT as the parameter.
   - This will return the full token URI, which can be used to access the NFT metadata.
4. If needed, use the `setBaseURI` function to update the base URI for the NFT metadata.

That's it! You have now created a custom NFT collection using the Hashlips library and deployed it
