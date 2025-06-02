# Sui Kiosk NFT Fetcher

A robust utility for fetching NFTs stored in Sui blockchain kiosks, with multiple fallback methods for maximum reliability.

## Features

- **Multiple API Support**: Uses BlockVision API with fallbacks to SuiVision API and direct blockchain queries
- **Kiosk Discovery**: Automatically discovers kiosks via KioskOwnerCap objects owned by the wallet
- **NFT Extraction**: Fetches and filters NFTs from kiosks based on type
- **Transaction Examples**: Includes example transaction code for interacting with each NFT
- **Comprehensive Logging**: Detailed console output for debugging and monitoring

## Installation

```bash
# Clone the repository
git clone https://github.com/Nuel-osas/koisk-fetcher.git

# Navigate to the directory
cd koisk-fetcher

# Install dependencies
npm install node-fetch @mysten/sui.js
```

## Usage

1. Update the API key, wallet address, and target NFT type in the script:

```javascript
// Target wallet and NFT type
const walletAddress = '0x98a945d6523ba0b4685c4d50d0449c811fded93ad7a20cf2d61af6a6fd4d4d0b';
const targetNFTType = '0xd44eeba23c7256b426113b5b645638f00abc0f27ec224f7286be6f9853df8a5a::_sudoz_artifacts::Nft';

// BlockVision API Key
const BLOCKVISION_API_KEY = 'your_api_key_here';
```

2. Run the script:

```bash
node suiVisionFetcher.js
```

## API Methods

The script attempts to fetch NFTs using three different methods in sequence:

1. **BlockVision API**: Primary method, requires an API key
2. **SuiVision API**: First fallback, public API that doesn't require authentication
3. **Direct Blockchain Query**: Final fallback using the Sui client directly

## Customization

You can easily modify this script to target different NFT types by changing the `targetNFTType` variable and adjusting the filtering logic in each fetch method.

## License

MIT
