# Dart (Notes)
## Variables
'type :var = :val
int, Double, String... Type
Dynamic type --> Var
Constantes --> final 'type :var ou const :var
### Vérifier le type
:var is type --> bool
var.runtimeType --> string
### Interpolation dans les string
Inscrire $var permet d'afficher la valeur dans un string; ex: print('Bonjour $varNom et tu as ${varAge + 2}')
## Null safety
Variable ne peut pas être nulle par défaut
Pour le faire, il faut ajouter ? après le type:
ex:. int? age;

Puis, pour assigner une variable null à une autre variable, il faut utiliser le ! après la première. Ex:. String result = answer! (Assertion operator)

Avec final, on peut attendre la valeur en ajoutant late devant final

= À éviter

## Control Flow
### Conditions
if (condition) {} 
else if (condition) {} 
else {}

Vérifier Null => isEmpty

### Boucles
 for ( < initialisation >;  < condition >;  < incrementation >) {
    < code >
  }

  < initialisation >
  while (< condition >) {
    < code >
    < incrementation >
  }

  < initialisation >
  do {
    < code >
  } while (< condition>);

Possible également de break ou continue

### Assert (Seulement en développement)
Vérifie une condition, lève erreur si le retour est faux.

EX.:   var a = q; assert(a != 2);

## Operateurs
### Base
Arithmétique: + - * / 
Logique: == < > <= >= != && || ++ --

### Avanced
??= -> Assigner une valeur seulement si nulle
< condition > ? valeur vrai : valeur faux -> Ternaire
.. -> Cascade
as -> "Convertir" une variable 

## Fonctions
Fonctions = objets

### Définir une fonction
< nomDeLaFonction > (< params1 > ou { nomParams = < default > }  >){} 
ou
< type > < nomDeLaFonction > (){}
ou
< nomDeLaFonction() > => code

nomDeLaFonction(x) ou nomDeLaFonction(nomParams: < valeur >)