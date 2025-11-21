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
# Task 1 — Change the Hostname

## On R1
```bash
enable
configure terminal
hostname R1
exit
```
---
# Task 2 — Configure an Unencrypted enable password
```bash
configure terminal
enable password CCNA
exit
```
### Test it
```bash
exit
enable
Password: CCNA
```
---
## Task 3 — View Password in Running Configuration

```bash
show running-config
```

You should see:

```
enable password CCNA
```

This is **plaintext (insecure)**.
---
## Task 4 — Encrypt All Plaintext Passwords

```bash
configure terminal
service password-encryption
exit
```

### Verify encryption
```bash
show running-config
```

Expected:

```
enable password 7 <encrypted_string>
```
---
## Task 5 — Configure a Secure `enable secret`

```bash
configure terminal
enable secret Cisco
exit
```

### Verify
```bash
show running-config
```

### Expected Results

| Password Type     | Command         | Encrypted Type | Strength        |
|------------------|-----------------|----------------|-----------------|
| enable password  | Type 7          | Weak           | ❌ Not secure   |
| enable secret    | Type 5          | Strong hash    | ✔ Recommended   |
---
## Task 6 — Save the Configuration

Any of the following:

```bash
write memory
```

or

```bash
copy running-config startup-config
```
---
