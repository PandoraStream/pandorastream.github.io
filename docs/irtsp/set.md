---
title: SET method
layout: default
parent: iRTSP Protocol
nav_order: 8
---

# SET method

This method configures the properties for the video and audio streams.

## Request

| Header    | Description                                                                       |
|-----------|-----------------------------------------------------------------------------------|
| v         | The [configuration](#video-configuration) for the video stream                    |
| a         | The [configuration](#audio-configuration) for the audio stream                    |
| streaming | The [streaming type](/docs/media-stream#streaming-type) to be used on the streams |
| bt        | The bitrate (Kbps) to be used on the streams                                      |
| t         | Unknown, possibly time related                                                    |

Example:

```
iRTSP/1.21
Seq=5
SET/SET
v=31,800,25,400,240;
a=61,32,44100,2;
streaming=iDataChunk;
bt=1000
t=1468689
Submit

```

## Response

| Header    | Description                                                                 |
|-----------|-----------------------------------------------------------------------------|
| streaming | The [streaming type](/docs/media-stream#streaming-type) used on the streams |
| bt        | The bitrate (Kbps) used on the streams                                      |
| t         | Unknown, possibly time related                                              |

Example:

```
iRTSP/1.21
Seq=5
RSP/SET/200
streaming=iDataChunk;
bt=1000;
t=1468689,1877240442,1877240451
Submit

```

## Video Configuration

The video configuration consists on an array of values which define certain properties that the video stream will use.

Example: `31,800,25,400,240`

| Index | Description            |
|-------|------------------------|
| 0     | Video codec (31: H264) |
| 1     | Video bitrate (Kbps)   |
| 2     | Video framerate        |
| 3     | Video width            |
| 4     | Video height           |

## Audio Configuration

The audio configuration consists on an array of values which define certain properties that the audio stream will use.

Example: `61,32,44100,2`

| Index | Description           |
|-------|-----------------------|
| 0     | Audio codec (61: MP3) |
| 1     | Audio bitrate (Kbps)  |
| 2     | Audio frequency (Hz)  |
| 3     | Audio channels?       |
