# PHASE 01 — Fondations & Home Lab
## Semaines 1 à 5 | 22 juin 2026 – 26 juillet 2026

> **Objectif :** Comprendre comment les ordinateurs parlent entre eux, et documenter ton environnement de travail comme un professionnel.  
> **Motto :** "Pas de SIEM sans réseau. Pas d'analyse sans logs. Pas de portfolio sans preuves."

---

## Vue d'ensemble des 5 semaines

| Semaine | Thème | Livrable | Deadline |
|---------|-------|----------|----------|
| 1 | Réseau & Wireshark | `W1_Network_Fundamentals.md` + 3 screenshots | 28 juin |
| 2 | Home Lab Setup | `W2_Lab_Setup.md` + schéma réseau | 5 juillet |
| 3 | Windows Logs & Sysmon | `W3_Windows_Logs.md` + 1 screenshot Event Viewer | 12 juillet |
| 4 | Linux Logs & Parsing | `W4_Linux_Logs.md` + 1 screenshot auth.log | 19 juillet |
| 5 | Consolidation & Cheat Sheets | `Cheat_Sheet_Linux.md` + `Cheat_Sheet_Windows_Event_IDs.md` | 26 juillet |

---

## SEMAINE 1 — Réseau & Premier Contact
### 22 juin 2026 – 28 juin 2026

**Objectif :** Comprendre TCP/IP, capturer du trafic, et documenter ce que tu vois.

### Rituel quotidien (22h00 – 00h00)

| Horaire | Durée | Activité | Détails |
|---------|-------|----------|---------|
| 22h00 – 22h10 | 10 min | **Anki** | 10 cartes vocabulaire réseau |
| 22h10 – 22h55 | 45 min | **Lab / Pratique** | TryHackMe + Wireshark |
| 22h55 – 23h25 | 30 min | **Théorie** | Notes, lecture, compréhension |
| 23h25 – 23h50 | 25 min | **Documentation** | Écrire dans le fichier W1 |
| 23h50 – 00h00 | 10 min | **Planification** | Noter la tâche du lendemain |

### Jour 1 — Lundi 22 juin : Introduction & TCP/IP Basics

**Mission 1 :** Lire la section "Networking Fundamentals" sur TryHackMe "Pre-Security" (gratuit).  
**Mission 2 :** Créer un fichier `W1_Network_Fundamentals.md` dans ce dossier. Structure :
```markdown
# Week 1 — Network Fundamentals
## Date: 2026-06-22

### 1. What I learned today
- OSI Model: 7 layers (Physical → Application)
- TCP/IP Model: 4 layers (Network Interface → Application)
- Key difference: OSI is theoretical, TCP/IP is practical

### 2. Vocabulary (Anki cards)
- packet: a unit of data transmitted over a network
- protocol: rules for communication (TCP, UDP, HTTP)
- port: a number identifying a specific service (22=SSH, 80=HTTP)
- IP address: unique identifier of a device on a network
- subnet mask: defines the network portion of an IP
- gateway: device connecting local network to external network
- DNS: translates domain names to IP addresses
- handshake: process of establishing a connection (TCP 3-way)
- OSI model: 7-layer framework for network communication
- router: device forwarding traffic between networks

### 3. Screenshot of the day
[placeholder: screenshot TryHackMe completion]

### 4. Questions I have
[écrire ici ce que tu n'as pas compris — je répondrai]
```

**Mission 3 :** Télécharger et installer **Wireshark** (gratuit, wireshark.org). Pas de capture encore, juste l'installation.

**Mission 4 :** Créer un compte **GitHub** si ce n'est pas fait. Nom pro : `yamga-soc` ou `yy-soc-analyst`.

---

### Jour 2 — Mardi 23 juin : Wireshark — Première Capture

**Mission 1 :** Ouvrir Wireshark. Sélectionner ton interface réseau (Wi-Fi ou Ethernet).  
**Mission 2 :** Capturer pendant 2 minutes pendant que tu fais :
- Ouvrir un navigateur, aller sur un site (ex: google.com)
- Ouvrir un terminal, faire `ping 8.8.8.8`
- Arrêter la capture

**Mission 3 :** Observer :
- Combien de paquets ? (regarder le compteur en bas)
- Trouver un paquet DNS (filter: `dns`)
- Trouver un paquet TCP (filter: `tcp`)
- Trouver un paquet ICMP (filter: `icmp`)

**Mission 4 :** Dans `W1_Network_Fundamentals.md`, ajouter la section :
```markdown
### Day 2 — First Wireshark Capture
- Total packets captured: [X]
- DNS query seen: [domain name] → [IP address]
- TCP packet: [source IP:port] → [destination IP:port]
- ICMP packet: [source] → [destination], type: [echo request/reply]
```

**Screenshot à prendre :** Le filtre DNS dans Wireshark montrant la requête pour google.com.

---

### Jour 3 — Mercredi 24 juin : TCP 3-Way Handshake

