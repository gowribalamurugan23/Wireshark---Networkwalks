# Wireshark---Networkwalks



# 🦈 Wireshark SOC Analyst Project

Hands-on network traffic investigation using **Wireshark**, completed as part of the **Networkwalks Cybersecurity Internship (Week 1, SOC Project Module)**.

I played the role of a SOC analyst across **8 labs**: 2 foundation labs (capturing and analysing traffic) and 6 SOC investigation labs with 10 tasks each, covering attackers, conversations, plain-text passwords, brute-force attempts and a scam call.

**Result: all 8 labs completed. The 6 SOC labs scored 100/100 each (60/60 tasks, 8 November 2026).**

---

## 📌 Summary

| Lab | Title | Type | Result |
|-----|-------|------|--------|
| 1 | Packet Capture | Foundation (PDF) | Completed |
| 2 | PCAP Analysis | Foundation (PDF + PCAP) | Completed |
| 3 | Identify the Attacker's IP | SOC lab (10 tasks) | 100/100 |
| 4 | Follow TCP Stream 1 | SOC lab (10 tasks) | 100/100 |
| 5 | Follow TCP Stream, Part 2 | SOC lab (10 tasks) | 100/100 |
| 6 | HTTP Plain Text Credentials | SOC lab (10 tasks) | 100/100 |
| 7 | Catch the Brute Force Attacker | SOC lab (10 tasks) | 100/100 |
| 8 | Catch the Call Scammer | SOC lab (10 tasks) | 100/100 |

---

## 📡 Lab 1: Packet Capture

Capture my own Wi-Fi traffic while opening a website, then analyse it.

| # | Task | Status |
|---|------|--------|
| 1 | Find my own IP address | ✅ |
| 2 | Find the DNS server | ✅ |
| 3 | Find the website IP | ✅ |
| 4 | Find the Server Name (TLS handshake) | ✅ |
| 5 | Find the server port | ✅ |
| 6 | Find the TLS version | ✅ |

**What I did:** ran a live capture on the Wi-Fi interface, opened `networkwalks.com`, and filtered with `dns.qry.name == "networkwalks.com"`.

| Field | Observed |
|-------|----------|
| Client | 192.168.1.6 |
| DNS server | 1.1.1.1 |
| Query | A record for `networkwalks.com` (also AAAA) |
| Website IP | 192.232.216.135 |

**Skills:** live capture, DNS filtering, TLS handshake inspection.

---

## 🗂️ Lab 2: PCAP Analysis

Open a saved capture of `microsoft.com` and answer the same questions offline.

| # | Task | Status |
|---|------|--------|
| 1 | Open the PCAP file in Wireshark | ✅ |
| 2 | Find the client IP | ✅ |
| 3 | Find the DNS server | ✅ |
| 4 | Find the website IP | ✅ |
| 5 | Find the Server Name | ✅ |
| 6 | Find the server port and TLS version | ✅ |

**What I did:** unzipped and opened the capture (107 packets), then filtered with `dns.qry.name == "microsoft.com"` (4 packets displayed).

| Field | Observed |
|-------|----------|
| Client | 192.168.0.105 |
| DNS server | 8.8.8.8 |
| Query | A and AAAA for `microsoft.com` |
| Response | Multiple A records returned |

**Skills:** offline PCAP analysis, DNS query/response matching, reading packet details and hex.

---

## 🔍 Lab 3: Identify the Attacker's IP

Find the attacker's IP address in the traffic by analysing a port scan.

| # | Task | Status |
|---|------|--------|
| 1 | Capture the traffic | ✅ |
| 2 | Show only SYN packets | ✅ |
| 3 | Find the attacker | ✅ |
| 4 | Find the target | ✅ |
| 5 | Source port | ✅ |
| 6 | Ports probed | ✅ |
| 7 | Open ports | ✅ |
| 8 | Reply for closed ports | ✅ |
| 9 | Closed ports | ✅ |
| 10 | Attack type | ✅ |

**Skills:** SYN filtering, handshake analysis, open vs closed port replies, scan identification.

---

## 💬 Lab 4: Follow TCP Stream 1

Rebuild a conversation and read what was sent.

| # | Task | Status |
|---|------|--------|
| 1 | Capture the traffic | ✅ |
| 2 | Find the chat port | ✅ |
| 3 | Who started the chat? | ✅ |
| 4 | Stream number | ✅ |
| 5 | Size of the chat | ✅ |
| 6 | Who needs help? | ✅ |
| 7 | The problem drive | ✅ |
| 8 | Temporary password | ✅ |
| 9 | Guest Wi-Fi password | ✅ |
| 10 | Text colour | ✅ |

**Skills:** Follow TCP Stream, stream indexing, reading unencrypted chat data.

---

## 🕵️ Lab 5: Follow TCP Stream, Part 2

