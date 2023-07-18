***
sh
git init
"cette commande va intialiser un depot Git, Git va traquer toutes les modifications effectuées au sein de ce dossier. "

***
Création de dépot 

Pour consulter l'état du dépot Git om suffit de lancer la commande :
***sh
git status
***

Pour sauvegarder il faut se placer a la racine et taper la commande :
*** sh
git commit -m "first commit"
***
Pour ajouter des fichiers non-suivis :
***bash
git add .
***


git add . 
git commit -m "first commit"

présentation géneral de Merise:
cette methode se caracterise par trois points clés :
- un approche dit systématique : on transforme les processus de l'entreprise en SI
- une séparation  des données et des traitements 
- une approche nivelée

### L'approche systématique

-le système de pilotage : 
Il est composer de l'ensemble des acteurs qui vont 'piloter' le système d'information 
-le système d'information : 
Il est composer de l'ensemble des acteurs qui vont 'utiliser' le système d'information
-le système opérant : 
Il est composer de l'ensemble des acteurs qui vont 'produire' les donnees du systeme d'information

![alt text](image.png)

### La separation des donnees et des traitements

La separation des donnees et des traitements permet de separer les donnees du système d'infomation et les traitements effectues sur donnees.
Cette demarche se fait en 3 etapes : 
-L'analyse des flux : on analyse les flux d'informations entre les acteurs du systeme d'information et les acteurs du systèmes operant
-L'étude des documents interne (factures, bon de livraison)
-L'etude des documents en externes (fournisseurs, clients), 

les differents types d'informations : 
- les infos de bases ou elementaires : ce sont les donnees de base du systeme d'informations 
-les informations calculees : ce sont les donnees calculees a partir des donnees de base
- les traitements ou les fonctions : ce sont les traitements effectue sur les donnees de base pour obtenir les donnees calculees 

En resume : vous devrez identifiees les donnees et les traitement effectue sur ces donnees 

### L'approche nivelée 

Pour effectuer la conception d'un SI, on va utiliser une approche nivelée. Cette approche se compose de 4 niveaux : 

-Le niveau conceptuel
-le niveau organisationnel
-le niveau logique
-le niveau physique

#### le niveau conceptuel

Le niveau conceptuel permet de modéliser les données de l'entreprise.
On va utiliser le modèle conceptuel de données (MCD) pour modéliser les données de l'entreprise, et le MCT pour modéliser les traitements effectué
sur ces données.

#### Le niveau organisationnel 

Le niveau organisationnel va permettre d'intégrer a l'analyse précedente toutes les notions de temporalité, de chronologie des opérations, de  contraintes géographique, des niveaud d'accès. On va utiliser le modele organisationnel des traitements et le modele organisationnel des traitement (MOT) et le modéle organisationnel des données (MOD) pour modéliser les traitements de l'entreprise.

En résumer on se pose les questions suivantes a partir des données recueillis au niveau conceptuel :

-**quand** les traintements sont-ils effectués ? 
-**Où** les traitements sont-ils effectués ?<br>
-Par **Qui* les traitements sont-ils effectués ?

#### Le niveau  logique

Le niveau logique va permettre de modéliser les données de l'entreprise en utilisant le modèle logique de données (MLD) et les traitement de l'entreprise en utilisant le modèle logique des traitements (MLT)

Le MLD est independant des languages de programmations et SGBD(Systeme de Gestion de Base de Données).

On repond a la question : **Avec Quoi** les traitements sont-ils effectues ?

#### Le niveau physique

Il s'agit de l'organisation `réelle` des données. on va utiliser le modèle physique de données (MPD) et le modèle physique des traitements (MPT).

Ici, on apporte les solutions technique de stockage des données et de traitement des données.

On reponds a la question : **Comment** les traitements sont-ils effectués ?

#### Résumé : les 4 niveau de Merise 

![Alt text](image-1.png)

### Des données aux dépendances fonctionnelles

Pour être intégrées dans un SI, les données doivent être triées et organisées. On va souvent tenter de les classer par type de données :

- Chaine de caratctères, format texte
- Type alphanumérique, format texte
- Le type numérique (intégrer, float)
- Le type date (date, datetime, timestamp)
- Le logique ou booleen (true, false)

Creation d'un dictionnaire de donnees 