**Mission 1 :** Lire sur le "TCP 3-Way Handshake" (SYN → SYN-ACK → ACK).  
**Mission 2 :** Dans Wireshark, filtrer sur `tcp.port == 80` ou `tcp.port == 443`.  
**Mission 3 :** Trouver un handshake complet : repérer les flags `SYN`, `SYN-ACK`, `ACK`.  
**Mission 4 :** Documenter dans `W1_Network_Fundamentals.md` :
```markdown
### Day 3 — TCP 3-Way Handshake
- I found a TCP handshake to: [website/IP]
- Step 1: Client sends SYN (seq=[number])
- Step 2: Server sends SYN-ACK (seq=[number], ack=[number])
- Step 3: Client sends ACK (ack=[number])
- This proves: TCP is connection-oriented
```

**Screenshot à prendre :** Les 3 paquets SYN/SYN-ACK/ACK alignés dans Wireshark.

---

### Jour 4 — Jeudi 25 juin : Ports & Services

**Mission 1 :** Apprendre les 10 ports essentiels : 22(SSH), 23(Telnet), 25(SMTP), 53(DNS), 80(HTTP), 110(POP3), 143(IMAP), 443(HTTPS), 445(SMB), 3389(RDP).  
**Mission 2 :** Dans Wireshark, filtrer sur `tcp.port == 443` et observer le trafic HTTPS.  
**Mission 3 :** Ajouter à Anki les 10 ports + services.  
**Mission 4 :** Documenter dans `W1_Network_Fundamentals.md` :
```markdown
### Day 4 — Common Ports
- 22/SSH: secure remote access
- 80/HTTP: web traffic (unencrypted)
- 443/HTTPS: web traffic (encrypted)
- 3389/RDP: remote desktop (Windows)
- 445/SMB: file sharing (Windows)
- ... (list all 10)
```

---

### Jour 5 — Vendredi 26 juin : Nmap — Scan de Ports (introduction)

**Mission 1 :** Télécharger et installer **Nmap** (gratuit, nmap.org).  
**Mission 2 :** Commande : `nmap -sV 127.0.0.1` (scan localhost). Observer les résultats.  
**Mission 3 :** Commande : `nmap -p 22,80,443 8.8.8.8` (scan Google DNS sur 3 ports).  
**Mission 4 :** Documenter dans `W1_Network_Fundamentals.md` :
```markdown
### Day 5 — Nmap Introduction
- Command used: `nmap -sV 127.0.0.1`
- Result: [list open ports and services]
- What I learned: Nmap identifies services by version
- Warning: scanning external IPs without permission can be illegal. Always scan your own lab.
```

---

### Jour 6 — Samedi 27 juin : Synthèse & Vocabulaire

**Mission 1 :** Relire `W1_Network_Fundamentals.md`, compléter les sections manquantes.  
**Mission 2 :** Réviser les 40 cartes Anki créées cette semaine.  
**Mission 3 :** Ajouter une section finale :
```markdown
### Week 1 Summary
- Key concepts mastered: [list 5]
- Tools used: Wireshark, Nmap, TryHackMe
- Questions remaining: [list]
- Next week: Home Lab setup
```

---

### Jour 7 — Dimanche 28 juin : Buffer & Revue

**Mission 1 :** Refaire la capture Wireshark du jour 2 sans regarder les notes.  
**Mission 2 :** Refaire le scan Nmap sans regarder la commande.  
**Mission 3 :** Vérifier que le fichier `W1_Network_Fundamentals.md` est complet et propre.  
**Mission 4 :** **ME FAIRE REVOIR LE FICHIER** — revenir ici, coller le contenu, je corrige et valide.

---

## Templates de livrables (à utiliser chaque semaine)

### Template de document Markdown
```markdown
# [Title] — Week [X], Day [Y]
## Date: [YYYY-MM-DD]

### 1. What I learned today
[Bullet points, simple English]

### 2. Tools used
- [Tool name]: [purpose]

### 3. Screenshots & Evidence
![Description](screenshots/filename.png)

### 4. Key commands
```bash
[command]
```

### 5. Reflection
[What was hard? What do I need to repeat?]

### 6. Questions for review
[What I didn't understand]
```

### Template de Cheat Sheet
```markdown
# Cheat Sheet: [Topic]

## Command 1: [name]
```bash
[command] [options] [example]
```
**Purpose:** [what it does]
**When to use:** [SOC context]
**Example output:**
```
[realistic output]
```
```

---

## Rappel — Règles d'or de la Phase 1

1. **Tout est documenté** : si tu ne l'écris pas, ça n'existe pas.
2. **Tout est en anglais** : mauvais anglais > pas d'anglais.
3. **Tout est répété** : refaire les captures jusqu'à ce que ce soit naturel.
4. **Pas de Kali pour l'instant** : on reste sur Ubuntu + Windows. Kali vient plus tard.
5. **Les questions sont bonnes** : noter ce que tu ne comprends pas. C'est ton terrain de progrès.

---

> **Semaine 2 commence le 29 juin** : Home Lab Setup (VirtualBox, pfSense, Ubuntu Server).
> On se revoit ici après le Jour 7 (28 juin) pour valider le livrable W1.
