# Cisco Packet Tracer Spanning Tree Protocol Lab

A Cisco Packet Tracer switching lab demonstrating redundant Layer 2 links and Spanning Tree Protocol loop prevention.

## Project Overview

This project documents a three-switch topology with redundant inter-switch connections and endpoint PCs. The screenshot is labeled Spanning Tree Protocol and shows one link state in orange, consistent with a simulated redundant-path/blocking scenario.

## Features

- Three-switch redundant topology
- Spanning Tree Protocol loop-prevention concepts
- Observation of forwarding and alternate/blocking link states
- Simulation-mode evidence and endpoint connectivity checks

## Technologies Used

- Cisco Packet Tracer
- Cisco Catalyst 2960 switches
- Spanning Tree Protocol (STP)
- Ethernet switching

## Project Structure

```text
packet-tracer-spanning-tree-lab/
├── README.md
└── screenshots/
    └── spanning-tree-redundant-topology.jpg
```

## Network Topology Details

The screenshot shows three 2960-series switches connected in a triangle, providing redundant Layer 2 paths. A PC is connected to at least two of the switches. The orange link indicator suggests a non-forwarding state on a redundant path, though the exact STP role and state should be confirmed in the recreated lab.

## How to Recreate and Test

1. Add three Layer 2 switches and at least two PCs.
2. Connect the switches in a triangle to create redundant paths.
3. Connect each PC to an access port on a switch and assign addresses in the same subnet.
4. Allow STP to converge, or configure a deliberate root bridge using the supported STP commands.
5. Inspect port roles and states to identify forwarding and alternate/blocking ports.
6. Test host connectivity and observe how STP prevents a Layer 2 forwarding loop.
7. In Packet Tracer Simulation mode, inspect STP events if available.

## Useful Verification Commands

```text
enable
show spanning-tree
show spanning-tree vlan 1
show interfaces status
show mac address-table

# Optional root bridge selection (adjust VLAN and priority as appropriate)
configure terminal
spanning-tree vlan 1 root primary
end
show spanning-tree vlan 1
```

## Expected Results

STP should select a loop-free forwarding topology and place redundant paths into an alternate/blocking state as needed. Hosts on the same VLAN should communicate after convergence. The screenshot's simulation event list shows successful ICMP events, but the exact final STP state is not independently verified here.

## Screenshots

![Spanning Tree Redundant Topology](screenshots/spanning-tree-redundant-topology.jpg)

## Important Notes

The original `.pkt` file was not provided. This package contains the supplied screenshot and documentation only. STP behavior depends on bridge IDs, priorities, link costs, and the Packet Tracer switch model.

## Portfolio Use

This repository is intended as networking-lab documentation for a student internship portfolio. To present it as a completed practical implementation, recreate and verify the topology in Cisco Packet Tracer and add the resulting `.pkt` file and your own test evidence.
