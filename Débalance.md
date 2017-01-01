# Aide-Mémoire - Débalance

On accepte en règle générale une débalance de 5% sur un réseau triphasé. Au-delà de ce pourcentage, il faut tenter de balancer les charges pour réduire la débalance.

Le pourcentage de 5% m'a été donné par Claude Martin le 12 novembre 2014. Je ne trouve pas de référence ailleurs mais ça semble une bonne règle du pouce.

## Impacts

Les 2 problèmes avec la débalance sont :

1. La puissance maximale de chaque phase ne doit pas dépasser le tiers de la puissance maximale du transformateur;
2. Si la débalance est trop important, les tensions vont être affectées négativement.

## Analyse

Pour analyser le 2e impact identifié ici-haut, je ne connais pas d'autre méthode actuellement que de calculer les composantes symmétriques à partir du circuit débalancé et de convertir le résultats en phaseurs.

Ça semble trop fastidieux pour la plupart des cas. Il est généralement préférable de s'en tenir à la limite de 5%.
