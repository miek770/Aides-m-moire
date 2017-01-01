# Aide-mémoire - Court-circuit

## Intrants

### Bus Data

- Nominal kV (when the prefault voltage option is set to use nominal kV);
- %V (when the prefault voltage is set to use bus voltage);
- Type (such as MCC, switchgear, etc.) and continuous bracing ratings;
- X-factor (à vérifier je ne suis pas certain);
- Equipment name.

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
- 3-Phase MVA~SC~ and X/R.

### Synchronous Generator Data

- Rated MW, kV and power factor;
- X~d~’’, X~d~’ and X/R;
- Generator type (i.e., salient pole, round rotor);
- Data required for generator decrement curves.

### Inverter Data

- Rated MW, kV and power factor;
- K factor in the rating page (je ne suis pas certain, à vérifier).

### Synchronous Motor Data

- Rated kW / HP, kV and the number of poles;
- X~d~’’, X~d~’ and X/R;
- % LRC, X~d~ and T~do~’ for IEC short-circuit calculation.

### Induction Motor Data

- Rated kW/hp and kV;
- X/R plus one of the following:
    - X~SC~ at ½ cycle and 1.5-4 cycles if ANSI short-circuit Z option is set to X~SC~; or
    - % LRC if ANSI short-circuit Z option is set to Std MF; or
    - % LRC and T~d~’ for IEC short-circuit calculations.

### Lumped Load Data

- If possible, group motors <50 HP;
- Rated MVA and kV;
- % motor load;
- % LRC, X/R and X~SC~ for ½ cycle and 1.5-4 cycles;
- X’ and T~d~’ for IEC short-circuit calculation.

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

### Other Data

- Standard (ANSI / IEC);
- XFMR tap option (transformer tap modeling method);
- Prefault voltage;
- Faulted bus.

## Guides et normes

- IEEE 1015-2006, IEEE Recommended Practice for Applying Low-Voltage Circuit Breakers Used in Industrial and Commercial Power Systems, 29 septembre 2006
- IEEE 141-1993, IEEE Recommended Practice for Electric Power Distribution for Industrial Plants (Red Book), 29 avril 1994;
- IEEE 399-1997, IEEE Recommended Practice for Industrial and Commercial Power Systems Analysis (Brown Book), 31 août 1998;
- IEEE C37.010-1999, IEEE Application Guide for AC High-Voltage Circuit Breakers Rated on a Symmetrical Current Basis, 1er janvier 2009.

## Erreurs courantes

- **Données de base :** Toujours, toujours vérifier toutes les données de base (intrants) essentiels avant d'envoyer mon étude en vérification interne. J'ai tendance à faire des erreurs stupides sur des équipements critiques comme le transformateur principal du site;
- **Asymétrie :** Faire une mention de l’asymétrie ou l’inclure aux résultats pour la basse tension si le X/R est supérieur à 6,6. Au-delà de ça on sort des limites définies par le standard IEEE 1015-2006.
