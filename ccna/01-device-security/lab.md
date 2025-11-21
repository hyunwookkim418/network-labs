# Lab 01 — Device Security Basics

## Objective
In this lab you will:
- Change the hostname of router and switch
- Configure an unencrypted enable password
- Test and verify the password
- Enable password encryption
- Configure a secure enable secret
- Save the configuration

---

## Topology
![Topology](./images/topology.png)

---

## Task 1 — Change the Hostname

**On R1**
```bash
enable
configure terminal
hostname R1
exit

## Task 2 — Configure an Unencrypted enable password
configure terminal
enable password CCNA
exit

Test it
exit
enable
Password: CCNA
