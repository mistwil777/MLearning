# Programme ML Accéléré — Contexte projet

## Ce qu'est ce projet

Programme d'apprentissage ML en 8 jours pour un étudiant M2 IA (alternance Capgemini). Chaque jour = `cours.md` + `exercice.md` dans `jour{N}/`. Le générateur `generate_html.py` produit le HTML depuis les markdown.

Le site est déployé sur Vercel via le repo GitHub `mistwil777/MLearning`.

---

## État du programme

| Jour | Thème | Statut |
|------|-------|--------|
| 1 | Paysage ML — taxonomie, bibliothèques, règles vs ML | ✅ Complet + visualisations |
| 2 | ML Classique — régression logistique, RF, XGBoost, pipeline, métriques | ✅ Complet + visualisations |
| 3 | Séries temporelles — ARIMA, Prophet, darts, évaluation | ✅ Complet + visualisations |
| 4 | Deep Learning & Transfer Learning — PyTorch, HuggingFace, fine-tuning | ✅ Complet |
| 5 | MLOps — MLflow, drift, Airflow/Prefect, FastAPI, Docker, monitoring | ✅ Complet + visualisations |
| 6 | Architecture hybride — ML + GenAI, RAG, agents, orchestration | ✅ Complet |
| 7 | Capstone — 3 cas complets de A à Z | ✅ Complet |
| 8 | Régression approfondie — Ridge, Lasso, polynomiale, courbes d'apprentissage | ✅ Complet + visualisations |

---

## Architecture technique

```
ml_accelerated/
├── generate_html.py     ← générateur central (NE PAS supprimer)
├── CLAUDE.md            ← ce fichier
├── README.md + .html    ← page d'accueil / index
├── index.html           ← copie de README.html pour Vercel
├── vercel.json          ← config déploiement statique
├── decision_framework.md + .html
└── jour{1-8}/
    ├── cours.md + .html
    └── exercice.md + .html
```

### generate_html.py — fonctionnalités clés
- Callouts : `:::situation`, `:::problem`, `:::rule`, `:::callout-insight`, `:::warning`, `:::limit`
- Mindmaps SVG : `:::mindmap <svg...> :::`
- Flashcards flip : `:::flashcards Q:/R: :::` — scroll horizontal, flip animé
- Bouton plein écran sur les mindmaps
- Fix overlap SVG automatique (JS au chargement)
- Liens `.md` → `.html` automatiquement réécrits
- `index.html` généré automatiquement depuis `README.md`

### Palette CSS
```
--bg:#16151a  --s1:#1e1c24  --s2:#26232f
--blue:#3987e5  --violet:#9085e9  --aqua:#1baf7a
--yellow:#e8a600  --red:#e66767
```

---

## Décisions prises et règles établies

### Pédagogie
- **Définition d'abord**, situation réelle ensuite — jamais l'inverse
- Tout terme technique expliqué au premier usage
- Questions instinctives soulevées en conversation = contenu manquant dans le cours
- Ton neutre et publiable — pas de références à "une question posée"
- Titres de sections : déclaratifs, jamais en forme de question implicite

### Visualisations
- SVG inline obligatoire pour chaque concept clé
- Dark theme, coordonnées calculées manuellement
- Cartes mentales : viewBox minimum 1100×470, bezier connectors, color-coded par famille

### Contenu
- Jamais surcharger un cours existant — ouvrir un nouveau jour si nécessaire
- Ridge/Lasso/régression polynomiale → Jour 8 (pas dans Jour 2)
- Chaque outil suit le schéma : origine → problème résolu (avant/après code) → cas réel → quand ne pas l'utiliser

### Déploiement
- Pusher uniquement les `.html` (les `.md` et `generate_html.py` sont dans `.gitignore`)
- Commande : `python3 generate_html.py && git add *.html */*.html index.html && git commit -m "..." && git push`

---

## Profil de l'étudiant

- Expérience pratique GenAI et multi-agents — pas de maîtrise théorique déclarée
- Points forts observés : bon raisonnement d'architecture système, intuition sur les complémentarités (clustering + séries temporelles, RAG + catalogue produit)
- Points faibles : mécanismes internes des algorithmes classiques, choix entre outils sur des critères précis, lecture et interprétation des métriques
- Apprend par visualisation, analogies, et cas réels français identifiables
- Veut une mesure honnête et objective de sa progression

---

## Ce qui reste à faire

- Continuer l'approfondissement selon les lacunes identifiées à la lecture des cours
- Déploiement Vercel : plugin installé (`npx plugins add vercel/vercel-plugin`), authentification à finaliser
- Mettre à jour le README.md avec le Jour 8 dans le tableau de progression
