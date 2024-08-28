# Tool
**Sublist3r** est un tool qui permet d'automatiser la recherche osint de sous domaines grâce à des techniques de dorking et de nombreuses bases de données. 
https://github.com/aboul3la/Sublist3r

**ffuf** est un tool qui permet d'automatiser la recherche de sous domaines via virtual host. (voir notes ffuf)
https://github.com/ffuf/ffuf

# Certificats SSL/TLS
***Pour les sites possédants un certificat SSL ou TLS, des logs sont conservés sur l'activités de ses sites et de leur domaines, ont peut donc y retrouver la création de tout les sous domaines associés:***
- https://crt.sh/
- https://ui.ctsearch.entrust.com/ui/ctsearchui

# Dorking
***Avec une recherche filtré grâce à du google dorking ont peut trouvé les sous domaines indexés par google:***
- "-site:www.domain.com site:*.domain.com"

# Brute force
***Ont peut utiliser un tool comme dnsrecon pour brute force les sous domaines d'un site à partir d'une wordlist***