# 🔐 Task 4: Setup and Use a Firewall on Windows/Linux

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

### ✅ 3. Blocked Inbound Traffic on Port 23 (Telnet)

```bash
sudo ufw deny 23
```

### ✅ 4. Allowed SSH (port 22)

```bash
sudo ufw allow 22
```

### ✅ 5. Tested the Block Rule

```bash
telnet localhost 23
nmap -p 23 localhost
```

### ✅ 6. Removed the test rule

```bash
sudo ufw delete deny 23
```
# In Windows

 ## ⚙️ Steps Performed

### ✅ 1. Opened Firewall Configuration

- Opened `Windows Defender Firewall with Advanced Security` from Start Menu.

### ✅ 2. Listed Current Inbound Rules

- Navigated to **Inbound Rules** in the left pane to view existing rules.

### ✅ 3. Blocked Inbound Traffic on Port 23 (Telnet)

- Clicked on **New Rule > Port > TCP > Specific local ports: 23**
- Selected **Block the connection**
- Applied to all profiles (Domain, Private, Public)
- Named the rule: `Block_Telnet_Port_23`

### ✅ 4. Tested the Block Rule

- Used `telnet localhost 23` to test connectivity.
- Also verified using `nmap` from another machine:

  ```bash
  nmap -p 23 <Windows-IP>
  ```
### ✅ 5. Allowed SSH (Optional - Port 22)

- Created a rule to allow SSH if needed:
  - New Rule > Port > TCP > Port 22 > Allow the connection.

### ✅ 6. Removed the Test Block Rule

- Went back to **Inbound Rules**.
- Right-click on `Block_Telnet_Port_23` and selected **Delete**.



## 📸 Screenshots

All screenshots of the above steps are available in the `/screenshots` folder, including:

### In Linux:

- Firewall status before/after
    
- Port 23 block confirmation
    
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
