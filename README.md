# Malicious Software (Malware)

**Malware**, or **Mal**icious soft**ware**, is the term used to describe a *program, software, application, or code* that has the intention to cause *harmful and malicious activities, without the owner's consent and intentionally,* to **(different systems)** computers, systems, networks, or servers.

## Malware Capabilities (MC 9 Behaviors to lookout)
These are specific capabilities of malware they perform as *malicious activities and behavior without the owner's consent.* Unexpected and unusual behaviors are observable that _hint_ the different systems are already infected or ongoing infection. These are the common malicious activities of malware:
1. **Propagation**        - to **spread itself** (malware) to other computers, systems, networks, and/or servers, through a medium: internet, email, peer-to-peer, network, physical media, cloud media, etc.
2. **Destruction**        - to **destroy, delete, or damage critical and important data** within the different systems, and to stop, halt, and/or terminate all systems operations.
3. **Deception**          - to **deceive users** into engaging (downloading, executing, or other activities) with the malware or its malicious components.
4. **Remote Connection**  - to **connect** to the different systems and gain control over them.
5. **Data Theft**         - to **steal sensitive, private, and critical data** from different systems.
6. **Exploitation**       - to **abuse the vulnerabilities of the system** to bypass their security to gain access, control, spread malware, destroy and steal data, as well as deceive the owners.
7. **Anti-Detection**     - to **prevent detection and removal** by stealth mechanisms
8. **Digital Extortion**  - to **obtain money (digitally)** while scaring and fueling fear in the owners.
9. **Adverse Activities** - to **perform different kinds of system operations** that are adverse to the owner and with their consent.

# Malware Types
There is a large variety of malware, and they are categorized into different types. The general malware types are **Virus**es, **Worm**s, and **Trojan**s. The not-so-general malware types are exploits, rootkits, backdoors, ransomware, and botnets. Malware is different from Grayware, the former is illegal, and the latter is legal, which is why it is not included in the malware types.

## General Malware Types
| General Malware Types | Relationships to Other Malware Type | Level of Generalization of Malware Types | 
| ---          | ---                                 | ---                                      |
| Virus        | 1. Worm: Instant Messaging (IM), Peer-to-Peer (P2P), Internet Relay Chat (IRC); 2. Trojan: Backdoor, Command and Control Server (C2 server, CnC Server); | Level 1: Most General |
| Worm         | 1. Virus: Instant Messaging (IM), Peer-to-Peer (P2P), Internet Relay Chat (IRC); | Level 2: General |
| Trojan       | 1. Virus: Backdoor, Command and Control Server (C2 server, CnC Server); | Level 3: Least General |

### Malware Types: Definitions
| Malware Type | Textbook Definition | File Analysis Definition |
| ---          | ---        | ---           |
| Virus        | **Infects computers and other files** by _inserting a part of its code into another file_. It can't execute independently and needs a host file to attach itself to before "actual" infection. | _[MC-129]_ **APIs (application programming interfaces)** called are usually, **ReadFile**, **WriteFile**, **CreateFile**, **CopyFile**, **DeleteFile**, and **MoveFile**. The malicious code or the part of the code that traverses and infects other files is prepended (first bytes), appended (last bytes),  and cavity (in between bytes or in the padding). Then it only infects specific types of files to lessen the chance of getting caught, making less noticeable, and faster infections. |
| Worm         | **Sends copy(ies) of itself** to different systems through different mediums: _E-mail, Network Drives, Removable Drives, Instant Messaging (IM), Peer-to-Peer Networks (P2P), Social Networking, and other (remote) connections._ | _[MC-1269]_ **APIs (application programming interfaces)** called are usually, **CreateFile**, **CopyFile**, **DeleteFile**, and **MoveFile**. Unlike the virus, the worm does not need any "host" file to infect and propagate, it is a self-contained program that searches for folders, directories, network shares, network drives, media drives, e-mails, and other connections to let it propagate even deeper onto to different systems | 
| Trojan       | It **will not propagate** unlike other malware and its **infection uses outside methods or third (3rd) party applications** to get dropped onto different systems. A software or application downloaded from a sketchy website looks like legitimate software but in actuality, it is a trojan horse that brought the trojan malware onto the owners' system. Hence the name, Trojan and Trojan Horse. | _[MC-234679]_ **APIs (application programming interfaces)** called are usually related to, **Process** and **Services**. Other activities of this malware entail: downloading or dropping another malware, hiding other malware (backdoors and rootkits), and allowing a remote bad actor/hacker to take control, disrupt system operations, and destroy the whole system. | 

## Other Malware Types
The general malware types virus, worm, and trojan have different sub-types for almost all of them. Some of the sub-types are so popular, it had their own classification when classifying malware in general.

| Malware Type | Sub-Types | Remarks and/or Definition |
| ---          | ---       | ---                       |
| Virus        | _None_    | Every malware can be generalized more or less as a virus -- due to the **popularity of the word virus** instead of malware (the umbrella term for every type including the virus) |
| Worm         | IM-Worm, P2P-Worm, IRC-Worm, Email-Worm, Net-Worm, SocMed-Worm, USB-Worm, and others | **Propagating so much** between different systems? Most likely a worm. |
| Trojan       | Troj-Backdoor, Troj-Downloader, Troj-Dropper, Troj-Password, Troj-Spy, Troj-DDoS, Troj-IM, Troj-Banker, Troj-KeyLog, Troj-Proxy, Troj-C2, Troj-RootKit and, Troj-Ransom (separation -- Ransomware) | If it is not propagating, it is most likely a trojan and **is hiding something** |
| Exploit      | _None_ | It uses a vulnerability of different systems and **"exploits" or abuses the vulnerability** to perform different kinds of system operations such as remote code execution (RCE), privilege escalation, unauthorized access, and other operations. The exploits code is usually named shellcode. |
| Rootkit      | User-Level Rootkits, Kernel-Level Rootkits, and All the trojan sub-types | Similar to trojans, rootkits do destruction, remote connection, keylogging, stealing data, hiding from the security of the different systems, and others. The key difference between a trojan and a rootkit is, the rootkit should be **administrator-level access**, and is hiding within the _depths of the different systems' core (or root)_.|
| Ransomware   | Lockscreen, Crypto, and CryptoLocker | _Limits and prevents_ the owner of the different systems from accessing them, _stealing_ their data, _locking_ the screen, _encrypting_ the data, and _forcing_ the victim (owner) to **pay the ransom fee** with certain payment methods (usually bitcoins) that are all written in the **ransom note**. |
| Fileless     | _None_ | Usual fileless malware comes from different kinds of exploitations of vulnerabilities and then gaining access to a specific program running in the system. Fileless is **found in the memory**, injected into a program that is either running the fileless as a DLL (Dynamic Link Library) or as a PE (Portable Executable). It is harder to detect, and remove, and leaves almost no traces and footprints for forensics to analyze (except memory forensics). |

# References
+ [Types of Malware, Textbook definition](https://www.mecs-press.net/ijeme/ijeme-v8-n2/IJEME-V8-N2-3.pdf)
+ [Malware Type Relationships](https://usa.kaspersky.com/content/en-us/images/repository/isc/malware-tree.jpg)
+ [Fileless](https://www.trellix.com/en-us/security-awareness/ransomware/what-is-fileless-malware.html)

For more, read [MALWARE.MD](https://github.com/P1kasaur/malicious_software/blob/main/malware.md)
