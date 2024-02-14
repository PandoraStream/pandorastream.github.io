---
title: PUSHINFO method
layout: default
parent: iRTSP Protocol
nav_order: 5
---

# PUSHINFO method

This method is requested by the server to the client to give information about the result of the connection test.

## Request

The request can be either:

| Header  | Description                             |
|---------|-----------------------------------------|
| Bitrate | The result bitrate (Kbps) in the stream |

Or, if the connection test fails:

| Header | Description    |
|--------|----------------|
| Error  | The error code |

Example for a successful connection:

```
iRTSP/1.21
Seq=0
SET/PUSHINFO
Bitrate=888
Submit

```

Example for a too slow connection:

```
iRTSP/1.21
Seq=0
SET/PUSHINFO
Error=1014
Submit

```

## Response

The response doesn't include any headers.

Example:

```
iRTSP/1.21
Seq=0
RSP/PUSHINFO/200
Submit

```
