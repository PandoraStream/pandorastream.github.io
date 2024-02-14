---
title: ECHO method
layout: default
parent: iRTSP Protocol
nav_order: 10
---

# ECHO method

This method is used for validating that the server is still alive.

## Request

| Header | Description                       |
|--------|-----------------------------------|
| t      | Unknown, seems to be time related |

Example:

```
iRTSP/1.21
Seq=3
SET/ECHO
t=61018
Submit

```

## Response

The response doesn't include any headers.

Example:

```
iRTSP/1.21
Seq=3
RSP/ECHO/200
Submit

```
