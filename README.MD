# Minting an NFT on Solana

This guide walks you through the process of minting an NFT on the Solana blockchain using the provided code.

## Prerequisites

- **Node.js**
- **Anchor Framework**
- **Solana CLI**

## Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/your-repo/solana-mint-nft.git
   cd solana-mint-nft
   ```

2. **Install Dependencies**:

   ```bash
   npm install
   ```

3. **Build the Project**:

   ```bash
   anchor build
   ```

4. **Configure Solana CLI**:

   Set up your Solana CLI to use the Devnet or cluster of your choice.

   ```bash
   solana config set --url https://api.devnet.solana.com
   ```

## Usage

### Updating the Metadata

To update the metadata of your minted NFT, follow these steps:

2. **Update the Metadata File**:

   Upload a new JSON file with the updated metadata to a cloud storage service (such as GitHub, AWS S3, or IPFS). Ensure that this file contains the new information about your NFT. Here’s a sample JSON structure:

   ```json
   {
     "name": "Updated NFT Name",
     "symbol": "UPD",
     "description": "A description of the updated NFT.",
     "image": "https://your-image-url.com/image.png",
     "attributes": [],
     "properties": {
       "files": [
         {
           "uri": "https://your-image-url.com/image.png",
           "type": "image/jpeg"
         }
       ]
     }
   }
   ```

3. **Modify the Metadata Object**:

   In the `mint-nft.ts` (or the appropriate file containing the metadata definition), update the `metadata` object to reflect the new information. For example:

   ```javascript
   const metadata = {
     name: "Updated NFT Name",
     symbol: "UPD",
     uri: "https://your-new-metadata-url.com/updated-metadata.json",
   };
   ```

### Minting an NFT

Run the script to mint the NFT.

```bash
anchor run mint-nft
```
