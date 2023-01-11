# Semaine 2 - Découverte de la récurrence et présentation du projet

Dans cette session, nous avons découvert ensemble le principe de la **récurrence**.

Une fonction par récurrence est une fonction qui se définit par des appels de cette même fonction pour des indices inférieurs.

> Bon, ça c'est du jargon mathématique, on va donner un exemple pour expliquer

Prenons par exemple la fonction mathématique **factorielle** :

factorielle(x) va être égale à x * (x-1) * (x-2) * ... * 2 * 1

Exemple : `factorielle(4) = 4 * 3 * 2 * 1`

On peut écrire cet exemple également `factorielle(4) = 4 * factorielle(3)` et c'est là le coeur de la fonction récursive.

## Les deux fondamentaux d'une récurrence

- La fonction doit faire référence à elle même et diminuer son indice
- La fonction doit comporter une **condition d'arrêt**, c'est-à-dire un "moment" où la fonction ne se rappellera pas.

Par exemple, une convention mathématique nous dit que `factorielle(0) = 1`. Donc, il existe une condition d'arrêt à 0.

Nous pouvons donc, en Python, définir la fonction comme ceci :

```py
def factorielle(n):
  if n == 0:                      #notre condition d'arrêt
    return 1
  else:
    return n * factorielle(n-1)   #on refait bien appel à factorielle() avec un n inférieur.
```

## Un exemple sur Turtle ?

Nous allons utiliser la récurrence pour dessiner une triforce composée de triforces !

Commençons par reprendre notre fonction triangle :
```py
import turtle as t
t.speed(0)

def triangle(taille, couleur):
    t.fillcolor(couleur)
    t.pendown()
    t.begin_fill()
    for i in range(3):
        t.forward(taille)
        t.left(120)
    t.end_fill()
    t.penup()
```

À partir de là, nous allons définir une fonction `triforce` :
- Dessiner un triangle
- Se déplacer jusqu'au prochain emplacement
- Dessiner le deuxième triangle
- Se déplacer
- Dessiner le dernier triangle
- Revenir au point de départ

Une fois fini, nous remplaçons les fonctions `triangle()` par des fonctions `triforce()` !
- On ajoute notre condition d'arrêt (une triforce 0 renverra un simple triangle)
- On fait varier les valeurs dans `triforce()`, donc `n` et `taille` pour que les déplacements et les tailles se baissent correctement !

```py
def triforce(n, taille, couleur="red"):
  if n == 0:
    triangle(taille*2, couleur)
    
  else:
    triforce(n-1, taille/2, couleur)
    t.forward(taille)
    triforce(n-1, taille/2, couleur)
    t.left(120)
    t.forward(taille)
    t.right(120)
    triforce(n-1, taille/2, couleur)
    t.right(120)
    t.forward(taille)
    t.left(120)
```

Le résultat final pour `triforce(1,100)`

<img width="309" alt="image" src="https://user-images.githubusercontent.com/91781579/211888049-6a6bd851-053b-4922-8ddb-b8e086561479.png">


Le résultat final pour `triforce(4,100)`

<img width="276" alt="image" src="https://user-images.githubusercontent.com/91781579/211887903-78511797-31ff-4aa1-9377-f0d6e18f19eb.png">

Nous avons rendu nos triangles **récursifs** !

# Le Projet

À cette session, j'ai présenté le premier projet du semestre : La création d'un arbre par récurrence !

Par observation, déduction et compréhension du code des triforces, il faut tenter de construire cet arbre.

> En bonus, si le projet avance vite par rapport aux autres, il est possible de tenter de faire varier l'épaisseur du trait et sa couleur, pour une meilleure esthétique

<img width="616" alt="Arbre Récursif" src="https://user-images.githubusercontent.com/91781579/211886594-f7ecdd4a-4bef-4501-a2bb-daca24f25cf2.png">
