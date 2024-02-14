---
title: START method
layout: default
parent: iRTSP Protocol
nav_order: 2
---

# START method

The START method initializes the connection between the client and the server, and it allows them to share their capabilities, such as the scheme used for the protocol.

## Request

| Header | Description                         |
|--------|-------------------------------------|
| sc     | The client minimum supported scheme |
| t      | Unknown, seems to be time related   |

Example:

```
iRTSP/1.21
Seq=0
SET/START
sc
t=1454326
Submit

```

## Response

| Header | Description                         |
|--------|-------------------------------------|
| t      | Unknown, seems to be time related   |
| sc     | The server minimum supported scheme |

Example:

```
iRTSP/1.21
Seq=0
RSP/START/200
t=45850,1806955874,1806955874
sc
Submit

```

## Scheme

The currently known values for the scheme are:
- Empty value, in which case it represents the raw protocol with no encryption
- `tls`, which represents TLS encryption. If this value is returned as response, the client and server will perform a TLS handshake and continue the following messages over TLS
