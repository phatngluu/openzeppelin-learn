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