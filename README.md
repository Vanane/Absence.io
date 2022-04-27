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

* 1) Saisie d'une demande absence par le salarié ->(statut wf 'SAISIE')
* 2) salarié valide sa saisie -> (statut wf 'CTRL')
* Choix par le manager :
	* 3) Validation de la demande par le Manager (statut wf'VALID_MAN')
	* 4) Refus de la demande par le Manager -> (statut wf 'REFUS_MAN')
	* 5) Si  type_absence <> 'CONGE' alors (sinon directement au dernier point):
		* 6) Validation par le DRH -> statut (statut wf 'VALID_RH')
		* 7) Refus par le DRH -> statut (statut wf 'REFUS_RH')
* Choix par le RH :
	* 3. bis) OU validation le DRH -> statut (statut wf 'VALID_RH')
	* 4. bis) Refus par le DRH -> statut (statut wf 'REFUS_RH')
* 8) Modification d'une demande refuser ou valider par le salarié (statut wf 'SAISIE')...

## Amélioration possible

- Timer entre chaque action (si pas d'action avant la date de début de l'absence alors non valide...)

## champs d'une absence : 

 - type d'absence (CONGE, FAMILLE, PARENT... LST_DEROULANTE)
 - statut de l'absence (pas sure) 
 - commentaire (VARCHAR2) 
 - Date début (DATE)
 - Date fin (DATE) 



## TODO

- Pour les dates d'absences : proposer deux créneaux pour les absences de demi-journées

