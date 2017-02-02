# Transport maritime

Avec la récente découverte de l'amérique, le transport de personnes sur les océans semble être un business qu'il ne faut en aucun cas laisser passer.
Manque de chance, vous n'avez pas de bateaux..... vous décidez donc de monter une startup qui fournira un service pour interfacer les usagers et les navigateurs. 


# MVP

Votre MVP ne concernera que le devis, ce qui sera déjà pas mal pour l'époque.

## format d'entrée
Votre interface devra accepter le format suivant: 
```javascript
{
  "nbjours":int,
  "ages":int[],
  "options":String[], 
  "DateDepart":"1540-11-15",
  "DateRetour":"1540-12-09",
  "Pays":String,
  "navire":String
}
```

## Calcul de base

Un trajet pour une personne se calcule ainsi:
(nombre de jours * coût journalier) + Options 


## Coût journalier
Le coût journalier dépend du type de bateaux: 
- Caravelle : 1,3 Ducat journalier
- Galion : 1 Ducat journalier 
- Caraque : 1,1 Ducat journalier 

C'est le prix pour un adulte.

Les enfants et les seniors payent 120% du prix journalier, car il y a plus de risques de tomber malade.

Les jeunes bénéficient d'une ristourne et ne payent que 90% du prix.


## Options
Il est possible de cumuler plusieurs options:
- régime alimentaire anti-scorbut: 0.8 Ducats par jours par passagers (0.5 pour les enfants)
- lessives : 1 Ducat par semaine entammée
- cabine particulière : 5 Ducats par jours [2 passagers maximums autorisés, sinon le devis est refusé]
- 2 repas par jours : 0.5 Ducats par jours par passagers
- eau douce : 0.6 Ducat par jours par passagers
- Matelot : cf cas spécial

## Cas spécial : Matelot
Il est possible de demander à profiter du trajet en tant que Matelot.

Ce type de devis ne peut contenir qu'une seule personne et aucune autre option (sous peine d'être rejeté).

Le trajet est alors gratuit, et le matelot gagne 1 Ducat/semaine compléte (on renvoit donc une somme négative)


## Age légal
Suivant les pays, l'âge qui définit la frontière entre les typologie de paxx change:

- France: enfant < 16 <= jeune < 26 <= adulte < 60 <= senior
- Espagne: enfant < 14 <= jeune < 28 <= adulte < 50 <= senior
- Portugal: enfant < 12 <= jeune < 22 <= adulte < 55 <= senior
- Angleterre: enfant < 17 <= jeune < 26 <= adulte < 45 <= senior
