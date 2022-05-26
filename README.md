# Create project
```
npm init -y
npm install --save-dev hardhat
```
# Compile with Hardhat
## Add `hardhat.config.js`
```
// hardhat.config.js

/**
* @type import('hardhat/config').HardhatUserConfig
*/
module.exports = {
  solidity: "0.8.4",
};
```
## Compile
```
npx hardhat compile
```
# Using OpenZeppelin Contracts
## Importing OpenZeppelin Contracts
```
npm install --save-dev @openzeppelin/contracts
```

- Ownable contract marks the deployer account as the contract’s owner, and provides a modifier called onlyOwner. When applied to a function, onlyOwner will cause all function calls that do not originate from the owner account to revert. Functions to transfer and renounce ownership are also available.

# Deploying and interacting
## Deploy
```
# Setting up a Local Blockchain
npx hardhat node

# Deploy smart contract
# Hardhat doesn’t currently have a native deployment system, instead we use scripts to deploy contracts.
# We will create a script to deploy our Box contract. We will save this file as scripts/deploy.js.
# We use ethers in our script, so we need to install it and the @nomiclabs/hardhat-ethers plugin.

npm install --save-dev @nomiclabs/hardhat-ethers ethers

# Deploy
npx hardhat run --network localhost scripts/deploy.js
```

## Interacting via Hardhat console
```
npx hardhat console --network localhost
> const Box = await ethers.getContractFactory('Box');
undefined
> const box = await Box.attach('0x5FbDB2315678afecb367f032d93F642f64180aa3')
undefined
> await box.store(42)
{
  hash: '0x3d86c5c2c8a9f31bedb5859efa22d2d39a5ea049255628727207bc2856cce0d3',
...
> await box.retrieve()
BigNumber { _hex: '0x2a', _isBigNumber: true }
> (await box.retrieve()).toString()
'42'
```
## Interacting programatically
```
// scripts/index.js
async function main () {
  // Your code goes here
}

main()
  .then(() => process.exit(0))
  .catch(error => {
    console.error(error);
    process.exit(1);
  });

npx hardhat run --network localhost ./scripts/index.js
```