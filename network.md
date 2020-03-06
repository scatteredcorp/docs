# Network

## Message header

| Bytes |       Value       |
| :---: |  :-------------:  |
|   1   |  Magic (network)  |
|   1   |      Command      |
|   4   |     Total size    |
|   4   |      Checksum     |
|   ?   |  Message content  |
