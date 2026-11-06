# Challenge 002 — Network Traffic Analysis

A short, evidence-based Wireshark learning exercise documenting network visibility and basic traffic analysis.

## Scope

The exercise examined a short capture of 145 packets from a Wi-Fi interface. It reviewed DNS requests and responses, TLS handshake and application-data packets, TCP connection attempts and reset packets, private and public addressing, and Wireshark endpoint and conversation statistics.

## Key observations

- DNS was reviewed for name-resolution activity.
- TLS handshake and encrypted application-data traffic were identified; encrypted application contents were not interpreted.
- TCP connection attempts and reset packets were examined.
- Endpoints summarize activity for individual addresses; conversations summarize traffic exchanged between endpoint pairs.
- No attack was confirmed in the available capture.

## Limitations

This was a short, 145-packet observation of ordinary traffic, not an incident investigation, full network audit, or penetration test. A short capture may omit activity outside its time window. No confirmed attack was identified, and these results provide no security assurance. Sensitive identifiers and raw capture data are intentionally excluded.

## Detailed report

See [network traffic analysis report](network-traffic-analysis.md).
