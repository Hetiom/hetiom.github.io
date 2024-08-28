**informations générales:**
- response-request protocol
- ports par défault: 
- TCP: 139 
- UDP: 445 
# Explication

SMB - Server Message Block Protocol - est un protocole de communication client-serveur utilisé pour partager l'accès aux fichiers, imprimantes, ports série et autres ressources sur un réseau.
# Enumération

voir notes (**Enumération**)
- utiliser **Enum4Linux**
# Exploitation

Parce que nous essayons d'accéder à un partage SMB, nous avons besoin d'un client pour accéder aux ressources sur les serveurs. Pour cela, on utilise SMBClient.

**Syntaxe :**   smbclient //[IP]/[SHARE]  
-U [nom] : pour spécifier l'utilisateur  
-p [port] : pour spécifier le port