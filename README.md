# Homelab - Infrastructure sécurisée

## 👤 Présentation

Projet personnel d'infrastructure visant à reproduire un environnement d'entreprise afin de :
- Pratiquer l'administration système et réseaux
- Expérimenter la segmentation VLAN
- Mettre en oeuvre des politiques de sécurité
- Automatiser des tâches d'exploitation
- Documenter une infrastructure de manière professionnelle

Ce projet s'inscrit dans ma formation Administrateur d'Infrastructure Sécurisées (AIS).

---

## 🎯 Objectifs

- Concevoir une architecture réseau segmentée
- Mettre en place un firewall centralisé
- Déployer des services virtualisé
- Implémenter une stratégie de sauvegarde
- Mettre en place une supervision
- Produire une documentation complète (architecture, procédures, runbooks)

---

## 🏗️ Architecture globale

### Infrastructure physique

| Équipement | Rôle |
|------------|------|
| Mini-PC MS-01 | Hyperviseur principal (Proxmox) |
| Mini-PC Byte | Stockage & sauvegarde (TrueNAS / PBS) |
| Switch manageable | VLAN & segmentation |
| Box internet | Accès WAN |

### Infrastructure virtuelle

| VM | Rôle | VLAN |
|----|------|------|
| OPNSense | Firewall & routage | Core |
| Debian Admin | Poste d’administration | Admin |
| Ubuntu Technique | VM technique | Tech |
| Windows Server | AD / Services | Serveur |
| Windows 11 | Poste client domaine | Utilisateurs |
| VM Supervision | Monitoring | Supervision |
| VM Test  | Environnement de validation & restauration | Environnement-Test |

---

## 🌐 Segmentation réseau

- VLAN Admin
- VLAN Serveur
- VLAN Utilisateurs
- VLAN Technique
- VLAN Supervision
- VLAN Environnement-Test
- VLAN WAN

Une matrice de flux est disponible dans `/architecture/matrice_flux.md`.

---

## 🔐 Sécurité

- Firewall centralisé (OPNSense)
- Règles inter-VLAN restrictives
- Accès administration limité au VLAN Admin
- Sauvegardes planifiées
- Gestion des droits Linux
- Politique de séparation des rôles

Détails dans `/security/`.

---

## 💾 Sauvegarde & Continuité

- Proxmox Backup Server
- Snapshots planifiés
- Stockage ZFS
- Tests de restauration réalisés dans le VLAN Environnement-Test
- Validation d’intégrité des sauvegardes

L’environnement de test permet de valider les procédures de restauration sans impacter les services simulant la production.

Les procédures de test sont documentées dans `/docs/restore_backup.md`.

---

## 📊 Supervision

- Monitoring des ressources
- Alertes sur seuils critiques
- Scripts de contrôle de services

Documentation : `/docs/supervision.md`

---

## ⚙️ Automatisation

Scripts développés :

- Monitoring système
- Sauvegarde avec rotation
- Nettoyage de logs
- Vérification de services
- Montage rclone

Disponibles dans `/scripts/`.

---

## 🛠️ Stack technique

- Proxmox VE
- OPNSense
- Debian / Ubuntu
- Windows Server
- ZFS
- Bash / PowerShell
- Git / GitHub
- Mermaid (diagrammes)

---

## 📚 Documentation

| Dossier | Contenu |
|----------|----------|
| architecture | Diagrammes & conception |
| inventory | Inventaire matériel & VM |
| security | Politique sécurité & risques |
| docs | Procédures d’exploitation |
| runbooks | Gestion d’incidents |
| scripts | Automatisation |

---

## 🚀 Roadmap

- [ ] Implémentation PKI interne
- [ ] Mise en place d’un reverse proxy
- [ ] Centralisation des logs
- [ ] Déploiement Ansible
- [ ] Tests de reprise après incident

---

## 📎 Compétences mobilisées

- Conception d’architecture réseau
- Segmentation VLAN
- Administration Linux
- Gestion des permissions
- Automatisation Bash
- Gestion de sauvegardes
- Documentation technique structurée

---

## 📌 Conclusion

Ce homelab est conçu comme un environnement d’entraînement professionnel,
avec une approche orientée sécurité, documentation et exploitabilité.
