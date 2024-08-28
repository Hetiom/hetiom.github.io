# Note

__**Cours 2:**__
- **un réseau de neurone possède plusieurs couches:**
	- *la couche des inputs* (des valeur données).
	- *les couches de neurones cachés* (des __Connections__ avec différents poids (le poids multiplie l'input par sa valeur) reliant deux neurones et un __Biais__(qui ajoute sa valeur à la fin du calcul)).
	- *la couche d'output* qui est le résultat des couches précédentes en fonction d'une input.


__**Cours 3:**__

Les shapes:
![[main/Images et liens/Pasted image 20221104230004.png]]

Code:
Calcule de 4 inputs à travers un neurone:

![[main/Images et liens/Pasted image 20221104214758.png]]

Calcule de 4 inputs à travers 3 neurones:
**Attention**: Appart pour un réseau d'un seul neurone, où les poids et les inputs sont donc des vecteurs, il faut toujours mette les poids(weights) en premier dans le np.dot() (comme ceci: output = np.dot(weights, inputs) + biases) car avec plusieurs neurones, la liste des weights devient une matrice et donc le calcul ne marche pas dans les deux senses.

![[main/Images et liens/Pasted image 20221104221540.png]]
Output:

![[main/Images et liens/Pasted image 20221104221745.png]]


**Cours 4:**

pour optimiser les calculs, à la place de calculer un ensemble d'inputs sous forme de sample exemples: inputs = [1, 2, 3, 2.5]
								   ...
								   np.dot(weights, inputs) + biases
								   puis recommencer avec de nouvelles inputs pour affiner le calcul.
Nous allons regrouper toutes les inputs en différents lots d'inputs(lots = 
batches en anglais):

