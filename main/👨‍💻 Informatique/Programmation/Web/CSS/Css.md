# 1: Textes et polices

**1) héritage d'attribut**
Pour définir la couleur d'un texte ont utilise l'attribut "color:" mais si vous voulez utiliser la même couleur pour tout ce qui découle de la class ou la catégorie spécifié vous pourrez utiliser l'attribut "inherit" sur les prochain blocks de textes: 

```css
/*definit_la_couleur_pour_la_class_header*/
.header {
	color: #FFFFFF;
}
/*definit la couleur des liens de la class header en fonction de la couleur de la class header*/
.header a {
	color: inherit;
}
```

**2) gestion de police**

Pour définir une police à utilisé ont utilise l'attribut `font-family`, mais ==attention==: Il est important d'entrer plusieurs polices pour paliers au problèmes de compatibilité des autres navigateur, de plus la dernière police devrat être sans-serif ou serif:
```css
.main {
	font-family: 'Nunito', Arial, sans-serif;
}```

**3) taille de polices et hauteur de ligne**

La taille de la police peut être définit par l'attribut font-size:
```css
.title {
	font-size: 20px;
}```

Pour définir l'espace entre les lignes de texte, ont utilise l'attribut `line-height`, la valeur d'espacement peut être définis en pixel et autres unités mais aussi sans unité, l'espace serat alors calculé par rapport à la taille du texte:
```css
.text {
	line-height: 1.5; /* içi l'espace serat 140% de la police */
}```

**4) position de text**

Pour gérer la position et l'alignement d'un text ont utilise l'attribut `text-align` qui peut prendre plusieur paramètre: right(align le text à droite), left(align le text à gauche), center(centre le text), justify(occupe tout l'espace disponible)...
```css
.text {
	text-align: center
}```

**5) gérer des retours à la ligne**

Pour qu'un retour à la ligne ait lieux si il manque d'espace pour un mots ont utilise `&shy;`: 
```html
<p>voici un mot, supercalifragi&shy;listic</p>
```

