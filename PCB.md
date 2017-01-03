# Aide-mémoire conception de circuits

Surtout pour la conception de circuits sur Eagle, mais applicable à d'autres logiciels.

- Essayer de garder les traces sur le dessus du PCB, sauf pour de courtes distances;
- Mettre des traces plus larges pour l'alimentation;
- Ne pas utiliser le routing automatique;
- Éviter les traces en périphérie du PCB, au-delà de la converture du "ground plane". Si possible, mettre un contour de vias liés à la masse en périphérie pour naturellement éviter le problème;
- Mettre de gros vias en-dessous des circuits intégrés pour aider à dissiper de la chaleur. S'assurer que le cuivre n'est pas isolé, ce qui limiter la capacité à dissiper de la chaleur;
- Penser à faire des points de tests pour le multimètre et l’oscilloscope. Les faire avec des "headers" de 1 plutôt que des vias, qui sont parfois isolés (ne semble pas être le cas par défaut sur Eagle);
- Faire attention aux noms de signaux d’alimentation;
- Mettre des signes +/- sur l'alimentation pour ne pas se poser la question;
- Identifier la première pin de chaque bornier;
- Sélectionner les condensateurs de bypass en fonction des fréquences de fonctionnement du IC (voir [https://www.youtube.com/watch?v=BcJ6UdDx1vg](EEVblog #859 - Bypass Capacitor Tutorial). Penser à la fréquence du programmer et aussi aux fréquences des entrées/sorties. En fait je devrais consulter un petit guide de dimensionnement optimal en plus du vidéo explicatif indiqué;
- Mettre des condensateurs à chaque extrémité des traces d'alimentation, pas seulement à la charge;
- Mettre des vias pour raccorder les "ground planes" ensemble, encadrer les portions analogiques, encadrer le PCB, etc. Voir "ground stitching" sur internet.
