# Contracts

## Placement

This is the structure that represents a placement of multiple marbles.

| Bytes |      Value      |
| :---: | :-------------: |
|   1   | Number of types |
|   1   |   Marble type   |
|   4   |      Amount     |
|  ...  |       ...       |
|   1   |   Marble type   |
|   4   |      Amount     |

## StartContract

This contract must be signed by both players in order to create a new game.  

| Bytes |       Value       |
| :---: | :---------------: |
|   1   |      Version      |
|   1   |      Type = 0     |
|   ?   |  Fee (placement)  |
|   ?   | Player1 placement |
|   ?   | Player2 placement |
|   25  |  Player1 address  |
|   25  |  Player2 address  |
|   4   |   Player1 nonce   |
|   65  |    Player1 sig    |
|   4   |   Player2 nonce   |
|   65  |    Player2 sig    |

## ThrowContract

This contract is broadcast each time a player plays a round

| Bytes |      Value      |
| :---: | :-------------: |
|   1   |     Version     |
|   1   |     Type = 1    |
|   ?   | Fee (placement) |
|   1   |     Vector.X    |
|   1   |     Vector.Z    |
|   32  |    Game hash    |
|   1   |   Throw nonce   |
|   4   |   Player nonce  |
|   65  |    Signature    |

## TransactionContract

This contract must be signed by both players in order to instantly exchange marbles.  

| Bytes |       Value       |
| :---: | :---------------: |
|   1   |      Version      |
|   1   |      Type = 2     |
|   ?   |  Fee (placement)  |
|   ?   | Player1 placement |
|   ?   | Player2 placement |
|   25  |  Player1 address  |
|   25  |  Player2 address  |
|   4   |   Player1 nonce   |
|   65  |    Player1 sig    |
|   4   |   Player2 nonce   |
|   65  |    Player2 sig    |
