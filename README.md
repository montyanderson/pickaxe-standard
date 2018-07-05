---
title: Pickaxe
author: Monty Anderson (@montyanderson)
discussions-to: work@montyanderson.net
type: ERC
created: 2018-07-05
---

## Simple Summary

A standard interface for proof-of-work tokens with proportional mining.

## Abstract

This specification defines a standardised set of methods for implementing a token with decentralised distribution. However, unlike other proof-of-work token standards, tokens can be dispensed to a miner hashing at any arbitrary difficulty, with a relative payout.

## Motivation

While there exist many currencies and tokens using PoW, none allow for multiple miners to receive a payout per block. This means that centralised mining pools must be setup, increasing labour and fees required. Ethereum PoW tokens also have high fees that serve as a disincentive as they must be paid for every single block payout.

Pickaxe solves both of these problems: any amount of miners can receive a payout per block (*jackpot*); miners can mine on a high difficulty over a large time period to alleviate transaction fees.

## Specification

### Interface

``` solidity
contract Pickaxe {
    uint constant jackpot = 512000000000000000000;
    uint jackpotDifficulty = 1000000;

    uint constant jackpotPeriodDuration = 86400;
    uint jackpotPeriodStart = 0;
    uint minted = 0;

    uint constant maxTarget = ~uint(0);

    uint supply = 0;
    bytes32 challenge;

    event Mint(address indexed from, uint reward, bytes32 newChallenge);

    function mint(uint nonce, uint rewardDifficulty);
}
```

## Rationale

## Backwards Compatibility

## Test Cases

## Implementation

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
