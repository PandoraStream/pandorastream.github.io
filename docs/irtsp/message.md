---
title: iRTSP Message
layout: default
parent: iRTSP Protocol
nav_order: 1
---

# iRTSP Message

An iRTSP message is composed as follows:

```
Version + CRLF
"Seq" + = + Sequence Number + CRLF
Type + / + Method (+ / + Code) + CRLF
Header (+ = + Value) + CRLF
...
"Submit" + CRLF
```

All iRTSP messages end with the word `Submit`, followed by a `CRLF`.

Example iRTSP request:

```
iRTSP/1.21
Seq=0
SET/START
t=45850
sc
Submit

```

Example iRTSP response:

```
iRTSP/1.21
Seq=0
RSP/START/200
t=45850,1806955874,1806955874
sc=tls
Submit

```

## Version

This represents the iRTSP version used. Example: `iRTSP/1.21`

## Sequence Number

This stores the sequence value of an iRTSP message. It works the same way as the `CSeq` header of a standard RTSP message.

## Message Type

This differentiates if an iRTSP message is a request or a response. If the message is a request, it will have the value `SET`. If the message is a response, then it will use the value `RSP`. Both the client and server can send request and response messages.

## Method

This stores the method used on the message. The known possible values are:
- START
- SETUP
- KNOCK
- PUSHINFO
- USERINFO
- REMOTECTL
- SET
- PLAY
- ECHO
- TEARDOWN

## Headers

All message headers have a header field and value. These are split with an equal sign `=` and with no spaces, instead of the usual two dots `:` used in standard RTSP.
