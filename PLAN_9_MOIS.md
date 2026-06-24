# PLAN 9 MOIS — Portfolio SOC Analyst Tier 1
## Yamga Younta Yvan | Juin 2026 – Mars 2027

> **Rituel :** 22h00 – 00h00 (2h/jour) | 730h totales sur 9 mois  
> **Méthode :** 4 semaines de travail + 1 semaine de "buffer/recovery" par phase  
> **Philosophie :** Répéter jusqu'à l'habitude. Chaque phase produit des preuves.

---

## PHASE 1 : FONDATIONS & HOME LAB (5 semaines)
**Période :** 22 juin 2026 – 26 juillet 2026  
**Thème :** Comprendre comment les ordinateurs parlent, les surveiller, et les documenter.

### Semaine 1 — Réseau & Premier Contact (22-28 juin)
- **Théorie** : TCP/IP, OSI, ports, protocoles (TCP/UDP/ICMP)
- **Outil** : TryHackMe "Pre-Security" (gratuit) — compléter les 3 rooms
- **Pratique** : Wireshark — capturer 3 scénarios (navigateur, ping, DNS)
- **Vocabulaire** : 10 mots Anki (network layer, packet, port, protocol, handshake, etc.)
- **Livrable** : Document `W1_Network_Fundamentals.md` avec 3 screenshots commentés

### Semaine 2 — Home Lab : Infrastructure (29 juin – 5 juillet)
- **Setup** : VirtualBox + pfSense (firewall) + Ubuntu Server 22.04 LTS
- **Config** : Ubuntu avec SSH, pare-feu UFW, mise à jour
- **Pratique** : 20 commandes Linux essentielles (ls, cd, grep, cat, tail, sudo, etc.)
- **Livrable** : `W2_Lab_Setup.md` — schéma réseau, IP, config, 20 commandes

### Semaine 3 — Windows & Logs (6-12 juillet)

- **Setup** : VM Windows 10 Pro dans le lab (agent du SIEM futur)
- **Théorie** : Windows Event Logs — 5 Event IDs critiques (4624, 4625, 4648, 4688, 4720)
- **Pratique** : Générer une connexion échouée, la trouver dans Event Viewer
- **Outil** : Sysmon (installation + première config basique)
- **Livrable** : `W3_Windows_Logs.md` — 5 Event IDs avec définitions, 1 screenshot Event Viewer

### Semaine 4 — Linux & Logs (13-19 juillet)
- **Théorie** : `/var/log/auth.log`, `/var/log/syslog`, `journalctl`
- **Pratique** : Générer SSH échoué/réussi, le trouver dans auth.log
- **Outil** : `grep`, `awk`, `sed`, `cut` — parser un log réel
- **Livrable** : `W4_Linux_Logs.md` — 3 commandes de parsing, 1 screenshot auth.log

### Semaine 5 — Buffer & Consolidation (20-26 juillet)
- **Révision** : Refaire les 20 commandes Linux sans aide
- **Synthèse** : `Cheat_Sheet_Linux_Commands.md` (format pro, publiable)
- **Avancement** : Commencer TryHackMe "Blue Team Path" si temps
- **Livrable** : `Cheat_Sheet_Linux.md` + `Cheat_Sheet_Windows_Event_IDs.md`

**Livrables Phase 1 :** 6 artefacts
1. `W1_Network_Fundamentals.md` (3 screenshots Wireshark)
2. `W2_Lab_Setup.md` (schéma réseau + config)
3. `W3_Windows_Logs.md` (Event IDs + screenshot)
4. `W4_Linux_Logs.md` (parsing logs + screenshot)
5. `Cheat_Sheet_Linux.md` (20 commandes, format pro)
6. `Cheat_Sheet_Windows_Event_IDs.md` (10 IDs critiques)


---

## PHASE 2 : SIEM & DÉTECTION (8 semaines)
**Période :** 27 juillet 2026 – 20 septembre 2026  
**Thème :** Savoir chercher dans une mer de logs, corréler, et détecter.

### Semaine 6-7 — Wazuh SIEM (27 juillet – 9 août)
- **Setup** : Installer Wazuh sur Ubuntu Server
- **Config** : Connecter Windows 10 comme agent Wazuh
- **Test** : Générer une alerte (SSH échoué, changement de fichier) → la voir dans Wazuh
- **Livrable** : `W6_Wazuh_Setup.md` — schéma, config, 1 screenshot d'alerte

### Semaine 8-9 — Alertes & Corrélation (10-23 août)
- **Théorie** : Règles de détection, fausses alertes, seuils
- **Pratique** : Créer 3 alertes personnalisées (brute force SSH, processus suspect, connexion RDP)
- **Livrable** : `W8_Custom_Rules.md` — 3 règles avec explications + screenshots

