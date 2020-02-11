# Blocks

## Block Header

| Bytes |        Value        |
| :---: | :-----------------: |
|   1   |       Version       |
|   32  | Previous block hash |
|   32  |     Merkle root     |
|   4   |      Timestamp      |
|   4   |        Target       |
|   4   |        Nonce        |

## Block

| Bytes |         Value        |
| :---: | :------------------: |
|   77  |        Header        |
|   4   |  Number of contracts |
|   ?   | Serialized contracts |
