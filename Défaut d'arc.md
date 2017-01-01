# Aide-mémoire - Défaut d'arc

## Normes

- ANSI/NFPA, *NFPA 70E – Standard for electrical safety in the workplace, 2015 Edition*, 2014-07-29
- CSA Group, *CSA Z462-15 – Workplace electrical safety,* 2015-01-01
- La version 2015 apporte des changements importants, notamment :
    - La catégorie 0 est éliminée;
    - La distance d’approche interdite est éliminée;
    - Il est interdit d’utiliser la méthode de calcul de l’énergie incidente conjointement avec les catégories d’ÉPI présentées aux tableaux 4B et 4C. Cependant, l’article 4.3.5.5 (c) (iii) nous permet d’utiliser la classification d’ÉPI du site, ce qui correspond très probablement aux tableaux 4B et 4C. Demander une confirmation au client au début du projet.

## Intrants

### ÉQUIPEMENTS DE PROTECTION INDIVIDUELS

- Au début du projet, demander une confirmation du client pour la classification d’ÉPI à utiliser. Nécessaire depuis la version 2015 de la norme CSA Z462 (voir section « Normes » ici-haut).

### Bus Data

- Nominal kV (when the prefault voltage option is set to use nominal kV);
- %V (when the prefault voltage is set to use bus voltage);
- Type (such as MCC, switchgear, etc.) and continuous bracing ratings;
- X-factor;
- Gap between conductors;
- Working distance;
- Equipment name;
- Insulated glove class (required for some labels);
- Insulated glove V-rating in volts (required for some labels);
- Main protective device isolation.

### Branch Data

- Branch Z, R, X, Y, or X/R values and units, tolerance, and temperature, if applicable;
- Cable and transmission line length and unit;
- Transformer rated kV and MVA;
- Base kV and MVA of impedance branches;
- Overload heater resistance;
- Equipment cable impedance;
- Transformer winding connections, grounding types, and grounding parameters to determine the K~2~ factor per IEEE 1584.

### Power Grid Data

- Nominal kV;
- %V and angle;
- 3-Phase MVA~SC~ and X/R;
- Grounding types and parameters to determine the K~2~ factor per IEEE 1584.

### Synchronous Generator Data

- Rated MW, kV and power factor;
- X~d~’’, X~d~’ and X/R;
- Generator type (i.e., salient pole, round rotor);
- Data required for generator decrement curves;
- Grounding types and parameters to determine the K~2~ factor per IEEE 1584.

### Inverter Data

- Rated MW, kV and power factor;
- K factor in the rating page.

### Synchronous Motor Data

- Rated kW / HP, kV and the number of poles;
- X~d~’’, X~d~’ and X/R;
- % LRC, X~d~ and T~do~’ for IEC short-circuit calculation;
- Grounding types and parameters to determine the K~2~ factor per IEEE 1584.

### Induction Motor Data

- Rated kW/hp and kV;
- X/R plus one of the following:
    - X~SC~ at ½ cycle and 1.5-4 cycles if ANSI short-circuit Z option is set to X~SC~; or
    - % LRC if ANSI short-circuit Z option is set to Std MF; or
    - % LRC and T~d~’ for IEC short-circuit calculations.
- Grounding types and parameters to determine the K~2~ factor per IEEE 1584.

### Lumped Load Data

- Rated MVA and kV;
- % motor load;
- % LRC, X/R and X~SC~ for ½ cycle and 1.5-4 cycles;
- X’ and T~d~’ for IEC short-circuit calculation;
- Grounding types and parameters to determine the K~2~ factor per IEEE 1584.

### High Voltage Circuit Breaker Data

#### ANSI Standard Circuit Breaker

- Max kV;
- Cycle (not the contact parting time but the rated interrupting time).

#### IEC Standard Circuit Breaker

- Rated kV;
- Minimum delay (minimum delay time in second).

### Low Voltage Circuit Breaker Data

#### ANSI Standard Circuit Breaker

- Type (power, moulded case or insulated case);
- Rated kV.

#### IEC Standard Circuit Breaker

- Type (power, moulded case or insulated case);
- Rated kV;
- Minimum delay (minimum delay time in second).

### Trip Device

- Trip device type library parameters;
- Device settings / TCC curves.

### Fuse Data

- Fuse ID;
- Fuse library data including size and TCC curves;
- Rated kV.

### Overload Heater / 49

- Resistance / tolerance;
- OLH library parameters.

### CT / PT Data

- Bus, branch, source or load connections;
- Rating (ratio).

### Relay / MVSST Data

- CT / PT connections / assignments;
- Interlocked devices, device ID, action, delay, settings and unit;
- Relay / MVSST library parameters including settings and TCC curves.

### Other Data

- Standard (ANSI / IEC);
- XFMR tap option (transformer tap modeling method);
- Prefault voltage;
- Faulted bus.

## Erreurs courantes

- J'ai tendance à favoriser une faible catégorie de risque de défaut d'arc, quitte à sacrifier la sélectivité des protections. Je devrais plutôt présenter le problème avec une coordination optimale et offrir divers moyens de mitigation au client;
- **Données de base :** Toujours, toujours vérifier toutes les données de base (intrants) essentiels avant d'envoyer mon étude en vérification interne. J'ai tendance à faire des erreurs stupides sur des équipements critiques comme le transformateur principal du site;
- L’option de « source PD » est souvent mal définie et le logiciel ne parvient pas à déterminer le bon FCT;
- Penser à vérifier le « through fault current » dans les paramètres d’étude.

## Mitigation

- **Sélecteur AMS (Alternate Maintenance Settings) ou équivalent :** Ceux de Square-D permettent d'abaisser le temps de déclenchement de l'élément de surintensité à temps défini, ce qui correspond grosso-modo à activer une instantanée. Consulter le manuel du manufacturier;
- **Zone Selective Interlocking :** Les relais peuvent être raccordés entre eux dans une armoire de commutation de façon à ce que le disjoncteur le plus proche de la faute isole celle-ci sans délai supplémentaire. Ça permet de ne pas introduire de délai supplémentaire dans le disjoncteur principal;
- **Deuxième groupe de réglages :** On peut, si le manufacturier n'offre pas cette option et qu'on a un relais de protection numérique, programmer un deuxième groupe de réglages de maintenance et l'activer par programmation lorsque le sélecteur ou le bouton choisi est actionné;
- **Protection différentielle :** Une protection différentielle est extrêmement rapide et réduit donc considérablement le niveau de risque dans la zone couverte;
- **Relais style VAMP-321 :** Les relais de ce type sont en mesure de détecter la lumière et le courant de l’arc pour un déclenchement hyper-rapide.

## Étiquettes

- **En français :** Utiliser l’étiquette « Avery-6579 Danger »;
- **En anglais :** Utiliser l’étiquette « 3X6 Danger4 »;
- Choix du client.
