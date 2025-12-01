Developer Guide – IRN Coin (IRN)

This document provides technical instructions for developers integrating IRN Coin into their Web3 applications using Ethers.js or Web3.js.

Network Information

• Network: Polygon PoS

• Standard: ERC‑20

• Contract Name: IRNCoin

• Solidity Version: ^0.8.20

• Total Supply: 255,000,000 IRN

• ABI File: /abi/IRNCoin.json

Contract Address

Provide the deployed contract address here once deployment is complete:

<To be added after deployment>

Importing ABI (Ethers.js)


content_copy
javascript

note_add
ویرایش با Canvas
import { ethers } from "ethers";
import irnAbi from "./IRNCoin.json";

const provider = new ethers.providers.JsonRpcProvider("https://polygon-rpc.com");
const contractAddress = "<IRN_CONTRACT_ADDRESS>";

const IRN = new ethers.Contract(contractAddress, irnAbi, provider);
Read Wallet Balance


content_copy
javascript

note_add
ویرایش با Canvas
const balance = await IRN.balanceOf("0xUserAddress");
console.log("Balance:", ethers.utils.formatUnits(balance, 18), "IRN");
Transfer Tokens


content_copy
javascript

note_add
ویرایش با Canvas
const wallet = new ethers.Wallet(PRIVATE_KEY, provider);
const IRNWithSigner = IRN.connect(wallet);

await IRNWithSigner.transfer("0xRecipient", ethers.utils.parseUnits("100", 18));
Check Allowance


content_copy
javascript

note_add
ویرایش با Canvas
const allowance = await IRN.allowance("0xOwner", "0xSpender");
console.log("Remaining Allowance:", allowance.toString());
Approve Spender


content_copy
javascript

note_add
ویرایش با Canvas
await IRNWithSigner.approve("0xSpender", ethers.utils.parseUnits("5000", 18));
Events

The smart contract emits standard ERC‑20 events:

• Transfer

• Approval

Developers may subscribe to events:


content_copy
javascript

note_add
ویرایش با Canvas
IRN.on("Transfer", (from, to, value) => {
  console.log(`Transfer: ${value} from ${from} to ${to}`);
});
Notes for Developers

• No owner / admin functions exist

• No mint / burn methods

• Fully decentralized supply

• Recommended RPC: Polygon mainnet or official providers

• Gas fees are extremely low on Polygon PoS

End of Developer Documentation
