# AWS Security Setup

## 1. Root User Security
- MFA activée sur le compte root
- Aucune clé API root active
- Adresse e-mail de contact confirmée
- Le root n'est utilisé que pour les actions exceptionnelles sans alternative IAM

## 2. Budget et alertes
- Budget mensuel configuré avec alerte email en cas de dépassement

## 3. IAM Users
- Deux utilisateurs IAM créés : iam-admin et iam-analyst
- Séparation des rôles : admin pour la gestion, analyst pour la lecture
- MFA activée sur les deux users (Passkey / Windows Hello)
- Permissions appliquées via groupes uniquement, jamais directement sur les users

## 4. Prochaines étapes
- Lab 1.3 : Least Privilege avec S3
- Lab 1.4 : Simulation d'attaque IAM
- Phase 2 : VPC et Security Groups
- Phase 3 : CloudTrail + CloudWatch

## Pourquoi ne jamais utiliser le root
Le compte root possède tous les droits sans restriction.
En cas de compromission, un attaquant peut détruire ou détourner
l'ensemble du compte AWS sans possibilité de limitation.
De plus, le root ne permet pas une gestion fine des permissions
ni une bonne traçabilité.

Bonne pratique AWS : utiliser uniquement des utilisateurs IAM
ou des rôles pour les actions quotidiennes.
Le compte root est réservé aux actions exceptionnelles.
