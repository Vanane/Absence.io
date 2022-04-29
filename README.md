# Absence.io

## Acteurs

- Manager
- DRH
- Salarié

### Membres

- Bronce Bwayne (Batman/Batman), Salarié
- Imbiamba Jombes (Jombes/Jombes), Salarié
- Jone Bwick (Bwick/Bwick), Manager de Jombes et Bwayne
- Jean-Michel Gratos (Gratos/Gratos), DRH

## Workflows de saisie de demande d'absence

### Débuts

1. Un salarié crée une fiche d'absence, en donnant les dates de début et de fin, et le type de congé.

### Cas nominal

2. Si le salarié a un manager, et si le manager n'est pas absent lui-même, alors le manager du salarié traite la demande.
3. Le manager accepte la demande.
4. Dans le cas d'une absence de type Congé, la demande est ensuite transmise au DRH.
5. Le DRH accepte la demande, après vérification de la quantité de congés du salarié.
6. La demande est validée et le processus est terminé.

### Fins alternatives

7. Si l'absence n'est pas traitée à temps, elle est automatiquement refusée et le processus est clos.
	La date limite de traitement d'une demande est le jour avant le début de l'absence.
8. Si le manager ou le DRH refusent la demande, celle-ci est refusée et le processus est clos.

## Amélioration possible

- Envoyer un mail pour prévenir le statut d'une absence aux salariés concernés.
- Pour les dates d'absence : proposer deux crénaux pour les absences de demi-journées.
- Ajouter un contrôle sur les dates de début et de fin, le début ne peut pas être après la fin.
- Ajouter un contrôle sur la date de début, le début ne peut pas être avant aujourd'hui.

## Données métier

### Fiche d'absence



 - | Nom            | Type   | Obligatoire/Multiple | Valeurs possibles                                            |
	| -------------- | ------ | -------------------- | ------------------------------------------------------------ |
	| dateDebut      | Date   | Obligatoire          | Date                                                         |
	| dateFin        | Date   | Obligatoire          | Date                                                         |
	| idSalarie      | String | Obligatoire          | Login d'un salarié                                           |
	| typeAbsence    | String | Obligatoire          | Enum : Congé, Décès, Mariage, RTT, Parental, Examen, Alternance, Formation, Maladie |
	| etatTraitement | String | Obligatoire          | Enum : SAISIE, CTRL, VALID_MAN, VALID_DRH, REFUS_MAN, REFUS_DRH, REFUS_TIMEOUT |
	| commentaire    | String | -                    | Texte                                                        |
	| idManager      | String | Obligatoire          | Login d'un salarié manager                                   |