### Semaine 10-11 — Splunk Basics (24 août – 6 septembre)
- **Cours** : Splunk Fundamentals 1 (gratuit sur splunk.com)
- **Pratique** : TryHackMe "Splunk Basics" + "Splunk 101"
- **Livrable** : `W10_Splunk_Notes.md` — notes de cours + 3 commandes SPL

### Semaine 12 — Buffer & Premier Write-up (7-20 septembre)
- **Mission** : TryHackMe "Blue Team" room — 1 room complète, write-up structuré
- **Structure** : Summary → Tools → Analysis → Findings → Recommendations
- **Livrable** : `W12_Writeup_TryHackMe.md` — premier write-up professionnel

**Livrables Phase 2 :** 6 artefacts
7. `W6_Wazuh_Setup.md`
8. `W8_Custom_Rules.md` (3 règles)
9. `W10_Splunk_Notes.md`
10. `W12_Writeup_TryHackMe.md`
11. Dashboard Wazuh (screenshot publiable)
12. `Cheat_Sheet_SIEM_Splunk.md` (commandes SPL essentielles)

---

## PHASE 3 : ATTAQUE & RÉPONSE (9 semaines)
**Période :** 21 septembre 2026 – 22 novembre 2026  
**Thème :** Connaître l'ennemi. Comprendre MITRE ATT&CK. Rédiger des procédures.

### Semaine 13-14 — MITRE ATT&CK (21 sept – 4 oct)
- **Théorie** : 15 techniques de MITRE ATT&CK (T1110, T1566, T1204, T1078, T1059, etc.)
- **Pratique** : Pour chaque technique : définition + exemple concret + log/alerte associée
- **Livrable** : `MITRE_ATT&CK_Table.md` — tableau de 15 techniques avec logs associés

### Semaine 15-16 — CyberDefenders Labs (5-18 oct)
- **Mission** : 2 labs CyberDefenders (gratuits, réalistes)
- **Write-up** : Structure rigide pour chaque lab
- **Livrable** : `CD_Lab1_Investigation.md` + `CD_Lab2_Investigation.md`

### Semaine 17-18 — Playbooks (19 oct – 1 nov)
- **Playbook 1** : "Brute Force RDP — Investigation Procedure"
- **Playbook 2** : "Phishing Email — Triage & Response"
- **Playbook 3** : "Suspicious Windows Process — Investigation"
- **Livrable** : `Playbook_01_BruteForce_RDP.md` + `Playbook_02_Phishing.md` + `Playbook_03_Suspect_Process.md`

### Semaine 19 — Buffer & Consolidation (2-22 nov)
- **Révision** : Refaire les 3 playbooks de mémoire
- **Synthèse** : Tableau de corrélation "Technique MITRE → Log → Playbook"
- **Livrable** : `Correlation_Matrix.md` — matrice Technique/Log/Playbook

**Livrables Phase 3 :** 6 artefacts
13. `MITRE_ATT&CK_Table.md` (15 techniques)
14. `CD_Lab1_Investigation.md`
15. `CD_Lab2_Investigation.md`
16. `Playbook_01_BruteForce_RDP.md`
17. `Playbook_02_Phishing.md`
18. `Playbook_03_Suspect_Process.md`

---

## PHASE 4 : AUTOMATION & MENACES (9 semaines)
**Période :** 23 novembre 2026 – 24 janvier 2027  
**Thème :** Automatiser, analyser les menaces, et compiler son savoir.

### Semaine 20-21 — Python pour SOC (23 nov – 6 déc)
- **Script 1** : Parser un fichier log (auth.log) et compter les IPs échouées
- **Script 2** : Checker une IP via VirusTotal API (gratuit)
- **Script 3** : Générer un rapport texte à partir d'une alerte Wazuh
- **Livrable** : `scripts/` dossier avec 3 scripts commentés + README

### Semaine 22-23 — Threat Intelligence (7-20 déc)
- **Mission** : Choisir une campagne récente (ex: ransomware). Rechercher IOCs (IPs, hashes, domaines).
- **Rapport** : "Threat Intelligence Brief — [Campagne]" — 5 pages
- **Livrable** : `TI_Brief_Campagne.md` — rapport structuré avec sources

### Semaine 24-25 — Cloud Security Basics (21 déc – 10 jan)
- **Théorie** : AWS/Azure/GCP — services de sécurité de base (IAM, CloudTrail, GuardDuty)
- **Pratique** : Compte AWS Free Tier — activer CloudTrail, voir 3 events
- **Livrable** : `Cloud_Security_Basics.md` — 3 services + 1 screenshot CloudTrail

