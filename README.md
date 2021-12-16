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


for (type var in array){

}

array.forEach(() => )
array.map(() => ) (Résultat: Nouvelle liste)
 
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

## Liste
List<< type >> < nom > = [val, val, val] ou var list2 = List.filled(50, hello) => Créer une liste de 50 hello
list[ index ]
list.sublist(2,5) //Partie de la liste
  .first
  .last
  .length
  .add
  .removeLast
  .insert

Liste peuvent utiliser le spread syntax:
var combined = [...liste1, ...liste2]

Ou utiliser l'ajout conditionnel à la liste:
var i = [ i1, i2, i3, if(i3) i4]


## Map (Dictionnaire)
Map< keyType, valueType > var = {
  key: value
}
var['key']
var.values
var.values.toList()
for x in xs.entries
forEach((key, value))


## Classes
Blueprint d'un élément

### Créer une classe
class NomAvecMajusculeAuDébut {
  variables

  méthodes (fonctions)

  fonction statique: statif nom(){}
  Permet d'appeler une fonction sur la classe et non pas spécifiquement sur une instance
}

### Initialisation
NomAvecMajusculeAuDébut var = new* NomAvecMajusculeAuDébut()
*facultatif

var.i1

## Constructeur
Permet d'initialiser une instance
Dans la classe:

final int var1
final int var2
late finale inte var3

NomAvecMajusculeAuDébut(this.var1, this.var2, [var optionnel]){
  var3 = var1 + var2
}

Si Variable avec nom, par défaut optionnel. Ajouter required 

Possibilités de créer plusieurs constructeurs:
NomAvecMajusculeAuDébut.MéthodeConstructeur(var){}
NomAvecMajusculeAuDébut.AutreConstructeur(var,var){}

## Interfaces
Ce que voit les autres développeurs dans Intellisense
De base, tout est montré, mais, on peut cacher les éléments qui ne doivent pas être touché par le programmeur.

Caché: Constructeurs, _var, _method

abstract: interface seulement

## Extend
Étendre les fonctionnalités d'une clase en créant une autre classe. 

Utilisation: class Classe2 extends Classe1
Classe 2 hérite de tout Classe1
On peut ensuite ajouter autres choses, ou override en:

@override
void FonctionAOverride(){} //Remplace


@override
void FonctionAOverride(){
  super.FonctionAOverride(); //importer le code de la classe parente.
}

## Mixin
Une sorte de classe qui ne peut pas être instanciée. C'est un comportement qu'on ajoute.

mixin Nom{
  code
}

Peut être ajouté à Superclasse:
class Classe2 extends Classe1 with Mixin1, Mixin2{}

## Generics
Les génériques permettent de définir le type des paramètres

class Nom<type>{
  type value;
}

Substitut de paramètre précis

## Packages
import 'somewhere.dart'
import 'somewhere.dart' hide class --> Caché une classe pour éviter les collisions
import 'somewhere.dart' show class --> Afficher une clase seulement pour éviter les collisions
import 'somewhere.dart' as External; --> Namespaced pour éviter collision

## Async
Pour travailler avec Async, importer 'dart:async'
### Futures (Promises)
Fonctions async non blocantes
One time event
var d = Future.delayed(Duration(seconds: 5))

d.then(() => );
 .catchError();

 On peut utiliser aussi async/await.

 Future<String> nom() async{
   var d = await Future.value('World') --> Attend que cela soit résolu
 }

 ### Stream
 Plusieurs async (Timeline d'async)
 
 var s = Stream.fromIterable([1,2,3])
 s.listen((e)=>)

 Une liste qui évolue dans le temps. 

 Possible d'utiliser: .map, .listen
Peut être écouter seulement une fois, sauf si
 var s = Stream.fromIterable([1,2,3]).asBroadcastStream

 Fonctionne avec Async/Await avec For in (for(int value in stream){})