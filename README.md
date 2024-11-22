# NoSQL
# Redis

## Introduction : les Bases de Données NoSQL

Contrairement aux bases de données relationnelles traditionnelles, qui utilisent des tables et des relations entre données, les bases de données NoSQL sont conçues pour répondre aux besoins modernes de scalabilité et de rapidité. Elles se divisent en quatre grandes familles :

### 1. Bases de données clé-valeur
Dans ce type, les données sont stockées sous forme de paires clé-valeur, où chaque clé est unique et associée à une valeur. C’est une structure simple, idéale pour les systèmes nécessitant une récupération rapide. Redis appartient à cette catégorie.

### 2. Bases de données orientées colonnes
Elles stockent les données en colonnes plutôt qu’en lignes, optimisant les requêtes analytiques sur de grands ensembles de données. Cassandra est un exemple typique.

### 3. Bases de données orientées documents
Ces bases utilisent des formats comme JSON ou BSON pour stocker les données. Elles sont idéales pour des structures complexes ou des cas où les données peuvent varier d’un document à l’autre. MongoDB en est un exemple courant.

### 4. Bases de données orientées graphes
Conçues pour gérer des relations complexes entre entités, elles sont parfaites pour des cas comme les réseaux sociaux ou les systèmes de recommandation. Neo4j est une base de données orientée graphes bien connue.

---

## Redis : Présentation et Fonctionnalités

### Qu’est-ce que Redis ?
Redis est une base de données NoSQL de type clé-valeur, open-source, connue pour sa rapidité. Elle stocke les données principalement en mémoire pour des performances optimales, avec des options pour la persistance sur disque.

### Objectif
Redis offre un ensemble riche de fonctionnalités pour la manipulation des données, telles que la création, la suppression, et la gestion des clés. Il est particulièrement utilisé comme cache, file d’attente de messages, ou encore pour le stockage temporaire de sessions.

---

## Utilisation de Redis : Concepts de Base

### Lancement du serveur Redis
- **Démarrer le serveur** : `redis-server`
- **Utiliser un client pour interagir avec la base** : `redis-cli`

### Gestion des clés
- **Créer une clé** : `SET macle mavaleur`
- **Lire une clé** : `GET macle`
- **Définir une durée de vie (TTL)** : `EXPIRE macle 120`
- **Supprimer une clé** : `DEL macle`

### Listes
Redis permet de créer et de gérer des listes ordonnées :
- **Ajouter des éléments** : `RPUSH mescours "BDA"`
- **Afficher les éléments** : `LRANGE mescours 0 -1`
- **Supprimer un élément** : `LPOP mescours`

Les listes autorisent les doublons, contrairement aux ensembles.

### Ensembles (Sets)
Les ensembles contiennent des éléments uniques :
- **Ajouter des éléments** : `SADD utilisateurs "sarra"`
- **Afficher tous les éléments** : `SMEMBERS utilisateurs`
- **Supprimer un élément** : `SREM utilisateurs "marc"`

Redis permet également des opérations comme l’union ou l’intersection entre deux ensembles.

---

## Structures Avancées

### Ensembles triés (Sorted Sets)
Les ensembles triés associent chaque élément à un score pour maintenir un ordre :
- **Ajouter des éléments avec score** : `ZADD leaderboard 100 "Alice"`
- **Afficher une plage d’éléments** : `ZRANGE leaderboard 0 -1`

### Hashes
Les Hashes sont utilisés pour stocker des objets structurés :
- **Ajouter des champs** : `HSET user:1 username "Alice"`
- **Afficher tous les champs** : `HGETALL user:1`
- **Incrémenter une valeur** : `HINCRBY user:1 age 1`

---

## Communication Pub/Sub
Redis permet une communication entre processus via des canaux :
- **S’abonner à un canal** : `SUBSCRIBE mesCours`
- **Publier un message** : `PUBLISH mesCours "Un nouveau cours sur Redis"`

---

## Fonctionnalités Avancées

### Gestion de la persistance
Redis peut sauvegarder les données en mémoire sur disque pour garantir leur persistance. Cela permet de récupérer les données en cas de panne.

### Concurrence
Redis est conçu pour gérer de multiples utilisateurs simultanés, garantissant la cohérence des données grâce à son architecture mono-threadée et à ses commandes atomiques.

### Bases multiples
Par défaut, Redis propose 16 bases de données accessibles via `SELECT`. Chaque base est indépendante, mais elles partagent la même mémoire.

---

## Utilisation Courante de Redis
Redis est souvent utilisé conjointement avec une base de données relationnelle pour bénéficier de sa rapidité en mémoire tout en conservant les données critiques sur disque. Par exemple :
- **Cache** : Pour accélérer l’accès aux données fréquemment utilisées.
- **Gestion de sessions** : Stockage temporaire des sessions utilisateur.
- **Analyse en temps réel** : Pour des systèmes de score, des classements, etc.

---

## Conclusion
Redis est un outil puissant et polyvalent pour manipuler des données rapidement et efficacement. En tant que base de données NoSQL de type clé-valeur, elle offre une structure simple et une performance optimale.
