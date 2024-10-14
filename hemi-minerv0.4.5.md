# hemi-miner

## Official Tutorial for Setting Up Hemi-Miner

Welcome to the Hemi-Miner setup guide! Follow these steps to get Hemi-Miner up and running on your system.

### Prerequisites
Ensure you have `wget`, `tar`, `nano`, and basic terminal commands available on your system.

### Download and Setup

1. **Download the Hemi Network Binary**
   ```bash
   wget https://github.com/hemilabs/heminetwork/releases/download/v0.4.5/heminetwork_v0.4.5_linux_amd64.tar.gz
   ```

2. **Create a Directory for Hemi**
   ```bash
   mkdir hemi
   ```

3. **Extract the Downloaded Archive**
   ```bash
   tar --strip-components=1 -xzvf heminetwork_v0.4.5_linux_amd64.tar.gz -C hemi
   ```

4. **Navigate to the Hemi Directory**
   ```bash
   cd hemi
   ```

5. **View Help Information (optional)**
   ```bash
   ./popmd --help
   ```

### Configuration

6. **Generate Wallet (MUST DO)**
   ```bash
   ./keygen -secp256k1 -json -net="testnet" > popm-address.json
   ```
   IF YOU HAVE OLD WALLET YOU MUST DO GENERATE WALLET AND THEN INPORT YOUR OLD PRIVATE KEY IN NUMBER 8

7. **SEE WALLET**
   ```bash
   cat popm-address.json
   ```

8. **Set Up Environment Variables**
   Replace `yourpk` with your private key.
   ```bash
   export POPM_BTC_PRIVKEY=yourpk
   export POPM_STATIC_FEE=400
   export POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public
   ```

### Run the Miner

**USE SCREEN**
   ```bash
   screen -S Hemi-Miner
   ```

9. **Start the Hemi Miner**
   ```bash
   ./popmd
   ```
   
**CLOSE SCREEN**
   ```bash
   ctrl a + d 
   ```

## Additional Notes

- Ensure you replace placeholder values and settings with those specific to your configuration.
- Refer to the [Hemi Network documentation](https://github.com/hemilabs/heminetwork) for more detailed information and updates.

For support or questions, please contact our community via [Hemi Network GitHub](https://github.com/hemilabs/heminetwork).

Happy mining! 🚀
