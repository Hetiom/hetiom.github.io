**Bypass**: 
- **Désactiver javascript dans son navigateur**
- **Intercepter et modifier la page qui arrive** (avec Burp par example) afin de désactiver le filtre js.
- **Intercepter et modifier l'upload**. Là où la méthode précédente fonctionne avant que la page Web ne soit chargée, cette méthode permet à la page de se charger mais intercepte l'upload du fichier une fois qu'il est déjà accepté par le filtre. Exemple, si le filtre interdit les fichier en .php et .js, j'upload mon shell avec l'extension .png puis je capture la requête pour modifier l'extension de mon shell avant qu'il n'arrive au serveur.
- **Envoyer directement le fichier au serveur** en utilisant curl par example.