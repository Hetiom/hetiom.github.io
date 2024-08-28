**Informations générales:**
- Port par défaut: 25
- All OS

# Explication

SMTP, "**Simple Mail Transfer Protocol**" est utilisé pour gérer l'envoi d'e-mails. Afin de prendre en charge les services de messagerie, une paire de protocoles est requise, comprenant **SMTP** et **POP/IMAP**. Ensemble, ils permettent à l'utilisateur d'envoyer le courrier sortant(**SMTP**) et de récupérer le courrier entrant(**POP/IMAP**)

**POP et IMAP:**
POP, ou "Post Office Protocol" et IMAP, "Internet Message Access Protocol" sont tous deux des protocoles de messagerie qui se chargent du transfert de mails entre un client et un serveur de messagerie. Les principales différences résident dans l'approche plus simpliste de POP consistant à télécharger la boîte de réception du serveur de messagerie vers le client. Où IMAP synchronisera la boîte de réception actuelle, avec le nouveau courrier sur le serveur, en téléchargeant tout ce qui est nouveau. Cela signifie que les modifications apportées à la boîte de réception sur un ordinateur, via IMAP, persisteront si vous synchronisez ensuite la boîte de réception à partir d'un autre ordinateur.

**fonctionnement:**

![[main/Images et liens/Pasted image 20230211145725.png]]

![[main/Images et liens/Pasted image 20230211153152.png]]

**Version simplifié:**
**1.** Votre client de messagerie se connecte au serveur SMTP de votre domaine, par ex. smtp.google.com. Cela lance le handshake SMTP. Une fois ces connexions établies et validées, la session SMTP démarre.  
  
**2.** Le processus d'envoi de courrier peut maintenant commencer. Le client soumet d'abord l'expéditeur et l'adresse e-mail du destinataire (le corps de l'e-mail et toutes les pièces jointes) au serveur.  
  
**3.** Le serveur SMTP vérifie alors si le nom de domaine du destinataire et de l'expéditeur est le même.  
  
**4.** Le serveur SMTP de l'expéditeur établira une connexion avec le serveur SMTP du destinataire. Si le serveur du destinataire n'est pas accessible ou n'est pas disponible, l'e-mail est placé dans une file d'attente SMTP.  
  
**5.** Ensuite, le serveur SMTP du destinataire vérifiera l'e-mail entrant, il vérifie si le domaine et le nom d'utilisateur ont été reconnus. Le serveur transmettra ensuite l'e-mail au serveur POP ou IMAP, comme indiqué dans le schéma ci-dessus.

**Liens utiles:**
- https://www.afternerd.com/blog/smtp/
- https://computer.howstuffworks.com/e-mail-messaging/email3.htm

# Enumération

voir notes (**Enumération**)

Utilisation de metasploit: 
**Modules:** smtp_version & smtp_module

# Exploitation
 Bruteforce O_o
