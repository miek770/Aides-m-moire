# Aide-mémoire utilisation de PIC de Microphip

Surtout pour la conception de circuits pour PIC.

- Toujours installer un bornier pour PICkit2 ou 3 sur mes circuits pour pouvoir programmer sans retirer le PIC;
- Lorsqu'une routine d'interruption utilise des variables globales, les déclarer volatiles. Pas besoin de sauvegarder les variables explicitement avec "save=" dans le #pragma de l'isr, en fait ça ne fonctionne pas si on fait les 2.
