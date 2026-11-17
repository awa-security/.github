# <img src="data:image/svg+xml;utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect width='100' height='100' rx='22' fill='%2314181D'/%3E%3Cpath d='M 16 82 L 48 16' fill='none' stroke='%23E7E9EC' stroke-width='9' stroke-linecap='round'/%3E%3Cpath d='M 52 16 L 84 82' fill='none' stroke='%23E7E9EC' stroke-width='9' stroke-linecap='round'/%3E%3Cpath d='M 30.5 58 L 35 50 L 39.5 65 L 44 47 L 48.5 58' fill='none' stroke='%23C97B4A' stroke-width='4.6' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M 48.5 58 C 55 58 58 58 63 58' fill='none' stroke='%237CB8AE' stroke-width='4.6' stroke-linecap='round'/%3E%3Ccircle cx='67.5' cy='58' r='5.6' fill='%237CB8AE'/%3E%3C/svg%3E" width="38" height="38" align="center" alt="AWA Logo" /> AWA — Alert Without Alarm

**Outcome-aware verification of web-tier intrusion alerts, with independent ground truth.**

<img src="data:image/svg+xml;utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1000 120' width='100%25'%3E%3Cdefs%3E%3CradialGradient id='centerGlow' cx='50%25' cy='50%25' r='50%25'%3E%3Cstop offset='0%25' stop-color='%237CB8AE' stop-opacity='0.35'/%3E%3Cstop offset='50%25' stop-color='%237CB8AE' stop-opacity='0.1'/%3E%3Cstop offset='100%25' stop-color='%237CB8AE' stop-opacity='0'/%3E%3C/radialGradient%3E%3CradialGradient id='pulseGlow' cx='50%25' cy='50%25' r='50%25'%3E%3Cstop offset='0%25' stop-color='%237CB8AE' stop-opacity='0.95'/%3E%3Cstop offset='100%25' stop-color='%237CB8AE' stop-opacity='0'/%3E%3C/radialGradient%3E%3C/defs%3E%3Crect width='1000' height='120' rx='10' fill='%230B0E12'/%3E%3Cline x1='0' y1='60' x2='1000' y2='60' stroke='%23202833' stroke-width='1'/%3E%3Cpath fill='none' stroke='%23C97B4A' stroke-opacity='0.62' stroke-width='1.8' stroke-linecap='round'%3E%3Canimate attributeName='d' dur='4s' repeatCount='indefinite' values='M0,60 Q40,5 80,60 T160,60 T240,60 Q280,25 320,60 T400,60 Q450,55 500,60; M0,60 Q40,115 80,60 T160,60 T240,60 Q280,95 320,60 T400,60 Q450,65 500,60; M0,60 Q40,5 80,60 T160,60 T240,60 Q280,25 320,60 T400,60 Q450,55 500,60'/%3E%3C/path%3E%3Cpath fill='none' stroke='%23C97B4A' stroke-opacity='0.36' stroke-width='1.3' stroke-linecap='round'%3E%3Canimate attributeName='d' dur='3.2s' repeatCount='indefinite' values='M0,60 Q30,100 60,60 T120,60 T200,60 Q260,90 320,60 T420,60 Q460,64 500,60; M0,60 Q30,20 60,60 T120,60 T200,60 Q260,30 320,60 T420,60 Q460,56 500,60; M0,60 Q30,100 60,60 T120,60 T200,60 Q260,90 320,60 T420,60 Q460,64 500,60'/%3E%3C/path%3E%3Cpath fill='none' stroke='%23C97B4A' stroke-opacity='0.22' stroke-width='1' stroke-linecap='round'%3E%3Canimate attributeName='d' dur='2.6s' repeatCount='indefinite' values='M0,60 Q50,30 100,60 T200,60 T300,60 T400,60 L500,60; M0,60 Q50,90 100,60 T200,60 T300,60 T400,60 L500,60; M0,60 Q50,30 100,60 T200,60 T300,60 T400,60 L500,60'/%3E%3C/path%3E%3Ccircle cx='90' cy='28' r='2' fill='%23C97B4A' opacity='0.45'/%3E%3Ccircle cx='155' cy='92' r='2.5' fill='%23C97B4A' opacity='0.35'/%3E%3Ccircle cx='230' cy='24' r='1.8' fill='%23C97B4A' opacity='0.4'/%3E%3Ccircle cx='310' cy='85' r='2.2' fill='%23C97B4A' opacity='0.3'/%3E%3Ccircle cx='390' cy='46' r='2.5' fill='%237CB8AE' opacity='0.35'/%3E%3Ccircle cx='500' cy='60' r='50' fill='url(%23centerGlow)'/%3E%3Ccircle cx='500' cy='60' r='3.8' fill='%237CB8AE'/%3E%3Cline x1='500' y1='60' x2='1000' y2='60' stroke='%237CB8AE' stroke-opacity='0.75' stroke-width='2'/%3E%3Ccircle cy='60' r='15' fill='url(%23pulseGlow)'%3E%3Canimate attributeName='cx' from='500' to='1000' dur='2.8s' repeatCount='indefinite'/%3E%3C/circle%3E%3C/svg%3E" width="100%" alt="AWA Signal Verification Wave" />

Traditional signature engines (Suricata/Snort) inspect the incoming request in isolation, firing alerts whether the server rejected the probe or suffered a breach. **AWA** pairs each alerted request with the server's actual response to deliver a calibrated, outcome-aware verdict.

### Core Verdict Taxonomy

| Verdict | Meaning | Default Action |
| :--- | :--- | :--- |
| **Benign trigger** | Signature fired on harmless traffic | Suppress from analyst queue |
| **Failed attempt** | Real attack that did not succeed | Log with low priority |
| **Likely succeeded** | Verifiable evidence the attack worked | Escalate and optionally contain |
| **Inconclusive** | Insufficient evidence in telemetry | Route to human analyst |

### Key Deliverables

- **AWA-Bench:** An open benchmark of real HTTP attacks (succeeded and failed) and tricky-benign traffic labelled by an independent server-side oracle.
- **AWA Engine:** An outcome-aware verification service integrating Suricata `eve.json` and reverse-proxy telemetry with automated enforcement adapters.
- **Research Benchmark:** Leakage-free evaluation comparing request-only versus request-and-response architectures.

### Institutional & Project Info

- **Institution:** Faculty of Artificial Intelligence, Menoufia University, Egypt
- **Website:** [awasystem.net](https://awasystem.net)
- **Planned Licenses:** Code under Apache-2.0 · Dataset under CC BY 4.0
