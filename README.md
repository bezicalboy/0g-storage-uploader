# 0G Storage Auto-Upload Bot

This guide provides step-by-step instructions for setting up and using an automated file uploader bot with the official 0G Storage Client on the testnet.

The process involves two main components:
1.  **The official `0g-storage-client`**: This is the core command-line tool for interacting with the 0G storage network, which we will build from the source.
2.  **The Auto-Upload Bot**: A pre-compiled binary that uses the client to automatically upload files.

---

## Prerequisites

* Go (version 1.21 or later) installed on your system.
* Git version control.
* A 0G testnet wallet with a private key and some testnet tokens for transaction fees.

---

## Setup and Installation

Follow these steps carefully to ensure both the client and the bot are set up correctly.

### Step 1: Build the 0G Storage Client

First, we need to clone the official 0G Storage Client repository and build the binary from the source code.

1.  **Clone the official repository:**
    ```bash
    git clone [https://github.com/0glabs/0g-storage-client.git](https://github.com/0glabs/0g-storage-client.git)
    ```

2.  **Navigate into the project directory:**
    ```bash
    cd 0g-storage-client
    ```

3.  **Build the client binary:**
    ```bash
    go build
    ```

4.  **Verify the build:**
    After the build process completes successfully, you will find a new binary file named `0g-storage-client` in the current directory. Do not move or rename this file.

### Step 2: Add the Auto-Upload Bot

Now, place the auto-upload bot into the directory you just prepared.

1.  **Download the bot:**
    Download the bot binary in this repo.

2.  **Place the bot in the `0g-storage-client` folder:**
    Move the downloaded bot binary into the `0g-storage-client` directory, alongside the `0g-storage-client` binary you built in the previous step.

### Step 3: Configure Your Environment

The bot requires a `.env` file to connect to the network and use your wallet.

1.  **Create a `.env` file** in the root of the `0g-storage-client` directory.

2.  **Add the following configuration** to the `.env` file, replacing the placeholder private key with your own.

    ```dotenv
    RPC_URL=[https://evmrpc-testnet.0g.ai](https://evmrpc-testnet.0g.ai)
    PRIVATE_KEY=0xyourpk
    INDEX_URL=[https://indexer-storage-testnet-turbo.0g.ai](https://indexer-storage-testnet-turbo.0g.ai)
    ```

    * `RPC_URL`: The RPC endpoint for the 0G testnet.
    * `PRIVATE_KEY`: **IMPORTANT!** Replace `0xyourpk` with the actual private key of your 0G testnet wallet.
    * `INDEX_URL`: The endpoint for the storage indexer service.

    > **Security Warning**: Never commit your `.env` file to a public repository. Keep your private key secure at all times.

---

## Usage

With everything in place, you can now run the bot.

1.  **Ensure you are in the `0g-storage-client` directory.**

2.  **Make the bot executable (if necessary):**
    ```bash
    chmod +x ./bot
    ```
    *(Replace `bot` with the actual name of the bot file).*

3.  **Run the bot:**
    ```bash
    ./bot
    ```

The bot will now start, read the configuration from your `.env` file, and begin automatically uploading files to the 0G storage network using the `0g-storage-client` binary.
