# Aide-mémoire protection

## Intrants

 - Numéro complet du relais de protection, incluant toutes les options;
 - Schémas logiques de protection;
 - Réglages des éléments de protection (TCC ou tableaux);
 - Manuel d’utilisation du relais.

## Philosophie

 - En industrie régler la 51 d'un transformateur entre 100% et 120% de la capacité maximale;
 - En distribution régler la 51 d'un transformateur à au moins 150% de la capacité maximale, si la pointe est hivernale;
 - Régler la 50 au primaire d'un transformateur à 120% du courant maximal secondaire;
 - Régler la 50 à moins de 80% du courant minimal, mais tenir compte de la magnétisation des transformateurs;
 - Si approprié, régler la 50N à 20% du courant ph-t (dépend de coordination et autres contraintes).

## Erreurs courantes

 - J’oublie souvent de m’assurer que les éléments de protection sont associés à une sortie relais pour le déclenchement du disjoncteur. C’est particulièrement vrai pour les relais MiCOM pour lesquels on doit faire l’association dans le fichier PSL et non dans le fichier de paramètres;
 - Le Code Électrique nous oblige d’avoir une protection de neutre lorsque le défaut dépasse 1200A;
 - Toujours consulter le guide de paramétrage des relais. D’un relais à l’autre il y a souvent des subtilités, par exemple un paramètre multiplié par 2;
 - Synchronisation du temps, en heure locale ou en UTC?
 - Considérer le ratio de transformation, incluant les prises hors-charges. Un ratio plus élevé que le nominal augmente le courant secondaire par rapport au courant primaire, et décale donc une courbe au secondaire d'un transformateur vers la droite sur la TCC (par rapport aux courbes au secondaire du même transformateur);
 - Également considérer la tension d'opération du réseau.

### 2016-10-18 - Courant homopolaire

J'ai dit dans une note que le courant de défaut phase-terre était principalement homopolaire. En fait dans un défaut phase-terre le I1 = I2 = I0, et le défaut phase-terre = 3*I0. Donc c'était pas tout-à-fait exact.

J'aurais dû le formuler différemment, et finalement j'ai seulement dit que le défaut est phase-terre.

#### 2016-10-28 - Suivi suite à un autre événement à MU

Donc pour un défaut phase-terre sur un réseau :

 - Au point de défaut : I1 = I2 = I0, If = I1 + I2 + I3 = 3*I0
 - Aux sources homopolaires (ex.: transformateur de MALT) : IA = IB = IC = I0, I1 = I2 = 0
 - Aux sources non-homopolaires (ex.: transformateur delta) : I1 = I2, I0 = 0, et les phases dépendent de la phase en faute.

De plus des transformateurs de courant raccordés en delta ne verront pas de I0. Donc si on a un transformateur de MALT avec des TC en delta, on ne devrait jamais voir de courant sur les TC sauf si le défaut est interne, puisque le courant homopolaire est piégé dans l'enroulement delta.

### 2016-10-20 - Protection transformateur de MALT

Pour le parc éolien MU j'ai fait une erreur le 20 octobre 2016 en spécifiant une protection de neutre (51N) avec une mise au travail à ~100% du courant nominal du transformteur de MALT. À 2,6 MVA et 34,5 kV, le courant nominal est 43,5 A. Par contre c'est 43,5 A par phase, donc la 51 pourrait être ajustée à ce courant mais la 51N devrait être au triple de ce courant, donc 130,5 A.

C'est sûr qu'avec un défaut phase-terre le 3*I0 peut passer entièrement dans une patte, mais c'est la 51 qui devrait opérer dans ce cas pour protéger une bobine et non le 51N. Ce serait différent pour une résistance de MALT, où on doit vraiment protéger sur le 3*I0 (51N) puisqu'on a une seule branche.
