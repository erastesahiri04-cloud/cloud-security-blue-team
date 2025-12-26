# AWS Security Setup

## 1. Root User Security
- MFA (Multi-Factor Authentication) activée pour le root user
- Aucune clé API root active
- Adresse e-mail de contact confirmée

## 2. Budget et alertes
- Budget mensuel : 15.6$  
- Alerte e-mail configurée si dépassement

## 3. IAM Users
- Création d’un utilisateur IAM dédié pour les labs
- Attribution des permissions minimales nécessaires (principe du moindre privilège)
- MFA activée pour tous les utilisateurs IAM sensibles

## 4. Suivi et documentation
- Tous les changements de configuration sont documentés dans ce fichier
- Les prochaines étapes : activer CloudTrail, CloudWatch et VPC logging
