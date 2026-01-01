# Cloud Security Blue Team

## Qui je suis
Je m'appelle Sahiri Othniel. Je suis passionné par l'informatique et le cloud computing. Je suis actuellement en licence Administration et Sécurité des Systèmes et Réseaux Informatiques, avec une spécialisation personnelle pour devenir Cloud Security Engineer orienté Blue Team.

## Objectif du repo
Ce repository documente mon parcours pratique pour apprendre et maîtriser AWS, la gestion des identifiants (IAM), la sécurité réseau et la gestion des incidents.

## Stack utilisée
- AWS (IAM, VPC, CloudTrail, CloudWatch)  
- GitHub pour versionner mes labs  
- Outils de monitoring et d’alerting (à détailler plus tard)

## Vision
D'ici fin février, je veux être capable de sécuriser un environnement AWS, détecter et analyser les incidents de sécurité, et disposer d'un portfolio complet de labs pratiques pour mon avenir professionnel en informatique.

## Security mindset & Shared Responsibility

AWS repose sur un modèle de responsabilité partagée.
AWS est responsable de la sécurité du cloud, incluant l’infrastructure physique, les datacenters, le réseau et le matériel.
Le client est responsable de la sécurité dans le cloud, notamment la gestion des identités et des accès (IAM), la configuration sécurisée des services, la protection des données et la surveillance.

Mon security mindset est orienté Blue Team : je pars du principe que toute mauvaise configuration côté client peut devenir une faille de sécurité.
Je considère IAM, la journalisation, le monitoring et le contrôle des accès comme des piliers essentiels pour prévenir, détecter et analyser les incidents sur AWS.

## IAM Learning 
– Jour 4

### Ce que j'ai compris
- Les policies AWS sont en JSON et ont des composants clairs : Version, Statement, Effect, Action, Resource
- Effect “Allow” ou “Deny” détermine le droit
- IAM est central pour la sécurité : mauvaise policy = faille
- Même une permission “read-only” peut révéler des informations sensibles

### Ce qui est encore flou
- La syntaxe exacte de certaines actions avancées
- L’application combinée de plusieurs policies sur un même user/role
- L’usage de conditions complexes dans les policies

          +----------------+
          |    User1       |
          +----------------+
                 |
                 v
          +----------------+
          |    Group1      |
          +----------------+
                 |
                 v
          +----------------+
          |   Policy1      |
          | (s3:ListBucket)|
          +----------------+
                 |
                 v
          +----------------+
          | AWS Service    |
          |  (S3 Bucket)   |
          +----------------+

User → identité

Group → regroupe users

Policy → définit permissions

Service AWS → cible des actions

