# Network

## Message

Below is the minimal structure for a network message:

| Bytes |       Value       |
| :---: |  :-------------:  |
|   1   |  Magic (network)  |
|   1   |      Command      |
|   4   |     Total size    |
|   4   |      Checksum     |
|   ?   |  Message content  |
