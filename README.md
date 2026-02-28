Foundry Fund MeThis project is a decentralized funding application built with Foundry. It allows users to fund the contract with ETH based on a minimum USD value tracked via Chainlink Price Feeds. The owner of the contract can withdraw the funds at any time.## FeaturesDecentralized Funding: Users can send ETH to the contract.Price Conversion: Uses Chainlink Oracles to ensure a minimum USD requirement is met.Automated Scripts: Includes helper scripts for deployment and interactions (funding/withdrawing).Robust Testing: Comprehensive unit and integration tests.CI/CD Integration: Optimized for GitHub Actions.## Getting Started### PrerequisitesEnsure you have Foundry installed.Bashcurl -L https://foundry.paradigm.xyz | bash
foundryup
### InstallationClone the repository and install dependencies:Bashgit clone https://github.com/olayinkasanusi/foundry-fundme
cd foundry-fundme
forge install
### Local DevelopmentBuild the project:Bashforge build
Run tests:Bashforge test
Format code:Bashforge fmt
## Project StructureFolderDescriptionsrc/The core Smart Contracts (FundMe.sol, PriceConverter.sol).script/Deployment and interaction scripts.test/Unit and Integration tests.lib/External dependencies (Chainlink, Forge-Std, DevOps).## DeploymentTo deploy to a local or live network:Bash# Example for Sepolia
forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY
## InteractionsFunding the contract:Bashforge script script/interactions.s.sol:FundFundMe --rpc-url $RPC_URL --private-key $PRIVATE_KEY --broadcast
Withdrawing funds:Bashforge script script/interactions.s.sol:WithdrawFundMe --rpc-url $RPC_URL --private-key $PRIVATE_KEY --broadcast
## LicenseThis project is licensed under the MIT License.