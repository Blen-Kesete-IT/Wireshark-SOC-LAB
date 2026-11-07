# Wireshark SOC Lab

A portfolio of six completed Network Walks Wireshark SOC exercises. The labs cover port-scan analysis, TCP stream reconstruction, credential exposure, brute-force detection, and VoIP call replay. Each result screenshot shows a score of **100/100**.

## Lab results

| Lab | What I investigated | Evidence |
|---|---|---|
| 3 · Identify the Attacker’s IP | Filtered for TCP SYN packets, identified the scanning host and target, and used replies to distinguish open and closed ports. | [Lab 3 result](screenshots/lab-03.png) |
| 4 · Follow TCP Stream | Reconstructed a chat session, identified who initiated it, and located a temporary password and a guest Wi-Fi password in the conversation. | [Lab 4 result](screenshots/lab-04.png) |
| 5 · Follow TCP Stream, part 2 | Traced web traffic to the relevant TCP stream, identified the backup server and HTTP status code, and located a downloaded file. | [Lab 5 result](screenshots/lab-05.png) |
| 6 · HTTP plain text credentials | Traced login traffic to the originating PC and login page, identified the request method, counted attempts, and located the username and password in packet details. | [Lab 6 result](screenshots/lab-06.png) |
| 7 · Brute force catch | Identified the attacker, target, and account under attack. Compared failure and success response codes to locate the successful login. | [Lab 7 result](screenshots/lab-07.png) |
| 8 · VoIP call replay | Identified call setup and voice protocols, the caller and answering party, and the audio codec. Replayed the lab call to identify exposed payment details. | [Lab 8 result](screenshots/lab-08.jpeg) |

## Authentication from the network perspective

In Lab 6, the client PC sent a login request to the server over plain HTTP. Wireshark packet details revealed the submitted username and password. In Lab 7, repeated login requests produced failure responses before a successful response. Comparing the requests and replies showed which attempt succeeded. Lab 4 demonstrated a separate exposure path when someone shared passwords in a chat stream.

The screenshots are completion scorecards. Packet captures would establish the exact endpoints, methods, status codes, and packet sequence. Server code or implementation docs would be needed to determine how the application verifies and stores passwords or how it issues, validates, and expires session cookies or tokens.

Training exercises by [Network Walks](https://www.networkwalks.com/).
