---
title: SETUP method
layout: default
parent: iRTSP Protocol
nav_order: 3
---

# SETUP method

The SETUP method is used for sharing the ports that will be used for media sharing by the server, or game input by the client.

## Request

| Header | Description                                                                                                                                                                                                             |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Token  | The first part (before the comma) seems to represent a decreasing counter with thenumber of times that the connection to the server has been tried. The value after the comma is an unknown token for client validation |
| v      | The [media requirements](/docs/media-stream#media-header) for the video stream                                                                                                                                          |
| a      | The [media requirements](/docs/media-stream#media-header) for the audio stream                                                                                                                                          |
| c      | The [media requirements](/docs/media-stream#media-header) for the control stream. The control stream is also designated by the `Ctrl` indicator at the start                                                            |
| t      | Unknown, seems to be time related                                                                                                                                                                                       |

Example:

```
iRTSP/1.21
Seq=1
SET/SETUP
Token=98,0123456789abcdef0123456789abcdef
v=iDataChunk/unicast/tcp;
a=iDataChunk/unicast/tcp;
c=Ctrl;iDataChunk/unicast/tcp;
t=1455116
Submit

```

## Response

| Header | Description                                                                |
|--------|----------------------------------------------------------------------------|
| v      | The [media header](/docs/media-stream#media-header) for the video stream   |
| a      | The [media header](/docs/media-stream#media-header) for the audio stream   |
| c      | The [media header](/docs/media-stream#media-header) for the control stream |
| t      | Unknown, seems to be time related                                          |

Example:

```
iRTSP/1.21
Seq=1
RSP/SETUP/200
v=iDataChunk/unicast/tcp/44803
a=iDataChunk/unicast/tcp/44804
c=iDataChunk/unicast/tcp/44803
t=1455116,1877227460,1877227504
Submit

```
