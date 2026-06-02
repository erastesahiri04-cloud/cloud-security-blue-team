# IAM — Identity & Access Management

## À quoi sert IAM
IAM est le service AWS qui permet de gérer les identités et les accès.
Il définit qui peut accéder aux ressources AWS, quelles actions sont 
autorisées et dans quelles conditions.
IAM repose sur des utilisateurs, des groupes, des rôles et des policies.

## Pourquoi IAM est le cœur de la sécurité cloud
La majorité des incidents de sécurité sur le cloud proviennent d'une 
mauvaise configuration IAM. Des permissions trop larges, l'absence de MFA 
ou des clés exposées peuvent permettre à un attaquant de prendre le contrôle 
d'un compte AWS complet.

## Principes appliqués dans ce repo

### Groupe plutôt que user direct
On n'attache jamais une policy directement à un user. On l'attache au groupe,
et on ajoute le user au groupe. Cela permet de gérer des dizaines d'utilisateurs
en modifiant un seul objet, et de garder une lecture claire de "qui peut faire quoi".

### Policy attachée plutôt qu'inline
Une inline policy est écrite directement dans le groupe — elle n'est pas 
réutilisable et difficile à auditer. Une policy attachée est un objet IAM 
indépendant : versionnable, réutilisable, modifiable séparément.
En production, on attache toujours. On ne crée une inline policy que pour 
un cas d'usage unique et temporaire.

### Least Privilege
Chaque user reçoit uniquement les permissions dont il a besoin pour sa fonction,
rien de plus. Un analyst qui peut lire EC2 ne peut pas lancer d'instance.
Cela limite le rayon d'impact en cas de compromission.

## Structure du dossier
- `policies/ec2-readonly.json` — policy EC2 read-only pour le groupe Analysts
- `policies/s3-restricted.json` — policy S3 restreinte à un bucket (Lab 1.3)
- `attack-simulation.md` — simulation d'attaque IAM et correction (Lab 1.4)