### Semaine 26-27 — SOC Survival Guide (11-24 jan)
- **Compilation** : 15-20 pages PDF regroupant :
  - Cheat sheets Linux, Windows, SIEM
  - Tableau MITRE ATT&CK
  - 3 playbooks
  - Liste d'outils avec descriptions
- **Livrable** : `SOC_Analyst_Survival_Guide.pdf` — document publiable

**Livrables Phase 4 :** 6 artefacts
19. `scripts/` (3 scripts Python)
20. `TI_Brief_Campagne.md`
21. `Cloud_Security_Basics.md`
22. `SOC_Analyst_Survival_Guide.pdf`
23. `Cheat_Sheet_MITRE.md` (version condensée)
24. `Cheat_Sheet_Splunk_Splunk.md` (version avancée)

---

## PHASE 5 : CERTIFICATION & POLISSAGE (8 semaines)
**Période :** 25 janvier 2027 – 22 mars 2027  
**Thème :** Le mot magique sur le CV, le profil pro, et la préparation aux entretiens.

### Semaine 28-30 — Certification (25 jan – 15 fév)
- **Option A** : ISC2 CC (Certified in Cybersecurity) — gratuit
- **Option B** : Splunk Core Certified User — ~120€, très recherché
- **Option C** : CompTIA Security+ — ~300€, plus difficile mais plus reconnu
- **Étude** : 45 min/jour théorie + 15 min quiz
- **Livrable** : Certificat PDF + badge LinkedIn

### Semaine 31-32 — GitHub & LinkedIn (16 fév – 1 mars)
- **GitHub** : Publier tout le contenu des 4 phases. Structure propre. README en anglais.
- **LinkedIn** : Titre "Aspiring SOC Analyst | Blue Team | Home Lab | [Certification]"
- **About** : Paragraphe en anglais vendant ton parcours
- **Livrable** : Repo GitHub public + profil LinkedIn optimisé

### Semaine 33-34 — Mock Interviews (2-15 mars)
- **Questions** : 15 questions classiques SOC Tier 1
- **Entraînement** : S'enregistrer en vidéo/audio, répondre en anglais
- **Correction** : Analyse des réponses, affiner les tournures
- **Livrable** : Fichier `Interview_QA.md` — 15 questions + réponses scriptées

### Semaine 35-36 — Candidatures (16-22 mars)
- **Cible** : MSSP, ESN/SSII en Allemagne, remote EU (Pays-Bas, Belgique, Luxembourg)
- **Objectif** : 20 candidatures minimum
- **Livrable** : Fichier `Job_Applications_Log.md` — 20 lignes avec statut

**Livrables Phase 5 :** 3 artefacts
25. `Certificat_[Nom].pdf` + badge LinkedIn
26. `GitHub_Repo_Public` + `LinkedIn_Profile.md` (texte de référence)
27. `Interview_QA.md` + `Job_Applications_Log.md` (20 candidatures)

---

## TOTAL : 27 ARTEFACTS

| Catégorie | Nombre |
|-----------|--------|
| Documents Markdown (analyses, notes, playbooks) | 18 |
| Cheat Sheets | 4 |
| Scripts Python | 3 |
| PDF (Survival Guide) | 1 |
| Certificat | 1 |
| **TOTAL** | **27** |

---

## Calendrier Visuel

```
2026
Juin    ████░░░░░░░░░░░░░░░░░░  Sem 1-2 (Phase 1)
Juil    ████░░░░░░░░░░░░░░░░░░  Sem 3-5 (Phase 1)
Août    ████████░░░░░░░░░░░░░░  Sem 6-9 (Phase 2)
Sept    ████████░░░░░░░░░░░░░░  Sem 10-12 (Phase 2)
Oct     █████████░░░░░░░░░░░░░  Sem 13-16 (Phase 3)
Nov     █████░░░░░░░░░░░░░░░░░  Sem 17-19 (Phase 3)
Déc     █████████░░░░░░░░░░░░░  Sem 20-23 (Phase 4)

2027
Janv    █████░░░░░░░░░░░░░░░░░  Sem 24-27 (Phase 4)
Fév     ████████░░░░░░░░░░░░░░  Sem 28-32 (Phase 5)
Mars    ██████░░░░░░░░░░░░░░░░  Sem 33-36 (Phase 5)
```

---

> **Prochaine étape :** Ouvrir `PHASE_01_Fondations_Lab/PHASE_01_PLAN.md` et commencer la Semaine 1, Jour 1 (22 juin 2026).
