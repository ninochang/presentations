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
- Latency (3 ~ 5s)
- RTMP still supported on many platform as publish protocol even though flash player is offically dead.
    
---
![original](background.png)

# RTMP - Summary
- Pros:
    - High device compatabillity
    - Low resource usage due to TCP packets ordering.
- Cons:
    - Old codecs
    - Vulnerable to bandwidth and network issues.

^ 
- 完全依賴TCP 處理 loss packet, 容易在網路不穩情況受 congestion control 影響造成 delay.
- Enhanced-RTMP support VP9, HEVC, and AV1

---
![original](background.png)

# WebRTC

- **UDP** (default) and **TCP**
- Supported codecs:
    - video: VP8, VP9, H.264 (H.265, AV1 ... in progress)
    - audio: Opus (... inprogress)
- Lattency (< 500ms)
- Products: 
    - Discord [^1]
    - Google meet

[^1]: [Discord blog discribe their webRTC architecture](https://discord.com/blog/how-discord-handles-two-and-half-million-concurrent-voice-users-using-webrtc)

---
[.build-lists: true]

![original](background.png)

# Why WebRTC is not codec agnostic ?
- Relies codes supported by underlying browser.
- Browser don't support specific codec for various reason, like expensive livense to use H.265.
- Hardware encoding requirement for some codec like H.265, AV1 
(But newer chrome starts support hardware encode)

---
[.build-lists: true]

![original](background.png)
# How does WebRTC handle packet loss ?
- Forward Error Correction (FEC): Add redundant information to the transmitted packets, Allowing receiver to reconstruct lost packets even if they are not received.

- NACK: NACK notify sender to retransmit missing packets and fill in the gaps to maintain playback continuity.

- Adaptive bitrate control: Dynamically adjust the bitrate of the transmitted media stream based on network conditions.

---
![original](background.png)

# WebRTC - Summary

- Pros:
    - Strong security ensured by SRTP[^2]
    - Strong Community support, work on almost every browser.
    - High stability under bad network
- Cons:
    - Hard to scale when there's multi participants
    

[^2]: [Secure Real-Time Transport Protocol](https://datatracker.ietf.org/doc/html/rfc3711)

---
![original](background.png)

# SRT

- **UDP** based
- Supported codec: codec agnostic
- Lattency: (< 500ms)
- Loss packet handling: FEC, ARQ, Too-late packet
- Timestamp-Based Packet Delivery (TSBPD)

---
[.build-lists: true]

![original](background.png)

# Why SRT codec agnostic ?
- It doesn't have any codec limitation on data processing, 
the responsibility of encoding/decoding fall on upstream app using SRT.
- Acting as a normal udp packet wrap SRT content.

---
![original](background.png)

# SRT - Summary

- Pros:
    - Codec agnostic
    - Strong security ensured by AES encrypted content.
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
<!-- ![original](background.png) -->
# [fit] Quest: What video/audio codec does 
# [fit] **RTMP** support ?

- video: H.264
- audio: AAC

---
<!-- ![original](background.png) -->

# [fit] Deep dive into
# [fit]  **SRT**

---
![original](background.png)

# Timestamp-Based Packet Delivery
Timestamps allow the decoder to **reorder** packets if they arrive out of order due to network delays or retransmissions. Ensuring frames are decoded and displayed in the correct order.

---
![inline](srt-tsbpd.png)

--- 
![original](background.png)

# Automatic Repeat Request

---
# Packet Delivery Time
[TODO]
- Describe fomulla.

---
# [fit] Quest: packet delivery time 

---
![original](background.png)
# Too Late Packet

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
