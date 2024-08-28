**informations générales**
- TCP
- client-server protocol. 
- ports par défaut:
- 21: commandes
- 20: transfert de données
- accept les anonymous login
- données non chiffrés


# Explications

File Transfer Protocol (FTP) est, comme son nom l'indique, un protocole utilisé pour permettre le transfert à distance de fichiers sur un réseau. Il utilise un modèle client-serveur.

**important:** Une session ftp fonctionne sur deux canaux:
- un canal de commande
- un canal de données.
Cette séparation des informations de commande et des données dans des canaux séparés est un moyen de pouvoir envoyer des commandes au serveur sans avoir à attendre la fin du transfert de données en cours.

**important:** Le serveur FTP peut prendre en charge les connexions actives ou passives, ou les deux:
- Dans une connexion FTP active, le client ouvre un port et écoute. Le serveur doit s'y connecter activement.  
- Dans une connexion FTP passive, le serveur ouvre un port et écoute (passivement) et le client s'y connecte.

# Enumération

voir notes (**Enumération**)
ou https://www.exploit-db.com/exploits/20745

# Exploitation

**Syntaxe:** ftp (ip)

Dans un premier temps ont peut essayer de bruteforce le mot de passe du serveur ftp.
