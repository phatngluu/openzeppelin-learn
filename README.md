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
