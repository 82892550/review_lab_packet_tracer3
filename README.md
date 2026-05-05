# review_lab_packet_tracer3
# Console Access Configuration Lab (Packet Tracer)

## 📌 Overview

This lab focuses on configuring a Cisco router through a **console connection** using a PC. It covers setting secure access to the router and enabling password encryption.

---

## 🛠️ Lab Tasks

### 1. Connect PC to Router (Console)

* Connect:

  * **PC1 (RS-232)** → **R1 (Console Port)**
* Use the **Console cable (light blue cable)** in Packet Tracer

---

### 2. Access Router via Console & Set Hostname

* Open PC1 → Desktop → Terminal → OK

```bash id="m4z1dn"
Router> enable
Router# configure terminal
Router(config)# hostname R1
```

---

### 3. Set Enable Secret

```bash id="u1l2w7"
R1(config)# enable secret cisco
```

---

### 4. Configure Console Password

```bash id="gq4d8n"
R1(config)# line console 0
R1(config-line)# password ccna
R1(config-line)# login
R1(config-line)# exit
```

* Check running configuration:

```bash id="8z2jpf"
R1# show running-config
```

🔍 **Observation:**

* The console password appears in **plain text** (not encrypted yet)

---

### 5. Enable Password Encryption

```bash id="n5xw0c"
R1(config)# service password-encryption
```

* Verify:

```bash id="a9d3ke"
R1# show running-config
```

🔐 **Result:**

* Console password is now **encrypted**
* All visible passwords are no longer in plain text

---

### 6. Save Configuration

```bash id="k7r2pm"
R1# copy running-config startup-config
```

---

## 📚 Key Concepts Learned

* How to access a router using a **console cable**
* Configuring secure access via **console line**
* Difference between encrypted and plain-text passwords
* Using `service password-encryption` to secure credentials
* Saving configurations in Cisco IOS

---

## 🧠 Notes

* Without the `login` command, the console password will not be required
* `enable secret` is always encrypted by default
* `service password-encryption` encrypts all passwords but with weak encryption (Type 7)

---

## 📁 Tools Used

* Cisco Packet Tracer

---

## 🚀 Author

Created as part of CCNA practice labs
