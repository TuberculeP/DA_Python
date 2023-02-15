# Projet Baston

> Le but du projet sera d'observer un combat entre un chevalier et des monstres grâce à des prints dans la console.

## L'énoncé

Jean est un chevalier qui possède 10pv et une armure au début du jeu
Il va affronter les ennemis en boucle jusqu’à la mort

Les ennemis possèdent 3pv et un pourcentage d’armure et d’attaque :
    le pourcentage d'armure signifie que Jean a [pourcentage] de chance de toucher l'ennemi
    le pourcentage d'attaque signifie que l'ennemi a [pourcentage] de chance de toucher Jean
    ces deux statistiques sont égales (10% initialement)
    le pourcentage augmente de 5% chaque fois que l'ennemi survit à un tour

L'armure de Jean a 30% de chance de se casser lors d'un coup de l'ennemi 
on considère que le coup qui brise l'armure n'inflige pas de dégâts supplémentaires.

Si Jean possède une armure, son arme a 70% de toucher l'ennemi, sinon, 50% seulement.
Jean et l'ennemi infligent 1pv de dégât

### Chaque classe créée sera séparée dans un fichier dédié et importé dans le main.py
