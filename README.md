# Algorithme snake
L’objectif est d’utiliser l’algorithme des snakes comme une alternative plus pertinente au calcul du gradient d’une image pour le d´etourage d’un objet.

# Explication de l'algorithme

On dispose d'une image dont on souhaite contourer l'objet. Ici, on prend l'exemple d'une goutte :

![Image](im_goutte.png)

On définit ainsi notre snake \( c \) comme une liste contenant les coordonnées de tous les points du contour :
c(s) = | x(s) |
       | y(s) |,  s ∈ [0, 1]

La courbe \( c \) est donc une courbe lisse et fermée et on l'initialise de sorte que se soit un cercle. Cette courbe prend en paramètre un réel entre 0 et 1 (abscisse curviligne). Étant fermée, on a évidemment \( c(0) = c(1) \).

On réalise deux hypothèses sur \( c \) :
- \( c \) est une courbe lisse
- \( c \) se place sur les contours de la forme

On obtient apres l'initialisation la figure suivante :

![Image](Figure_goutte.png)

Maintenant nous devons resoudre l'equation suivante ( voir pourquoi dans le compte rendu ) : 
`α/2 * ||c'(s)||^2 + β/2 * ||c''(s)||^2 - γ * ||∇||`

C’est l’´equation `a r´esoudre de sorte que c’est le contour qui minimise E. Cependant cette ´equation
diff´erentielle est difficile `a r´esoudre `a cause du dernier membre. C’est pour cela qu’on a impl´ementer
dans ce TP le sch´ema it´eratif de convergence.