![Alt text](image-2.png)

### Les dépendances fonctionnelles 

Une dépendance fonctionnelle est une relation entre deux attributs d'une table. Elle permet de définir une relation de dépendance entre deux attributs d'une table.

![Alt text](image-14.png) 
![Alt text](image-5.png)
![Alt text](image-6.png)
![Alt text](image-7.png)
![Alt text](image-3.png)


Le but de l'exercice est d'elaborer un MCD a partir d'un dictionnaire de donnees.

Ici on va introduire les notions d'entités, de relation et de propriétés.

#### Les propriétes sont les informations de base d'un SI.


#### Les entités sont les objets du SI.

![Alt text](image-8.png)

Quelques définitions :
    - entité forte : une entité qui ne dépend pas d'une autre entité pour exister
    - entité faible : une entité qui dépend d'une autre entité pour exister

#### Les relations

![Alt text](image-9.png)

**Les cardinalités** : Elle permettent de définir le bombre d'occurences d'une entité par rapport à une autre entité dans le cadre d'une relation.

![Alt text](image-10.png)

Petit Exemple : 

![Alt text](image-11.png)

![Alt text](image-12.png)

![Alt text](image-13.png)

#### Les relations "porteuse"

Une relation est dite porteuse si elle possede des proprietes.

#### Les relations reflexives

Une relation est dite reflexive si elle relie une entite a elle meme.


Quelques regle de conception : 

- toute entite doit avoir un identifiant
-toutes les propriéter dependant fonctionnellement de l'identifiant
-le nom d'une propriete ne doit  apparaitre qu'une fois dans le MCD : si vous avez une entite Eleve et une entite Professeur, vous ne pouvez pas avoir une proprieté nom dans les deux entités. Il faut donc renommer la propriéter nom de l'entite Professeur en nomProfesseur par exemple.
-les proprietes issues d'un calcul ne doivent pas apparaitre dans le MCD.

Le rôle d'une dependance fonctionnelle est de permettre de definir une relation de dependance entre deux attribut d'une table : une donnée A depend fonctionellement d'une donnée B lorsque la valeur de B determine la valeur de A.

Pour formaliser une dépendance fonctionnelle on utilise la notation suivante: 
Numéro adhérant `(Nom, Prénom, CP, Ville, Téléphone, Date d'adhésion,  mail)`

La partie gauche (numéro adhérant) est la `source` de la dépendance fonctionnelle.
La partie droite désigne le `but` de la dépendance.

#### Les dépendance fonctionnelles composées

Si une dépendance fonctionnelle qui fait intervenir plus de deux attributs on parle de dépendance fonctionelle composée.

Exemple : Pour connaître le temps d'un coureur sur une etape donnée il nous faut son numéro ou son nom ainsi que le nom ou le numéro de l'étape.

Formalisation :
`(numéro coureur, numéro étape)   (temps)`

#### Les dépendances fonctionnelles élémentaires

Une dépendance fonctionnelle A -> B est élémentaire s'il n'existe pas une donnée C, sous-ensemble de A, décrivant une dépendance fonctionnelle C -> B

Exemples :
- RefProduit -> LibelleProduit
- NumCommande RefProduit -> QuantiteCommande
- <strike> NumCommande RefProduit -> DésignationProduit </strike>

#### Dependance fonctionnelle elementaire directe
"On dit que la dépendance fonctionnelle A -> B est directe s'il n'exite aucun attribut C tel que l'on puisse avoir A -> C et C -> B.
En d'autres termes, cela signifie que la dépendance fonctionnelle entre A et B ne peut pas être obtenue par transitivité."

Exemple : 
- RefPromo -> NumApprenant
- NumApprenant -> NomApprenant
- RefPromo -> NomApprenant : RefPromo -> NumApprenant -> NomApprenant

#### Les contraintes d'integrité fonctionnelles (CIF)

Définition : Une CIF est définie par le fait qu'une des entites de l'association est completement determinee par la connaissance d'une ou de plusieurs entites participant a l'association.

Exemple : 

![Alt text](image-18.png)

Une salle peut contenir 0 ou plusieurs ordinateurs. Un ordinateur existe dans une et une seule salle.
Dans ce type de relation une CIF existe si on a une cardinalite 1,1