Practise Follow TCP Stream on a new capture and find the hidden data.

| # | Task | Status |
|---|------|--------|
| 1 | Capture the traffic | ✅ |
| 2 | Find the pages | ✅ |
| 3 | Where is it hidden | ✅ |
| 4 | Find the stream | ✅ |
| 5 | The code word | ✅ |
| 6 | The backup server | ✅ |
| 7 | Which direction | ✅ |
| 8 | Status code | ✅ |
| 9 | The downloaded file | ✅ |
| 10 | Who made the report | ✅ |

**Skills:** HTTP analysis, hidden data discovery, traffic direction, status codes, file identification.

---

## 🔓 Lab 6: HTTP Plain Text Credentials

Find usernames and passwords sent in clear text over HTTP.

| # | Task | Status |
|---|------|--------|
| 1 | Capture the traffic | ✅ |
| 2 | Which protocol | ✅ |
| 3 | The method | ✅ |
| 4 | The login page | ✅ |
| 5 | The PC that signed in | ✅ |
| 6 | How many attempts | ✅ |
| 7 | The username | ✅ |
| 8 | The password | ✅ |
| 9 | Packet details line | ✅ |
| 10 | The fix | ✅ |

**Skills:** HTTP POST inspection, credential exposure, packet details pane.
**Fix:** serve login pages over HTTPS/TLS.

---

## 🔐 Lab 7: Catch the Brute Force Attacker

Spot the repeated login attempts and find who is guessing passwords.

| # | Task | Status |
|---|------|--------|
| 1 | Capture the traffic | ✅ |
| 2 | The protocol | ✅ |
| 3 | The target | ✅ |
| 4 | The attacker | ✅ |
| 5 | The username | ✅ |
| 6 | Failure code | ✅ |
| 7 | Failed logins | ✅ |
| 8 | Success code | ✅ |
| 9 | The password that worked | ✅ |
| 10 | The attack type | ✅ |

**Skills:** login pattern analysis, response code comparison, brute-force detection.
**Fix:** rate limiting, account lockout, strong passwords, MFA.

---

## 📞 Lab 8: Catch the Call Scammer

Investigate the capture, play the call and identify the scammer.

| # | Task | Status |
|---|------|--------|
| 1 | Capture the traffic | ✅ |
| 2 | Call setup protocol | ✅ |
| 3 | Voice protocol | ✅ |
| 4 | Caller extension | ✅ |
| 5 | Caller name | ✅ |
| 6 | The codec | ✅ |
| 7 | Who answered | ✅ |
| 8 | Card number | ✅ |
| 9 | Expiry date | ✅ |
| 10 | The fix | ✅ |

**Skills:** SIP signalling, RTP streams, VoIP call playback, codec identification.
**Fix:** never share card details on unsolicited calls; use encrypted voice (SRTP/TLS).

---

## 🛠️ Wireshark Skills Practised

- Live capture and opening `.pcap` / `.pcapng` files
- Display filters
- Follow TCP Stream
- Packet details and hex/ASCII inspection
- Conversation and stream analysis
- Telephony and VoIP call playback
- TLS handshake details (Server Name, version)

### Example Display Filters

```text
dns.qry.name == "networkwalks.com"
tcp.flags.syn == 1 && tcp.flags.ack == 0
tcp.flags.reset == 1
http.request.method == "POST"
tcp.stream eq 0
sip
rtp
```

### DNS Analysis (Labs 1 and 2)

Examined transaction ID, flags, question/answer counts, record type and class for both the live capture and the saved PCAP.

-------|--------|------------|--------|
| `networkwalks.com` (A) | 192.168.1.6 | 1.1.1.1 | 192.232.216.135 |
| `microsoft.com` (A) | 192.168.0.105 | 8.8.8.8 | Multiple A records returned |

Examined transaction ID, flags, question/answer counts, record type and class.

---

## 🧠 Key Takeaways

- Many SYN packets with no completed handshakes point to a port scan.
- Unencrypted protocols (HTTP, plain chat, SIP/RTP) expose credentials and sensitive data.
- Many failed logins from one source followed by a success suggests brute force.
- Follow TCP Stream turns raw packets into readable evidence.
- Defend with encryption (HTTPS, TLS, SRTP), strong passwords, rate limiting and lockout.

---

## 📊 Assessment

- Labs 1 and 2 (foundation): completed
- 6 SOC labs: **100% in all** (60/60 tasks)
- Wireshark Quiz: **80%** (8 correct, 2 wrong)

---

## ⚠️ Ethical Use

All work was done inside the provided lab environments. Never capture or test traffic on a network you do not own or have written permission to test.

## 🙏 Acknowledgements

Thanks to [Networkwalks](https://www.networkwalks.com) for the internship and lab environment.

## 👤 Author

**Gowri Balamurugan**
Cybersecurity intern

