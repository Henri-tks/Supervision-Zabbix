# Supervision d'infrastructure avec Zabbix

Lab réalisé en B2 à Sup de Vinci (module Initiation à la supervision, février 2026).
Objectif : mettre en place une supervision de bout en bout d'un petit parc hétérogène avec Zabbix 7.0.

## Périmètre supervisé
- 1 serveur Linux (Ubuntu) via agent Zabbix
- 1 serveur Windows via SNMP
- 1 routeur Cisco via SNMP
- Environnement virtualisé : [hyperviseur à confirmer]

## Ce qui a été mis en place
- Organisation en groupes d'hôtes et templates (Linux by Zabbix agent, Windows by SNMP, Cisco IOS by SNMP)
- Seuils d'alerte paramétrés avec des macros d'hôte (CPU 80 %, RAM 80 %, disque 90 %)
- Déclencheur CPU : alerte si > 80 % pendant 5 minutes
- Éléments personnalisés hors templates : mémoire libre via agent SSH, statut du service Spouleur via SNMP
- Tableau de bord (CPU, trafic réseau, occupation disque) et gestion des alertes (incident sur le routeur détecté par ICMP)

## Captures d'écran
### Tableau de bord
![Tableau de bord Zabbix](01-dashboard.png)

### Hôtes supervisés
![Hôtes Windows et Linux](images/02-hotes.png)

### Seuils d'alerte (macros)
![Macros de seuils](images/03-macros.png)

### Déclencheur CPU
![Déclencheur CPU](images/04-declencheur-cpu.png)

### Graphiques de charge
![Graphiques CPU](images/05-graphiques.png)

### Alerte sur le routeur R1
![Incident routeur](images/06-alerte-routeur.png)

## Compétences mobilisées
Zabbix, SNMP (v2c/v3), supervision agent / sans agent, gestion des seuils et alertes, dépannage d'un hôte muet.
