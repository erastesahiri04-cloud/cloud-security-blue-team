# IAM Attack Simulation — Lab 1.4

## 5 actions critiques d'un attaquant avec AdministratorAccess

### 1. Désactiver CloudTrail
C'est l'action la plus dangereuse : une fois désactivé, l'attaquant devient 
intraçable et peut mener toutes ses actions suivantes sans laisser de trace 
dans les logs.

### 2. Créer un user backdoor
L'attaquant crée un nouvel utilisateur IAM avec ses propres credentials et 
des droits élevés. Même si on détecte la compromission initiale, il garde 
un accès persistant au compte.

### 3. Exfiltrer les données S3
Les buckets S3 stockent souvent des données sensibles de l'entreprise. 
L'attaquant peut télécharger l'intégralité du contenu et compromettre 
la confidentialité des données clients ou internes.

### 4. Modifier les Security Groups
En ouvrant des ports dangereux, l'attaquant expose les serveurs à des 
attaques réseau supplémentaires et crée des points d'entrée additionnels 
dans l'infrastructure.

### 5. Supprimer les policies IAM
En supprimant ou modifiant les policies existantes, l'attaquant peut 
révoquer les droits des administrateurs légitimes et saboter la capacité 
de l'équipe à répondre à l'incident.
