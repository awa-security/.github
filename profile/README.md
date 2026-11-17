# <img src="/profile/logo.svg" width="38" height="38" align="Top" alt="AWA Logo" /> AWA — Alert Without Alarm

**Outcome-aware verification of web-tier intrusion alerts, with independent ground truth.**

<p align="center">
  <img src="/profile/wave.svg" width="100%" alt="AWA Signal Verification Wave" />
</p>

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
