# Aide-mémoire conception de circuits

Surtout pour la conception de circuits sur Eagle, mais applicable à d'autres logiciels.

- Penser à faire des points de tests pour le multimètre et l’oscilloscope;
- Faire attention aux noms de signaux d’alimentation;
- Mettre des signes +/- sur l'alimentation pour ne pas se poser la question;
- Sélectionner les condensateurs de bypass en fonction des fréquences de fonctionnement du IC (voir [https://www.youtube.com/watch?v=BcJ6UdDx1vg](EEVblog #859 - Bypass Capacitor Tutorial). Penser à la fréquence du programmer et aussi aux fréquences des entrées/sorties. En fait je devrais consulter un petit guide de dimensionnement optimal en plus du vidéo explicatif indiqué;
- Mettre des vias pour raccorder les "ground planes" ensemble, encadrer les portions analogiques, encadrer le PCB, etc. Voir "ground stitching" sur internet.
