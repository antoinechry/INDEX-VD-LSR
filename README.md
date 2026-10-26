# Index VD+ LSR

Outil pour former des groupes de niveau homogènes sur les sorties LSR.

Chaque sortie vélo est placée sur un graphique VD+ / pente moyenne, avec les zones de couleur du club (gris, rouge, bleu, vert, blanc). Le rider voit quelle couleur choisir selon le terrain.

## Formule

VD+ = (Distance + D+ / xx) / temps = V + VAM / xx

Avec xx = 50, c'est le calcul de tête V (km/h) + 2 × VAM (en centaines de mètres).

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

Prototype. Les limites des zones (39, 35, 31, 27, 23, 19 km/h sur le plat, −8,5 % par point de pente) sont relevées à l'œil sur le graphique d'origine et restent à calibrer avec les données de plusieurs riders.

Page unique, sans build : ouvrir `index.html` ou passer par GitHub Pages.
