# Fiche karting v10

PWA mobile pour pilote KA100. Tout fonctionne hors-ligne après la première visite.

## Nouveautés v10
- **Météo auto** : date + heure + circuit → température, humidité, vent, pression, densité d'air, état piste estimé. Source Open-Meteo (gratuit, sans clé).
- **Import Alfano 6** : dépose un export CSV/XML de l'app Alfano → RPM max/mini, EGT, CHT, chronos par tour auto-remplis.
- **Couples KA100 corrigés** : 16 lignes du manuel IAME MAN-086-FR p.29 (dont la ligne "Support Bendix" qui manquait, et l'outil Hex.27 corrigé pour la couronne démarreur).
- **Comparatif 2 runs** avec différences mises en valeur.
- **Tours & partiels** : 10 tours, calcul auto du meilleur, moyenne, constance σ.
- **Carburation EGT/CHT** : analyse auto avec recommandations vis H.
- **Pressions** : Δ chaud-froid auto avec alertes si écart trop grand.
- **Checklists** pré- et post-session.
- **Export/import JSON** de tout l'historique.

## Installation

### Sur iPhone (Safari)
1. Ouvrir `index.html` (servi en https ou localhost)
2. Bouton Partager → "Sur l'écran d'accueil"
3. L'icône apparaît, l'app marche hors-ligne

### Hébergement
N'importe quel hébergement statique : GitHub Pages, Netlify, Vercel, serveur perso, etc.
Important : **HTTPS obligatoire** pour le service worker (sauf en localhost).

## Circuits pré-enregistrés (avec GPS pour la météo)
Aigues-Vives · Alès · Belmont · Berdery (Lescar) · Ganges · Layrac · Le Mans · Muret · Valence (Driv'kart / La Roche-de-Glun)

## Format Alfano CSV attendu
Le parseur essaie de reconnaître automatiquement les colonnes :
- RPM, "tr/min", "tour/min"
- Speed, vitesse, km/h
- EGT, exhaust, échap
- CHT, head, tête, water
- Lap time, lap_time, tps tour, temps tour

Si ton export n'est pas reconnu, le parseur affichera les headers détectés et tu peux me les envoyer pour adapter.

## Stockage
- localStorage (même appareil, même navigateur)
- Sauvegarde JSON exportable / importable
- Pas de cloud, pas de tracking
