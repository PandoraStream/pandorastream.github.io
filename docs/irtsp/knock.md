---
title: KNOCK method
layout: default
parent: iRTSP Protocol
nav_order: 4
---

# KNOCK method

The KNOCK method is used for getting the KNOCK media stream. In this stream, the server sends random data to the client at a certain bitrate set by the client. This is used for testing the connection and determining its speed.

## Request

| Header  | Description                                 |
|---------|---------------------------------------------|
| Bitrate | The bitrate (Kbps) to be used in the stream |

Example:

```
iRTSP/1.21
Seq=2
SET/KNOCK
Bitrate=1400
Submit

```

## Response

| Header | Description                                                        |
|--------|--------------------------------------------------------------------|
| p      | The [media header](/docs/media-stream#media-header) for the stream |

Example:

```
iRTSP/1.21
Seq=2
RSP/KNOCK/200
p=iDataChunk/unicast/tcp/44805;
Submit

```
