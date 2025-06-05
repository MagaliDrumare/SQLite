# SQLite

### Vidéo SQLite & LangChain 
- https://drive.google.com/file/d/1srtSIKtaMlEcxZXaiuOI2rL9bPKMqZmh/view?usp=sharing

## Définition de SQLite

SQLite est un système de gestion de base de données relationnelle (SGBDR) léger, autonome et embarqué, conçu pour fonctionner sans serveur externe[1][2][3]. Contrairement aux bases de données classiques comme MySQL ou PostgreSQL, qui utilisent une architecture client-serveur, SQLite s’intègre directement dans les applications et stocke l’intégralité de la base de données dans un seul fichier sur le disque. 

## Caractéristiques principales

- **Autonome et sans serveur** : Aucun processus serveur n’est nécessaire ; la base de données fonctionne directement via une bibliothèque intégrée à l’application. 
- **Légèreté** : La taille du système est très réduite (quelques centaines de kilooctets), ce qui le rend idéal pour les environnements à ressources limitées comme les appareils mobiles, les objets connectés (IoT) ou les applications embarquées. 
- **Portabilité** : La base de données est stockée dans un fichier unique, facilement transportable et indépendant de la plateforme.
- **Compatibilité SQL** : SQLite prend en charge la plupart des fonctionnalités du langage SQL standard, permettant des requêtes complexes et la gestion de transactions. 
- **Conformité ACID** : Il garantit l’intégrité et la fiabilité des données grâce à la conformité aux propriétés ACID (Atomicité, Cohérence, Isolation, Durabilité)
- **Facilité d’intégration** : SQLite est écrit en langage C et peut être utilisé avec de nombreux langages de programmation (Python, PHP, Ruby, etc.)
- **Sans configuration** : Aucune installation ou configuration complexe n’est nécessaire ; il suffit d’intégrer la bibliothèque dans l’application pour commencer à l’utiliser.

## Utilisations courantes

SQLite est largement utilisé dans :
- Les applications mobiles (Android, iOS)
- Les navigateurs web (Chrome, Firefox, Safari)
- Les logiciels de bureautique et de messagerie (ex : Skype)
- Les systèmes embarqués et IoT

## Conclusion

SQLite est donc une solution de base de données relationnelle simple, efficace et très répandue, privilégiée pour les projets nécessitant une base intégrée, portable et facile à gérer, sans la complexité d’un serveur dédié. 

- https://datascientest.com/sqlite-tout-savoir
- https://fr.wikipedia.org/wiki/SQLite
- https://www.ionos.fr/digitalguide/sites-internet/developpement-web/sqlite/
- https://kinsta.com/fr/blog/sqlite-vs-mysql/
- https://www.astera.com/fr/knowledge-center/postgresql-vs-sqlite/
- https://www.journaldunet.fr/web-tech/dictionnaire-du-webmastering/1203607-sqlite-definition/
- https://blog.stephane-robert.info/docs/services/bdd/relationnelles/sqlite/
- https://sqlite.fr


## Intégration entre SQLite et LangChain

L'intégration entre SQLite et LangChain permet de combiner la puissance d'une base de données légère (SQLite) avec les capacités avancées de traitement du langage naturel et d'agents conversationnels de LangChain. Voici les principaux modes d'intégration :

**1. Historique de conversation et mémoire**
- LangChain propose des modules comme `SQLChatMessageHistory` qui permettent de stocker l’historique des conversations dans une base SQLite. Il suffit de fournir un identifiant de session et une chaîne de connexion SQLite (par exemple, `sqlite:///sqlite.db`). Les messages utilisateurs et IA sont alors enregistrés et peuvent être récupérés pour assurer la continuité contextuelle des échanges. 

**2. Recherche vectorielle avec SQLiteVec**
- Grâce à l’extension `sqlite-vec`, SQLite peut servir de magasin de vecteurs pour des recherches sémantiques locales. Cette intégration permet d’indexer des textes, de générer des embeddings (vecteurs) et d’effectuer des recherches de similarité directement dans une base SQLite, sans serveur externe. Cela s’applique notamment aux scénarios de Retrieval-Augmented Generation (RAG). 

**3. Agents conversationnels connectés à SQLite**
- Il est possible de créer un agent LangChain qui comprend les requêtes en langage naturel, les traduit en requêtes SQL, interroge une base SQLite, puis formule une réponse basée sur les résultats. Cela permet de dialoguer avec une base de données via un chatbot, utile pour l’analyse de données, le support ou la recherche d’informations. 

**4. Utilisation de SQLAlchemy avec LangChain**
- LangChain s’appuie souvent sur SQLAlchemy pour interagir avec SQLite. On charge la base via une URI (`sqlite:///votre_base.db`), puis on utilise des chaînes personnalisées pour générer les requêtes SQL à partir d’entrées utilisateur, exécuter ces requêtes et transformer les résultats en réponses naturelles. 

## Exemples de cas d’usage

- Chatbots qui accèdent à des bases de données locales pour fournir des réponses personnalisées.
- Recherche sémantique sur des documents stockés localement (vector store).
- Applications mobiles ou embarquées nécessitant une base de données intégrée et des fonctionnalités IA sans dépendance serveur.

## Points forts de l’intégration

- **Simplicité** : Pas besoin de serveur externe, tout fonctionne en local.
- **Polyvalence** : Supporte la mémoire conversationnelle, la recherche vectorielle et le question-answering sur base de données.
- **Sécurité** : Les données restent sur l’appareil ou le serveur local.

En résumé, l’intégration entre SQLite et LangChain ouvre la voie à des applications IA locales, efficaces et faciles à déployer, particulièrement adaptées aux environnements à ressources limitées ou nécessitant la confidentialité des données. 

- https://python.langchain.com/docs/integrations/memory/sqlite/
- https://python.langchain.com/docs/integrations/vectorstores/sqlitevec/
- https://n8n.io/workflows/2292-talk-to-your-sqlite-database-with-a-langchain-ai-agent/
- https://www.youtube.com/watch?v=VZEv8oKTY-c
- https://alejandro-ao.com/chat-with-mysql-using-python-and-langchain/
- https://python.langchain.com/docs/integrations/vectorstores/sqlitevss/
- https://towardsdatascience.com/retrieval-augmented-generation-in-sqlite/
