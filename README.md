# Task 4: Setup and Use a Firewall on Windows/Linux

## 🎯 Objective

Configure and test basic firewall rules to **allow** or **block** network traffic using UFW (Linux) or Windows Firewall.

---

## 🛠️ Environment Used

- **OS:** Parrot OS (Linux), Windows 7 (VM), Windows 11.
- **Tool:** UFW (Uncomplicated Firewall),  Windows Defender Firewall with Advanced Security.


---

# In Linux

## ⚙️ Steps Performed

### ✅ 1. Enabled UFW

```bash
sudo ufw enable
```

### ✅ 2. Listed existing rules

```bash
sudo ufw status
sudo ufw status numbered
```

### ✅ 3. Blocked Inbound Traffic on Port 22 (SSH)

```bash
sudo ufw deny 22
```

### ✅ 4. Tested the Block Rule

```bash
nmap -p 22 localhost
```

### ✅ 5. Removed the test rule

```bash
sudo ufw delete deny 23
```

### ✅ 6. Allowed SSH (port 22)

```bash
sudo ufw allow 22
```

# In Windows

 ## ⚙️ Steps Performed

### ✅ 1. Opened Firewall Configuration

- Opened `Windows Defender Firewall with Advanced Security` from Start Menu.

### ✅ 2. Listed Current Inbound Rules

- Navigated to **Inbound Rules** in the left pane to view existing rules.

### ✅ 3. Blocked Inbound Traffic on Port 22 (SSH)

- Clicked on **New Rule > Port > TCP > Specific local ports: 23**
- Selected **Block the connection**
- Applied to all profiles (Domain, Private, Public)
- Named the rule: `Block_SSH_Port_22`

### ✅ 4. Tested the Block Rule

- Used `ssh your_username@192.168.1.72 ` to test connectivity.
- Also verified using `nmap` from another machine:

  ```bash
  nmap -p 22 <Windows-IP>
  ```
  
### ✅ 5. Removed the Test Block Rule

- Went back to **Inbound Rules**.
- Right-click on `Block_SSH_Port_22` and selected **Delete**.



## 📸 Screenshots

All screenshots of the above steps are available in the `/screenshots` folder, including:

### In Linux:

- Firewall status before/after
    
- Port 22 block confirmation
    
- UFW commands execution

### In Windows:

- Windows Firewall UI

- Rule creation wizard

- Testing block using Telnet/Nmap

- Rule removal



## 🧠 Key Learnings

- Learned how to **list**, **add**, and **remove** firewall rules using UFW.
    
- Understood the concept of **inbound/outbound** traffic control.
    
- Practiced basic **network traffic filtering** using port numbers.
    
- Realized the importance of **allowing SSH (port 22)** while working on Linux firewalls to avoid losing remote access.
 
- Understood how to use Windows Firewall to manage traffic.
  
- Understood the need to test rules and remove them after testing.

- Practiced how to block and allow specific ports.

- Learned the importance of inbound vs outbound filtering.
