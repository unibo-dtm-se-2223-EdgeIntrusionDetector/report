---
title: "01. Concept"
has_children: false
nav_order: 2
---

# 1. Concept

This section outlines the high-level scope and foundational principles of the **Edge Intrusion Detector** project.

## 1.1 Project Rationales
Modern Industrial IoT (IIoT) applications are heavily exposed to distributed cyber threats. Traditional defense mechanics route raw network telemetry to centralized cloud servers for heavy analytical processing. This paradigm induces severe bandwidth costs, transmission latencies, and serious vulnerabilities in data privacy. The goal of this project is to shift the threat classification layer from central cloud nodes directly to the resource-constrained network Edge.

## 1.2 System Topology
The platform implements an asymmetric **Hub-and-Spoke** architecture split into two operational components:
*   **Central Base Station (Python Workspace):** An enterprise-level intelligence station that coordinates dataset ingestion, ML modeling, decision tree optimization, and remote administrative telemetry monitoring.
*   **Edge Node (C Firmware Target):** A lightweight, low-level embedded software micro-layer running natively on a microcontroller. It runs the specialized **MicroShield** classification middleware to intercept and discard malicious frames.

---

## 1.3 Theoretical Background & Dataset Scoping
The operational behavior and data dimensions of the intrusion engine are mathematically framed using the benchmark parameters established by the academic reference frameworks **Edge-IIoTset** and **IoT-23**.

### 1.3.1 Feature Extraction Matrix
To enforce robust behavioral fingerprinting without relying on volatile and easily spoofed network identities (such as static IP or MAC addresses), the detection schema targets statistical packet characteristics aggregated over discrete time windows:

| Feature Token | Data Type | Operational Profile Description |
| :--- | :--- | :--- |
| `packet_rate` | `float32` | Instantaneous frame ingestion frequency within the active time window. |
| `payload_size_avg` | `float32` | Statistical average of the data frame length byte allocations. |
| `payload_size_var` | `float32` | Running variance of packet payloads to flag anomalous flooding structures. |

---

## 1.4 Conceptual Operational Workflow
The structural interactions spanning offline optimization, automated transcompilation, and real-time validation follow a synchronous progression detailed in the roadmap below.

![General System Flow Diagram](../../pictures/01-general-flow.png)
