---
title: TEARDOWN method
layout: default
parent: iRTSP Protocol
nav_order: 11
---

# TEARDOWN method

This method stops the transmission of all media streams.

## Request

The request doesn't include any headers.

Example:

```
iRTSP/1.21
Seq=1
SET/TEARDOWN
Submit

```

## Response

The response doesn't include any headers.

Example:

```
iRTSP/1.21
Seq=1
RSP/TEARDOWN/200
Submit

```
