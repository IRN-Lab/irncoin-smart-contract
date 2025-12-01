Smart Contract Documentation – IRN Coin

This document explains the architecture, functions, and behavior of the IRN Coin smart contract deployed on the Polygon PoS network.

Contract Information

• Contract Name: IRNCoin

• Solidity Version: ^0.8.20

• Standard: ERC‑20

• Network: Polygon Proof‑of‑Stake (PoS)

• License: MIT

Core Features

The contract includes the following key functionalities:

• Total supply is fixed at 255,000,000 IRN

• Uses OpenZeppelin ERC20 standard implementation

• Safe and gas‑efficient transfer functions

• Supports standard functions such as transfer, approve, transferFrom, allowance, and balanceOf

• No minting capability (total supply cannot increase)

• No ownership‑restricted functions

• Fully decentralized ERC‑20 behavior

Constructor Behavior

Upon deployment:

• The entire token supply is minted once

• All tokens are assigned to the deployer (msg.sender)

• No further supply creation is possible

Functions Overview

The following functions are part of the contract:

• totalSupply()

Returns the total number of IRN tokens in existence.

• balanceOf(address account)

Returns the token balance of a given address.

• transfer(address to, uint256 amount)

Transfers tokens to another address.

• approve(address spender, uint256 amount)

Allows an address to spend tokens on behalf of the owner.

• transferFrom(address from, address to, uint256 amount)

Transfers tokens from an approved address.

• allowance(address owner, address spender)

Returns the remaining allowance of the spender.

Security Notes

• Uses SafeMath‑compatible logic built into Solidity 0.8+

• No owner privileges, no mint, no pause functions

• Immutable supply ensures protection against inflation

• Standard ERC‑20 behavior reduces security risks
