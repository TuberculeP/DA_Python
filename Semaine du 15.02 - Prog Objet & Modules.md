# Programmation Objet sur Python

Nous découvrons aujourd’hui la programmation orientée objet sur Python, avec les Objets, les Classes, les Attributs et les Méthodes.

# Un objet ?

```python
class Verre:
  def __init__(self):
    return

monVerre = Verre() # monVerre est un objet Verre !
```

Un objet est une structure de données, exactement comme String, Int, Dict…

Tous ses paramètres seront rangés dans une `class` comportant un nom.

# Les méthodes

Une méthode est une fonction rattachée à un objet.

```python
test = "bonjour"  # test est un objet String
test.capitalize() # .capitalize() est une méthode de String
```

### Les méthodes par défaut

Il existe beaucoup de méthodes par défaut pour une classe, en voici deux :

- `__init__()` OBLIGATOIRE : Permet d’initialiser une instance de l’objet (voir exemple du verre en haut)
- `__str__()` : Est appelée lorsqu’on utilise l’objet dans un contexte textuel. Exemple :

```python
class Verre:
  def __init__(self):
    return
  def __str__(self):
    return "Je suis un verre"

monVerre = Verre()
print(monVerre) # Console => "Je suis un verre"
```

### Les méthodes personnalisées

Il est bien sûr possible de créer ses propres méthodes dans sa classe :

```python
class Verre:
  def __init__(self):
    return
  def renvoieCinq(self):
    return 5
  def renvoieQuelqueChose(self, un_truc):
    return un_truc

monVerre = Verre()
print(monVerre.renvoieCinq()) # Console => 5
print(monVerre.renvoieQuelqueChose("Bonjour")) # Console => "Bonjour"
```

# Les Attributs

De la même manière qu’une méthode, il est possible de stocker de simples variables dans une instance de classe, elle sera appelée attribut.

```python
class Verre:
  def __init__(self):
    self.estRempli = False

monVerre = Verre()

print(monVerre.estRempli) # Console => False
```

## Paramètre et interaction

Pour toute méthode, on peut appliquer des paramètres supplémentaires afin d’agir sur notre objet

```python
class Verre:
  def __init__(self, remplissage): # on ajoute la possibilité de décider du remplissage
    self.estRempli = remplissage

  def remplis(self):
    self.estRempli = True
  def vide(self):
    self.estRempli = False
	def setRemplissage(self, remplissage):
		self.estRempli = remplissage

monVerre = Verre(False)
print(monVerre.estRempli) # Console => False
monVerre.remplis()
print(monVerre.estRempli) # Console => True
monVerre.vide()
print(monVerre.estRempli) # Console => False
monVerre.setRemplissage(True)
print(monVerre.estRempli) # Console => True
```

# En complément : Découverte des modules

Avec Python, il est possible (voire recommandé pour une meilleure lisibilité) de séparer son code dans plusieurs fichiers.

Par exemple, je peux avoir un dossier `Projets\` qui contient deux fichier `main.py` et `verre.py`

Je peux séparer le code en faisant :

```python
# Dans verre.py :
class Verre:
  def __init__(self, remplissage): # on ajoute la possibilité de décider du remplissage
    self.estRempli = remplissage

  def remplis(self):
    self.estRempli = True
  def vide(self):
    self.estRempli = False
	def setRemplissage(self, remplissage):
		self.estRempli = remplissage
```

```py
# Dans main.py :

from verre import Verre # du fichier verre.py on importe la classe Verre

monVerre = Verre()
```
