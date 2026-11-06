# Challenge 002 — Network Traffic Analysis

## Executive summary

This report documents a short Wi-Fi packet capture reviewed with Wireshark as a learning exercise. The supplied results describe DNS, TLS, TCP, addressing, endpoints, conversations, and TCP reset review. They do not confirm an attack. The observations are limited to the available short capture and provide no assurance that the device or network is secure.

## Scope and evidence basis

- Capture: 145 packets from a Wi-Fi interface.
- Analysis performed: review of DNS requests and responses; identification of TLS handshake and application-data packets; examination of TCP connection attempts and reset packets; distinction between private and public IP addressing; inspection of endpoint and TCP conversation statistics.
- Evidence source: the user's supplied Wireshark results and associated learning-session notes. No raw capture, packet exports, or external enrichment was used.
- Reporting boundary: only findings represented in those supplied results are stated.

The supplied notes do not contain packet frame numbers, capture timestamps, DNS names or returned addresses, per-protocol packet counts, endpoint totals, conversation tuples, byte totals, or connection outcomes. Those details are not inferred or reconstructed here.

## Observations

### DNS

DNS requests and responses were reviewed. DNS can link a queried name with returned address information when both relevant query and response packets are present. The supplied results do not identify specific names or address records, so none are reproduced here.

### TLS

TLS handshake packets and encrypted application-data packets were identified. The supplied results support protocol-stage identification only; they do not establish the contents of encrypted application data.

### TCP

TCP connection attempts and reset packets were examined. The available notes do not specify which attempts succeeded, why any reset occurred, or whether behavior was abnormal. A reset by itself is not evidence of an attack.

### Addressing and traffic statistics

The exercise distinguished private from public IP addresses and reviewed Wireshark Endpoints and Conversations. Endpoints summarize statistics for individual network endpoints. Conversations summarize traffic exchanged between pairs of endpoints. The supplied notes do not include the actual address values or statistics; sensitive identifiers are omitted.

## Assessment

No attack was confirmed in the reviewed material. The results describe protocol and traffic-analysis practice, not a verified security incident. This finding is limited to the packets captured and the observations supplied; it does not establish that no malicious activity occurred outside the capture or that the device or network is secure.

## Limitations

- The capture was short and contained 145 packets, so it represents only a narrow time window and may omit other relevant activity.
- The supplied evidence does not include detailed packet-level values or quantitative endpoint and conversation outputs.
- TLS application data was encrypted and its contents were not interpreted.
- No baseline, broader host telemetry, corroborating logs, or incident context was supplied.
- No confirmed attack was found, but absence of confirmation in this limited capture is not proof of absence.
- This exercise is not a full network audit, penetration test, or security assessment and provides no security assurance.

## Lessons learned

- Use Conversations to understand traffic exchanged between endpoint pairs; use Endpoints to summarize activity for individual addresses.
- DNS evidence can correlate names and addresses only when the relevant DNS packets are captured.
- TLS packet visibility can reveal handshake and encrypted-data stages without revealing protected application content.
- Keep conclusions proportional to capture duration and evidence detail.
- A short capture that does not confirm an attack cannot establish that a network is secure.

## Privacy handling

This report intentionally excludes host and address identifiers, domain names, MAC addresses, and raw packet or capture data.
