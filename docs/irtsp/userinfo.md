---
title: USERINFO method
layout: default
parent: iRTSP Protocol
nav_order: 6
---

# USERINFO method

This method lets the server know the client's user ID.

## Request

| Header | Description                                                           |
|--------|-----------------------------------------------------------------------|
| userid | The client user ID. If it's not defined, the value is set to `(null)` |

Example:

```
iRTSP/1.21
Seq=3
SET/USERINFO
userid=(null)
Submit

```

## Response

The response doesn't include any headers.

Example:

```
iRTSP/1.21
Seq=3
RSP/USERINFO/200
Submit

```
