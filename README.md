# poly4th
# MyCircuit

This is a Circom circuit template written in version 2.0.0 of Circom. The circuit includes components for AND, NOT, and OR gates. The main purpose of this template is to perform logic operations on two input signals, a and b, and produce an output signal, q.

## Circuit Components
- AND Gate: The AND gate takes input signals a and b and produces an output signal, x, representing the logical AND of a and b.
- NOT Gate: The NOT gate takes input signals a and b and produces an output signal, y, which simulates the logical NOT operation on a and b.
- OR Gate: The OR gate takes input signals X and Y and produces the final output signal, q, representing the logical OR of x and y.

## Usage

To use this circuit template, provide input values for signals a and b. The circuit will then calculate the values of signals x, y, and q based on the defined logic operations. The output value of q will be logged for reference.

## Example Input

The example input provided for this circuit is:

```json
{
    "a": 0,
    "b": 1
}
```

## Deployment
### Installation
To install the necessary dependencies, run `npm i` in your project directory.

### Compilation
Compile the project by running `npx hardhat circom`. This will generate the `out` directory containing circuit intermediaries and the `MultiplierVerifier.sol` contract.

### Proof Generation and Deployment
Use the command `npx hardhat run scripts/deploy.ts --network mumbai` to execute the deployment script. This script performs the following tasks:

1. Deploys the `MultiplierVerifier.sol` contract on the blockchain.
2. Generates a proof using circuit intermediaries with the `generateProof()` function.
3. Creates calldata for the verification process using the `generateCallData()` function.
4. Calls the `verifyProof()` method on the deployed Verifier contract with the generated calldata to verify the proof.

By running this script, you will deploy the Verifier contract and verify the proof against the circuit, ensuring the correctness of your implementation.

## Instructions

To successfully compile and verify the correctness of the circuit, follow these steps:

1. Write the correct implementation of the `circuit.circom` file based on the provided template. Ensure that the defined AND, XOR, and OR gates perform the intended logic operations.

2. Compile the circuit to generate circuit intermediaries using the Circom compiler. This will produce files necessary for proof generation and verification.

3. Generate a proof using the input values `a=0` and `b=1`. The proof will demonstrate the correctness of the circuit for these specific inputs.

4. Deploy the Verifier contract that provides the `verifyProof()` method. This contract will verify the generated proof against the circuit.

5. Call the `verifyProof()` method on the deployed Verifier contract with the proof and the input values `A=0` and `B=1`. The method should return `true` if the proof is valid for the given inputs, indicating that the circuit implementation is correct.

6. Assert that the output of the `verifyProof()` method is `true`. This will validate the correctness of the circuit.

## License
This project is licensed under the MIT License. You are free to modify and distribute the code for personal and educational purposes.
