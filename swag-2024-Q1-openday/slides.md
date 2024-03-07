footer: **SWAG** backend team
slidenumbers: true
build-lists: false

# [fit] Go download **demo** resources.
- https://shortlink/resource.
- An QRCode

---

![fit](cover.png)

---
![original](background.png)

# Outline
- RTMP vs WebRTC vs SRT
- Deep dive into SRT
- Our choise
- DEMO

---
![original](background.png)

# [fit] [TODO]一張圖開場，stream protocol 的演進


---
[.build-lists: false]
![original](background.png)

# RTMP 
- **TCP** based
- Supported codecs:
    - video: H.264
    - audio: AAC
- Support first mile and last mile.
- RTMP still supported on many platform as first mile protocol.
    
---
![original](background.png)

# RTMP - Summary
- Pros:
    - Low Latency (3 ~ 5s)
    - High device compatabillity
    - Low resource usage due to TCP packets ordering.
- Cons:
    - Old codecs
    - Vulnerable to bandwidth and network issues.

---
![original](background.png)

# WebRTC

- **UDP** (default) and **TCP**
- Supported codecs:
    - video: VP8, VP9, H.264
    - audio: Opus

- Products: 
    - Discord [^1]
    - Google meet

[^1]: [Discord blog discribe their webRTC architecture](https://discord.com/blog/how-discord-handles-two-and-half-million-concurrent-voice-users-using-webrtc)

---
![original](background.png)

# WebRTC - Connection Flow

1. Exchange SDP with **Signaling Server**
2. Collect **ICE candidates** with TURN server
3. Exchange ICE candidates
4. **UDP hole punching** estiblish connection

---
![original](background.png)

# WebRTC - Connection Flow

![inline](webrtc-connection.gif)

ref: https://medium.com/agora-io/how-does-webrtc-work-996748603141

---
![original](background.png)

# WebRTC - TURN

![inline](webrtc-TURN.gif)


^ If NAT or Firewall configuration doesn't allow peer connect directly, need rely on TURN server relay.

---
![original](background.png)

# WebRTC - SDP

- Session Description Protocol (SDP)
- Communicate **codec, address, media type, audio and video** between peers.

---
![original](background.png)

# WebRTC - ICE candidates

- Set of **public IP address and port** that could potentially be an address that receives data.
- Client will gathere them by making a series of requests to a STUN server.


---
![original](background.png)

# WebRTC - Summary

- Pros:
    - Low lattency (< 500ms)
    - Strong security ensured by SRTP[^2]
    - Strong Community support, work on almost every browser
- Cons:
    - Maintain STUN and TURN server
    - Hard to scale when there's multi participants
    

[^2]: [Secure Real-Time Transport Protocol](https://datatracker.ietf.org/doc/html/rfc3711)

---
![original](background.png)

# SRT

- **UDP** based
- Supported codec: codec agnostic
- Products

---
![original](background.png)

# SRT - Summary

- Pros:
    - Codec agnostic
    - AES encrypted content
    - High stability under bad network
- Cons:
    - Not support by native web, require special player.
    - Require extra bandwidth for SRT machanism maintain stream quality

---
![original](background.png)

| Protocol | RTMP | WebRTC | SRT |
| --- | --- | --- |--- |
| Supported codecs |H.264, AAC| H.264, VP9, VP8, Opus, G.711 G.722, iLBC, iSAC | Unlimited |
| Latency | < 5s | < 500ms | < 500ms|
| Security | Need Extension | Built in | Built in (AES) |
| Disruption Tolerance | Average | Good | Good |

---
[.build-lists: true]
![original](background.png)
# Quest: What video/audio codec does RTMP support ?

- video: H.264
- audio: AAC

---
![original](background.png)

# [fit] Deep dive into
# [fit]  **SRT**

---
![original](background.png)
# Timestamp-Based Packet Delivery

- **Reproduce** the timing of packets committed by the sending application to the SRT sender on **receiver** side.
- Allows packets to be **scheduled** for delivery by the SRT **receiver** making them ready to be read by the receiving application 

---
![inline](srt-tsbpd.png)

---
# Packet Delivery Time
[TODO]
- Describe fomulla.

---
# [TODO] Quest: packet delivery time 

---
![inline](srt-too-late-packet-drop.png)


---
![original](background.png)

# WebRTC References:
- https://medium.com/agora-io/how-does-webrtc-work-996748603141
- https://www.100ms.live/blog/webrtc-turn-server

---
![original](background.png)

# DEMO
