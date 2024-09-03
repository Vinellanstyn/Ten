# Ten
### Running a Validator Node for Ten.xyz

To set up a validator node on the Ten.xyz network, follow these steps:

1. **System Requirements**:
   - **Hardware**: Ensure you have a server or VM with at least 8 CPU cores, 32 GB RAM, and 1 TB SSD storage.
   - **Operating System**: Ubuntu 20.04 LTS or later is recommended.
   - **Network**: A stable internet connection with at least 100 Mbps bandwidth is crucial for node operation.

2. **Software Installation**:
   - **Install Dependencies**:
     ```bash
     sudo apt update && sudo apt install -y build-essential curl jq
     ```
   - **Install Docker** (required for containerized deployment):
     ```bash
     curl -fsSL https://get.docker.com -o get-docker.sh
     sudo sh get-docker.sh
     ```
   - **Install Node.js** (for managing scripts):
     ```bash
     curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
     sudo apt-get install -y nodejs
     ```

3. **Get the Node Software**:
   - Clone the official repository:
     ```bash
     git clone https://github.com/ten-xyz/validator-node.git
     cd validator-node
     ```

4. **Configuration**:
   - Set up environment variables:
     ```bash
     cp .env.example .env
     nano .env
     ```
   - Fill in the required fields, such as `NODE_NAME`, `VALIDATOR_KEY`, and other network settings.

5. **Run the Node**:
   - Start the node using Docker:
     ```bash
     docker-compose up -d
     ```
   - Monitor the logs to ensure everything is running smoothly:
     ```bash
     docker-compose logs -f
     ```

6. **Continuous Attestation**:
   - The node must pass Secure Enclave attestation to participate in the network. This process verifies that your node operates within a secure and genuine environment, maintaining network integrity.

7. **Staking and Rewards**:
   - As a validator, you'll need to stake a certain amount of tokens, which acts as collateral. You can earn rewards for honest behavior and be penalized for malicious actions or failures.
