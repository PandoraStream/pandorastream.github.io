---
title: PLAY method
layout: default
parent: iRTSP Protocol
nav_order: 9
---

# PLAY method

This method starts the transmission of the video, audio and control streams.

## Request

| Header | Description                       |
|--------|-----------------------------------|
| t      | Unknown, seems to be time related |

Example:

```
iRTSP/1.21
Seq=6
SET/PLAY
t=1469001
Submit

```

## Response

| Header | Description                       |
|--------|-----------------------------------|
| t      | Unknown, seems to be time related |

Example:

```
iRTSP/1.21
Seq=6
RSP/PLAY/200
t=1469001,1877240750,1877240750
Submit

```
