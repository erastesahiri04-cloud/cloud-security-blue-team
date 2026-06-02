# IAM – Identity and Access Management

## À quoi sert IAM
IAM est le service AWS qui permet de gérer les identités et les accès.
Il définit qui peut accéder aux ressources AWS, quelles actions sont autorisées et dans quelles conditions.
IAM repose sur des utilisateurs, des groupes, des rôles et des policies.

## Pourquoi IAM est le cœur de la sécurité cloud
La majorité des incidents de sécurité sur le cloud proviennent d’une mauvaise configuration IAM.
Des permissions trop larges, l’absence de MFA ou des clés exposées peuvent permettre à un attaquant de prendre le contrôle d’un compte AWS.
En Cloud Security Blue Team, IAM est un pilier essentiel pour appliquer le principe du moindre privilège, limiter l’impact d’un incident et contrôler les accès aux ressources.

## Lab 1.2  : pourquoi on attache au groupe, pas au user, et ce que le least privilege a produit concrètement?
Pour une bonne pratique il est important d'attacher une policy json au group directement parce que c'et plus simple pour la gestion si on veux attribue des droit à un utilisateur on l'ajoute à un groupe lustot que de lui donner directement ça facilite la gestion on n'attache à un groupe à on peut gerer des dizaines de user iam , pour le groupe aussi mieux vaux attache que faire de l'inline, une inline policy est écrite directement dans le groupe et n'est pas réutilisable. Une policy attachée est un objet IAM indépendant que tu peux auditer, réutiliser, et modifier séparément. En production, on attache toujours on ne crée jamais d'inline policy sans raison précise. enfin le least privilege parmet d'avoir un user qui peut faire uniquement ce qui lui est autorisé pour eviter et reduire les degat 
