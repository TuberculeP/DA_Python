## Semaine 1

Nous avons mis en place Spyder 5 (https://www.spyder-ide.org/) pour développer durant le semestre plus simplement que sur VS Code.

Points vus ou revus :
- importer correctement un module
- déclarer et appeler une fonction (ici la fonction triangle)
- la notion de boucle

Premiers pas avec Turtle  :
- (ré)initialiser la fenêtre d'exécution (reset)
- lever ou poser le crayon (penup, pendown)
- avancer (forward) et pivoter (left,right)
- remplir une forme

Le programme suivant dessine une "triforce", trois triangles empilés.


```py
import turtle as t

t.reset()

def triangle(taille, couleur):
    t.fillcolor(couleur)
    t.pendown()
    t.begin_fill()
    for i in range(3):
        t.forward(taille)
        t.left(120)
    t.end_fill()
    t.penup()
    

triangle(100, "blue")
t.right(120)
triangle(100, "blue")
t.left(60)
t.forward(100)
t.left(60)
triangle(100, "blue")
```
