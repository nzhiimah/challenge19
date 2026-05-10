# Challenge 19 : PC Info Enumeration

### Objective :
- To enumerate RPC services running on the target machine.

### Target Information :

| Item | Value |
|---|---|
| Target IP | 192.168.83.129 |
| Service | RPC |
| Port | 111 |

### Tools Used :
- Nmap
- rpcinfo

### Steps :
1.Identify Target IP Address

Command : (Run inside Metasploitable 2)
```
ip a
```
Result :
<img width="749" height="238" alt="Screenshot 2026-05-10 151320" src="https://github.com/user-attachments/assets/366ec743-e9c3-4c6a-b3e5-357c76d39656" />
<br>

---
2. Verify RPC Port

Command :
```
nmap -p 111 192.168.83.129
```
Result :
<img width="553" height="190" alt="Screenshot 2026-05-10 160329" src="https://github.com/user-attachments/assets/c8790e11-47e1-4948-8a9f-2e531490fc4b" />
<br>

---
3. Enumerate RPC Services

Command :
```
rpcinfo -p 192.168.83.129
```

Result Summary :
<img width="371" height="414" alt="Screenshot 2026-05-10 160357" src="https://github.com/user-attachments/assets/d5b3dcfe-0250-4b19-8998-18a6f35c6535" />
<br>

| Service | Description |
|---|---|
| portmapper | RPC port mapping service |
| mountd | NFS mount service |
| nfs | Network File System |
| status | RPC status service |

Findings :
- Multiple RPC services were identified on the target machine.
- NFS-related services were exposed through RPC.
---
### Conclusion :
- RPC enumeration successfully identified several active RPC services running on the target machine.
