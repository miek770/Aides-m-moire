# Aide-mémoire utilisation de PIC de Microphip

Surtout pour la conception de circuits pour PIC.

- Toujours installer un bornier pour PICkit2 sur mes circuits pour pouvoir programmer sans retirer le PIC;
- Lorsqu'une routine d'interruption utilise des variables globales, les déclarer volatiles. Pas besoin de sauvegarder les variables explicitement avec "save=" dans le #pragma de l'isr, en fait ça ne fonctionne pas si on fait les 2.
- Essayer d'utiliser des entrées avec pull-up internes programmables pour les entrées numériques, afin d'éviter les résistances externes;
- Faire attention aux sorties open-drain. Celles-ci ne présentent pas Vdd lorsque la sortie est à 1 mais offrent plutôt un chemin vers le ground. Je me suis fait avoir par ça dans le circuit d'horloge binaire.
