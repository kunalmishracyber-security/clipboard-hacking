# Clipboard Hijacker Payload (Pentesting Research Tool)

## Objective

The **Clipboard Hijacker Payload** is a post-exploitation research tool designed for authorized penetration testing and security assessments.

Its purpose is to demonstrate how attackers may abuse clipboard functionality to monitor copied data and understand the security risks associated with sensitive information being stored temporarily in the system clipboard.

During normal usage, users may copy sensitive information such as:

* Passwords
* Cryptocurrency wallet addresses
* Payment details
* Authentication tokens
* Other confidential information

This project helps security professionals analyze clipboard-related threats and improve endpoint security defenses.

---

## How It Works

### 1. Clipboard Monitoring

The payload continuously monitors clipboard activity at a configured interval and captures available clipboard text data.

### 2. Data Transmission

Captured clipboard information is sent to a configured testing server using an HTTP POST request.

The transmitted data includes:

* **clipboard_data**
  Contains the captured clipboard text.

* **machine_name**
  Identifies the target system name.

* **user_name**
  Identifies the active user environment.

### 3. Local Logging (Optional)

The tool can maintain local logs of captured clipboard activity for testing and debugging purposes.

### 4. Error Handling

The script includes error handling mechanisms to record failures during clipboard access or communication with the testing server.

---

# Setup Instructions

## Install Required Dependencies

Install Flask on your testing server:

```bash
python3 -m pip install flask
```

---

## Start the Server

Run the Flask server:

```bash
python3 server.py
```

---

## Configure Payload

Update your testing server IP address inside:

```
clipboardcodes.ps1
```

---

## Execute Payload

Run the PowerShell script:

```powershell
powershell -NoP -NonI -W h -Exec Bypass .\clipboardcodes.ps1
```

After successful execution, the configured server will receive clipboard events according to the configured monitoring interval.

---

# Security Purpose

This project is created for:

✅ Authorized penetration testing
✅ Security research
✅ Awareness training
✅ Endpoint defense testing

Understanding clipboard abuse techniques helps security teams detect malicious behavior and build better protection mechanisms.

---

# Disclaimer

This project is intended **only for authorized security testing and educational purposes**.

Do not use this tool on systems, networks, or devices without explicit permission.
The author is not responsible for any misuse or illegal activity performed using this project.
