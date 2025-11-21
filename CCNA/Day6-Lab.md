# Lab 06 — Analyzing Ethernet Switching

## Objective
In this lab you will:
- View the switch MAC address table
- Generate traffic to populate dynamic MAC entries
- Clear dynamic MAC entries
- Observe MAC relearning behavior
- Verify forwarding decisions based on MAC learning

---
## Task 2 — Generate Traffic to Populate the MAC Table
From PC1 or PC2:
```bash
ping <other_host_ip>
```
Re-check:
```bash
show mac address-table
```
Expected:
- New dynamic MAC entries appear under the correct ports.
- Entries appear only after traffic is seen.
---

## Task 1 — View the MAC Address Table
On SW1
```bash
enable
show mac address-table
```
Expected output example:
| Vlan | Mac Address    | Type    | Ports |
|------|----------------|---------|-------|
|    1 | aaaa.bbbb.cccc | DYNAMIC | Fa0/1 |
---

## Task 3 — Clear Dynamic MAC Address Entries
```bash
clear mac address-table dynamic
```
Verify:
```bash
show mac address-table
```
Expected:
- All dynamic entries removed.
- Static entries remain.
---

## Task 4 — Observe Relearning Behavior
After clearing the MAC table:
1. Ping again between hosts
2. Check the table:
```bash
show mac address-table
```
Expected:
- Switch immediately relearns MACs from incoming frames.
- New entries reappear under appropriate ports.
---

## Credits

These labs were inspired by the instructional style and lab structure shown in the **Day 6: Analyzing Ethernet Switching** lesson from **Jeremy’s IT Lab CCNA course**. Jeremy’s clear explanations and practical demonstrations played a significant role in shaping the format and learning approach used in this repository.

You can find Jeremy’s IT Lab here:  
https://www.youtube.com/c/JeremysITLab
