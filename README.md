# Dart
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