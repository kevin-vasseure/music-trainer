# Music Trainer — Résumé de session

## Contexte

Projet personnel : apprendre à improviser au synthétiseur 25 touches de manière harmonieuse, sans connaissances musicales préalables.

---

## Concepts clés abordés

### Gamme pentatonique mineure
La gamme "sans fausse note" — idéale pour débuter l'improvisation. En La mineur : **La – Do – Ré – Mi – Sol**. Jouer ces notes sur un backing track en Am sonne toujours bien.

### Modes à connaître
| Mode | Couleur |
|---|---|
| Ionien (majeur) | Joyeux, lumineux |
| Dorien | Jazzy, soul, funk |
| Phrygien | Sombre, espagnol, metal |
| Mixolydien | Blues, rock |
| Blues | Expressif, feeling |

### Conseils d'impro
- Jouer avec les **silences** (aussi importants que les notes)
- **Répéter une phrase** puis la varier légèrement
- Monter/descendre la gamme graduellement
- La **tonique** = point de repos, commencer et finir dessus
- Varier les **octaves**
- Se caler sur le **rythme** du backing track

---

## Application web créée

Un synthétiseur d'entraînement interactif en HTML/CSS/JS pur (single file).

### Fonctionnalités
- **Clavier 25 touches** (C3 → C5), jouable à la souris, au touch ou au clavier PC
- **9 gammes** : pentatonique min/maj, ionien, dorien, phrygien, lydien, mixolydien, éolien, blues
- **12 toniques** (toutes les notes chromatiques)
- Touches de la gamme **surlignées en violet**, tonique en **rouge**
- **Synthé Web Audio API** : oscillateur + enveloppe + reverb
- Choix de la **forme d'onde** : sine, triangle, sawtooth, square
- **Volume** et **reverb** ajustables
- **Visualiseur** animé
- **Liens YouTube** vers des backing tracks adaptés à chaque mode
- **Conseils d'impro** qui tournent toutes les 8 secondes

### Fichier
`index.html` — fichier unique, aucune dépendance externe (sauf Google Fonts)

---

## Déploiement prévu

- **Repo GitHub** : `kevin-vasseure/music-trainer` (public)
- **Hosting** : GitHub Pages → `https://kevin-vasseure.github.io/music-trainer`
- **Workflow update** : Claude génère le fichier HTML → push via Claude Code

### Setup avec Claude Code

```bash
# 1. Créer le repo
gh repo create music-trainer --public --clone
cd music-trainer

# 2. Copier le fichier HTML généré par Claude
cp /chemin/vers/index.html .

# 3. Premier push
git add index.html
git commit -m "Initial commit — synth trainer"
git push origin main

# 4. Activer GitHub Pages
gh api repos/kevin-vasseure/music-trainer/pages \
  --method POST \
  -f "source[branch]=main" \
  -f "source[path]=/"
```

### Workflow pour les updates

```bash
# Claude génère un nouveau index.html
# Tu le copies dans le repo, puis :
cp /nouveau/index.html ~/music-trainer/index.html
cd ~/music-trainer
git add index.html
git commit -m "Update — <description>"
git push origin main
# → GitHub Pages se redéploie automatiquement en ~30s
```

---

## Token GitHub

Un classic token avec scope `repo` a été généré lors de la session.
> ⚠️ À révoquer et regénérer si nécessaire : [github.com/settings/tokens](https://github.com/settings/tokens)
