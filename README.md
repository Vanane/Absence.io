# Absence.io

Acteurs: 
	Manager
	DRH
	Salarié

Workflows de saisie de demande d'abs
1) Saisie d'une demande absence par le salarié ->(statut wf 'SAISIE')
	2) salarié valide sa saisie -> (statut wf 'CTRL')
		3) Validation de la demande par le Manager (statut wf'VALID_MAN')
		4) Refus de la demande par le Manager -> (statut wf 'REFUS_MAN')
			5) Si  type_absence <> 'CONGE' alors 
				6) Validation par le DRH -> statut (statut wf 'VALID_RH')
				7) Refus par le DRH -> statut (statut wf 'REFUS_RH')
		3 bis) OU validation le DRH -> statut (statut wf 'VALID_RH')
		4 bis) Refus par le DRH -> statut (statut wf 'REFUS_RH')
					8) Modification d'une demande refuser ou valider par le salarié (statut wf 'SAISIE')...

champs d'une absence : 
  	type d'absence(CONGE, FAMILLE, PARENT...)
 	statut de l'absence (pas sure) 
	commentaire (txt) 
	Date début (date)
	Date fin (date) 