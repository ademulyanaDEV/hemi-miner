# Hemi-Miner

## Tutorial for Setting Up Hemi-Miner on macOS

Welcome to the Hemi-Miner setup guide! Follow these steps to get Hemi-Miner up and running on your macOS system.

### Prerequisites
Ensure you have `wget`, `tar`, `nano`, and basic terminal commands available on your system. You may need to install `wget` using Homebrew if not already installed:

```bash
brew install wget
```

### Download and Setup

1. **Download the Hemi Network Binary**
   - For Intel-based Macs (amd64):
     ```bash
     wget https://github.com/hemilabs/heminetwork/releases/download/v0.11.5/heminetwork_v0.11.5_darwin_amd64.tar.gz
     ```
   - For Apple Silicon (M1/M2, arm64):
     ```bash
     wget https://github.com/hemilabs/heminetwork/releases/download/v0.11.5/heminetwork_v0.11.5_darwin_arm64.tar.gz
     ```

2. **Create a Directory for Hemi**
   ```bash
   mkdir hemi
   ```

3. **Extract the Downloaded Archive**
   ```bash
   tar --strip-components=1 -xzvf heminetwork_v0.11.5_darwin_amd64.tar.gz -C hemi
   ```

4. **Navigate to the Hemi Directory**
   ```bash
   cd hemi
   ```

### Configuration

5. **Generate Wallet (MUST DO)**
   ```bash
   ./keygen -secp256k1 -json -net="testnet" > popm-address.json
   ```
   - If you already have a wallet, generate a new one and import your old private key in step 7.

6. **View Wallet Information**
   ```bash
   cat popm-address.json
   ```

7. **Set Up Environment Variables (MUST DO)**
   - Replace `yourpk` with your private key.
   ```bash
   export POPM_BTC_PRIVKEY=yourpk
   export POPM_STATIC_FEE=3500
   export POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public
   ```

### Run the Miner

8. **Start a Screen Session**
   ```bash
   screen -S Hemi-Miner
   ```

9. **Start the Hemi Miner**
   ```bash
   ./popmd
   ```

10. **Detach from Screen Session** (so it runs in the background)
    ```bash
    ctrl a + d
    ```

11. **Reattach to the Screen Session**
    ```bash
    screen -r Hemi-Miner
    ```

## Additional Notes

- Ensure you replace placeholder values and settings with those specific to your configuration.
- Refer to the [Hemi Network documentation](https://github.com/hemilabs/heminetwork) for more detailed information and updates.

For support or questions, please contact our community via [Hemi Network GitHub](https://github.com/hemilabs/heminetwork).

Happy mining! 🚀
