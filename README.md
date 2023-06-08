# Toncli-local
This branch contains special version of TVM with the following new instructions:

## New TVM instructions

| xxxxxxxxxxxxxxxx<br/>Name | xxxxxxxx<br/>Opcode | xxxxxxxxxxxx<br/>Stack | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx<br/>Description                                                                                                                                                                                                                                           |
|:-----------------------------|:------------------------|:--------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `GASLIMITSTEMP`              | **`FEEF10`**            | _`- g_l g_r`_             | Returns the current gas limit `g_l` and remainig gas `g_r`.                                                                                                                                                                                                                                                                    |
| `PRIVTOPUB`                  | **`FEEF11`**            | _`priv - pub`_            | Converts Ed25519 private key into a public key.<br/>Both keys are represented as 256-bit unsigned integers.                                                                                                                                                                                                                    |
| `SIGN`                       | **`FEEF12`**            | _`x p - s`_               | Signs a 256-bit unsigned integer `x` using a private key `p`.<br/>Key is represented as a 256-bit unsigned integer.<br/>Signature is returned as a slice. It can be checked using [`CHKSIGNU`](https://ton.org/docs/#/smart-contracts/tvm-instructions/instructions?id=instr-chksignu).                                        |
| `SIGNS`                      | **`FEEF14`**            | _`x p - s`_               | Signs data portion of slice `x` using a private key `p`. Bit length of `x` should be divisible by 8.<br/>Key is represented as a 256-bit unsigned integer.<br/>Signature is returned as a slice. It can be checked using [`CHKSIGNS`](https://ton.org/docs/#/smart-contracts/tvm-instructions/instructions?id=instr-chksigns). |
| `RESETLOADEDCELLS`           | **`FEEF13`**            | _`-`_                     | Future cell loads will consume gas as if no cells were loaded before `RESETLOADEDCELLS`.                                                                                                                                                                                                                                       |


## Links
* [Toncli](https://github.com/disintar/toncli)
* [TON main repository](https://github.com/ton-blockchain/ton)