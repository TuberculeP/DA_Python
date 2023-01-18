# Quelques Exemples

Cette semaine, nous avons pris le temps d'avancer sur le projet, nous avons vu pour rappels deux nouveaux exemples de fonctions par récurrence :

## Le flocon

|Code|
|-|
```py 
def segment(taille, n):
    if n == 0:
        t.forward(taille)
    else:
        segment(taille/3,n-1)
        t.left(60)
        segment(taille/3,n-1)
        t.right(120)
        segment(taille/3,n-1)
        t.left(60)
        segment(taille/3,n-1)
```

|Explications|
|-|

Pour construire le flocon :

- Cas de base : un simple segment de taille `taille`

![image](https://user-images.githubusercontent.com/91781579/213266863-1bd2fd2c-5c0b-4e7b-9147-6164d85ee129.png)


- Cas 1 : construire un segment "fragmenté" avec des forward(taille/3) et des rotations

![image](https://user-images.githubusercontent.com/91781579/213267029-38229c6f-e890-45c2-b894-05cf01ca4156.png)

- Pour généraliser à n : remplacer les forward(taille/3) par des segment(taille/3, n-1)

![image](https://user-images.githubusercontent.com/91781579/213267254-31a39e4b-7dd3-4f46-970d-ffb16177e733.png)

> Ce cas 2 est formé de cas 1 qui eux-mêmes sont formés de cas 0


Maintenant il ne nous reste plus qu'à faire une fonction flocon(taille, n) qui est composée de 3 segments !

```py
def flocon(taille, n):    
    for i in range(3):
        segment(taille, n)
        t.right(120)
        
```

![image](https://user-images.githubusercontent.com/91781579/213268943-d0eda36a-4ab2-4b6e-81ca-2c0941fb96e3.png)

## Les Triangles Bizarres

Exemple plus rapide, nous partons d'un cas 0 qui est un simple triangle :

```py
def triangleBizarre(taille, n)
if n == 0:
        for i in range(3):
            t.forward(taille)
            t.right(120)
```
![image](https://user-images.githubusercontent.com/91781579/213269322-e6dea172-517d-44c3-b371-58ba0dd12424.png)

Ensuite, pour les cas 1 et +, nous avancerons avec des forward(taille/2) et construirons nos triangles sur le chemin, petit à petit :

```py
else:
        for i in range(3):
            t.forward(taille/2)
            t.left(120)
            triangleBizarre(taille/2, n-1)
            t.right(120)
            t.forward(taille/2)
            t.right(120)
```
![image](https://user-images.githubusercontent.com/91781579/213269583-ea238c28-d4c8-4f1a-8d06-bd01fd577727.png)

Etant donné que nous dessinons les triangles en nous servant de la fonction elle-même, les autres cas se font automatiquement !

![image](https://user-images.githubusercontent.com/91781579/213269809-78e2d821-47b8-46fe-999d-07e0f42d9924.png)
