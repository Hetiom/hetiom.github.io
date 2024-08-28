***Chaque requête a une structure spécifique qui a cette forme :***

**Verbe HTTP + URI + Version HTTP + Headers + Body (facultatif)**
(*L’aspect peut varier en fonction du logiciel ou du langage utilisé.*)

- **Verbes HTTP** correspondent à différents types d’actions, les plus courant sont ***GET*** (obtenir), ***PUT*** (mettre), ***POST*** (publier), et ***DELETE*** (supprimer).
- **URI** permet d'identifier une ressource et son chemin d'accès, ***exemple: data/user:Tomas***
- **Header** permet de faire passer des informations supplémentaires: De quel langage s’agit-il , À quelle date l’envoyez-vous, Quelle est votre clé d’authentification... Les headers sont représentés par une ***paire clé et valeur***. Par exemple "Date : Mardi 19 Janvier 2019"
- **Body** utiliser avec PUT et POST, contient les données réelles de la ressource que vous essayez de créer ou de mettre à jour. Les données sont envoyées sous format JSON.

# Code de réponse HTTP

***En général, les règles de base pour les codes de réponse HTTP sont les suivantes :**
-   **100+** ➡ **Information**
-   **200+** ➡ **Succès**
-   **300+** ➡ **Redirection**
-   **400+** ➡ **Erreur client**
-   **500+** ➡ **Erreur serveur**

doc: https://developer.mozilla.org/fr/docs/Web/HTTP/Status


# CRUD

**Le CRUD** est la liste des actions de base que vous pouvez effectuer sur une ressource. C’est un acronyme qui signifie **_C_**_reate_ (créer), **_R_**_ead_ (lire), **_U_**_pdate_ (mettre à jour), et **_D_**_elete_ (supprimer). Bien que le CRUD ne constitue pas vraiment un mécanisme technique en soi, chaque **action CRUD** est associée à un **verbe HTTP**. Voici la cartographie :

![[main/Images et liens/Pasted image 20230217123017.png]]
