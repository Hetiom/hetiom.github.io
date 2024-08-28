# Liens utiles:
https://www.youtube.com/watch?v=bG_orHEJxa0

# Tips:
"--spoofmac (adresse mac)""  pour changer d'adresse mac durant le scan
# General options:
Pour un scan TCP:

"-vv"                                           affiche des info sur ce qu'ils ce passe ==(toujours l'utiliser)==
"-oN" (nom du fichier)"             enregistre au format normal
"-sV"                                          services des ports ouverts
"-T1,2,3,4,5"                              accélères le vitesse du scan T5 étant le plus rapide
"-sA"                                          détecte le filtrage de parrefeux
"-A"                                            scan avec plusieurs paramètres "aggressifs"
"-p-"                                          scan Tous les ports (==toujours utiliser pour de l'énumération)==
"-sS"                                          scan furtif (juste SYN puis SYN/ACK)
"-sN"                                         scan furtif packet vide sans flag
"-sX"                                          scan furtif 

Pour un scan UDP:

"-sU"                                          pour un scan UDP
"--top-ports 20"                       scan les ports les plus utilisez afin de réduire le temps
# Firewall
"-sN"                                          scan furtif packet vide sans flag
"-sF"                                          scan furtif avec pack FIN
"-sX"                                          scan furtif 
# Map:
-sn ip/(4; 8; 16; 24)                     vas ping toutes les adresse ip du réseau spécifié dans une range spécifié

# Scripts:

tous les scripts locaux se trouves dans: /usr/share/nmap/scripts/script.db

![[main/Images et liens/Pasted image 20221203164347.png]]