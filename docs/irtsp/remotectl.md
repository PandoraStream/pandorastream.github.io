---
title: REMOTECTL method
layout: default
parent: iRTSP Protocol
nav_order: 7
---

# REMOTECTL method

This method serves an unknown purpose, but it's possibly passing information for configuring the control stream.

## Request

| Header | Description                                                                 |
|--------|-----------------------------------------------------------------------------|
| ctl    | Unknown, possibly containing information for configuring the control stream |

Example:

```
iRTSP/1.21
Seq=4
SET/REMOTECTL
ctl=wm/32805/0/0
Submit

```

## Response

The response doesn't include any headers.

Example:

```
iRTSP/1.21
Seq=4
RSP/REMOTECTL/200
Submit

```
