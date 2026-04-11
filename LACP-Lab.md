Technical Report: LACP EtherChannel Implementation

📌 Project Overview

The objective of this lab was to implement Link Aggregation (EtherChannel) between two Cisco Catalyst 2960 switches. By bundling multiple physical interfaces into a single logical Port-Channel, I achieved increased bandwidth and link redundancy while preventing Layer 2 loops.

🏗️ Network Architecture

Protocol: LACP (Link Aggregation Control Protocol - 802.3ad)

Configuration: Multi-link trunking between Distribution and Access switches.

Redundancy: Automatic failover if a physical link in the bundle fails.

Topology Diagram

⚙️ Configuration & Implementation Logic

I utilized LACP (the vendor-neutral standard) and configured the Port-Channel as a Trunk to allow multiple VLANs to traverse the aggregated link.
