---
title: Media streams
layout: default
---

# Media Streams

A media stream is a connection where data will be transmitted, either from the server to the client or the client to the server.

## Stream Types

There are 4 stream types:

- **Video**, where video data will be transmitted from the server to the client.
- **Audio**, where audio data will be transmitted from the server to the client.
- **Control**, where game input will be sent from the client to the server. The control stream can share the same port as another stream, like video.
- **Knock**, where the server sends lots of data to the client to perform a connection test.

## Media Header

A media header contains data about the properties that a stream will use. It consists of 4 sections:

`Streaming Type + / + Delivery Type + / + Transmission Protocol (+ / + Media Port)`

Example: `iDataChunk/unicast/tcp/40603`

### Streaming Type

How the media will be streamed. The only known value is `iDataChunk`, in which the data is sent over chunks.

### Delivery Type

How the data is delivered. The only known value is `unicast`, though it's possible that exists a `multicast` mode.

### Transmission Protocol

The protocol to use for transmission. Only two values are known: `tcp` and `ust`. In `ust`, a custom protocol over UDP is used. This protocol is used in Dragon Quest X Online as a "slow connection" mode.

### Media Port

The port that the client connect to to receive or send the media. This field isn't present when the client sends the media requirements on the SETUP method over iRTSP.
