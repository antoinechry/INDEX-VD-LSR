# Index VD+ LSR

Outil pour former des groupes de niveau homogènes sur les sorties LSR.

Chaque sortie vélo est placée sur un graphique VD+ / pente moyenne, avec les zones de couleur du club (gris, rouge, bleu, vert, blanc). Le rider voit quelle couleur choisir selon le terrain.

## Formule

VD+ = (Distance + D+ / xx) / temps = V + VAM / xx

Le graphique porte la **vitesse réelle** de chaque sortie en fonction de sa pente moyenne. Les zones de couleur sont des bandes de **VD+ constant**, ramenées en vitesse : comme VAM = V × 10 × pente (%), on a V = VD+ / (1 + 10 × pente / xx). La décroissance des zones est donc fixée par xx.

xx = 100 reproduit le graphique d'origine. Le calcul de tête V (km/h) + 2 × VAM (en centaines de mètres) correspond à xx = 50.

Le bon xx est celui qui rend la régression du VD+ d'un rider plate. La page le calcule pour chaque rider ; la médiane sur le club donne le xx à retenir.

## Terrains

| Terrain | Pente moyenne |
|---|---|
| Plat | moins de 0,5 % |
| Vallonné | 0,5 à 1,5 % |
| Escarpé | 1,5 à 2,5 % |
| Abrupte | plus de 2,5 % |

## Utilisation

1. Sur strava.com › Paramètres › Mon compte › **Télécharger ou supprimer votre compte** › **Demander une archive**.
2. Strava envoie un lien par e-mail. Décompresser l'archive.
3. Déposer `activities.csv` sur la page. Le fichier est lu dans le navigateur : rien n'est envoyé ni enregistré.

Les sorties de plus de 3,5 % de pente moyenne sont écartées, trop spécifiques pour situer un niveau. Les trajets marqués « Commute » sont exclus par défaut.

## Ce que fait la page

- Graphique des sorties, zones de couleur et courbe du rider (régression d'ordre 2)
- Couleur conseillée sur chaque terrain
- Groupe conseillé pour une sortie donnée (distance + D+)
- Calibration du coefficient xx
- Prompt prêt à l'emploi pour Claude avec le connecteur Strava

## Statut

Prototype. Les limites des zones (VD+ de 39, 35, 31, 27, 23 et 19 km/h) sont relevées à l'œil sur le graphique d'origine. Le xx reste à calibrer avec les données de plusieurs riders.

Page unique, sans build : ouvrir `index.html` ou passer par GitHub Pages.
