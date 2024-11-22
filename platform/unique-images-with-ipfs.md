# Unique Images with IPFS

To ensure that every NFT in your collection has a distinct image and metadata, you'll need to upload both to IPFS and set the generated IPFS CID as the baseURI for your collection. Here's how to do it step by step:

### Step 1: Prepare Your Images

1. Create a folder called `images` on your computer.
2. Name each image file to correspond with token IDs, starting from `0` up to `maxSupply - 1`. For example, if your collection has 1,000 NFTs, name the files `0.png` to `999.png`.
3. For demonstration purposes, let’s assume a smaller collection of 5 NFTs.

### Step 2: Upload Images to IPFS

1. Sign up for a free account on [Pinata Cloud](https://pinata.cloud).
2. Upload your `images` folder and copy the CID (Content Identifier) of the folder once uploaded.

### Step 3: Create Metadata Files

1. Create a JSON file for each NFT. For example, `0.json` should follow this structure:

```json
{
  "name": "My First NFT #0",
  "description": "This is my first NFT ever!",
  "image": "ipfs://YOUR_IMAGE_FOLDER_CID/0.png"
}
```

2. Duplicate this file for each NFT, updating the `name`, `description`, and `image` fields to match the correct token ID and image link.

For instance, `4.json` would look like this:

```json
{
  "name": "My First NFT #4",
  "description": "This is my first NFT ever!",
  "image": "ipfs://YOUR_IMAGE_FOLDER_CID/4.png"
}
```

### **Step 4: Upload Metadata to IPFS**

1. Place all JSON files into a folder called `metadata`.
2. Upload the `metadata` folder to Pinata and copy the CID of the folder.

### Step 5: Set the BaseURI in Your Contract

1. In the "Edit Collection" of IRONBALL, navigate to the "Contract" section.
2. Set the baseURI as `ipfs://YOUR_METADATA_FOLDER_CID/`.

Once this is completed, your NFTs will display their unique images and metadata.

### Additional Notes:

* This guide covers the essential metadata fields: `name`, `description`, and `image`. If you want to include attributes or other fields, refer to the OpenSea Metadata Standards.
* Make sure to double-check the CIDs and links to ensure your metadata and images display correctly.
