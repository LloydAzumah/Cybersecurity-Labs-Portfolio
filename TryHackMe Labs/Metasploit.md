# TryHackMe Lab: Metasploit

## METASPLOIT
Metasploit is an **exploitation framework** that supports all phases of penetration testing, from information gathering to post-exploitation and more.

---

## Main Components of the Metasploit Framework
- **msfconsole**: The main command-line interface for interacting with Metasploit  
- **Modules**: Supporting modules like exploits, scanners, payloads, etc.  
- **Tools**: Standalone tools such as `msfvenom`, `pattern_create`, and `pattern_offset` that assist in vulnerability research, assessment, and exploitation development  

---

## MSFCONSOLE Commands

- `history` → View previously typed commands  
- `use` → Select a module by index or name  
- `search` → Search for modules or tools in Metasploit  
- `show` → List any module that is specified  
- `show options` → Display configurable fields for a selected module, e.g., `RHOST`, `RPORT`, `SMBPass`  
- `back` → Exit from the context of a module  
- `set` → Insert data for a field within the context of a module  
- `unset` → Remove data for a field within the context of a module  
- `unset all` → Erase the entire data set for the current module context  
- `setg` → Set a value globally, applied across all modules  
- `unsetg` → Remove a global value  
- `exploit` → Launch the selected module  
  - **Note:** `run` is an alias for `exploit` but is not recommended for scanner modules  
- `exploit -z` → Backgrounds the session immediately after creation  
- `background` → Suspend a session or put it on standby  
- `sessions` → List all active sessions with their IDs  
- `sessions -i <ID>` → Interact with a specific session  
  - Example: `sessions -i 1`

