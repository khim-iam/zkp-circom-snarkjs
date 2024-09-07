# ZK-Snark Proof System: Using CIRCOM

This project demonstrates the setup and implementation of a Zero-Knowledge Proof (ZK-Snark) system using CIRCOM and SnarkJS. It covers the entire process from circuit creation to proof generation and verification.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)

## Introduction

Zero-Knowledge Proofs (ZKPs) are cryptographic protocols that allow one party (the prover) to prove to another party (the verifier) that they know a value, without revealing the value itself. This project focuses on creating a simple ZK-Snark system where a prover can prove knowledge of a pre-image of a hash without revealing the pre-image.

## Features

- **Circuit Design**: Create a circuit using CIRCOM to perform hash computations.
- **Proof Generation**: Generate cryptographic proofs using SnarkJS.
- **Verification**: Verify proofs both off-chain and on-chain.

## Prerequisites

- **Node.js**: Install Node.js from [nodejs.org](https://nodejs.org/)
- **CIRCOM Compiler**: Follow the installation steps from [CIRCOM documentation](https://docs.circom.io/getting-started/installation/)
- **SnarkJS**: JavaScript library for ZK-Snark proof generation and verification.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/zk-snark-proof-system.git
    cd zk-snark-proof-system
    ```

2. Install Node.js dependencies:
    ```bash
    npm install
    ```

3. Install CIRCOM library:
    ```bash
    npm install circomlib
    ```

4. Download the ptau file:
    ```bash
    wget https://hermez.s3-eu-west-1.amazonaws.com/powersOfTau28_hez_final_12.ptau
    ```

## Usage

1. **Compile the circuit:**
    ```bash
    circom circuit.circom --r1cs --wasm
    ```

2. **Generate proving and verification keys:**
    ```bash
    npx snarkjs groth16 setup circuit.r1cs powersOfTau28_hez_final_12.ptau circuit_0000.zkey
    ```

3. **Generate a proof:**
    ```bash
    node index.js
    ```

4. **Verify the proof:**
    ```bash
    node verify.js
    ```
