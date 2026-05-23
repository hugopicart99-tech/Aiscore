# ScoresAI — Tous les fichiers du projet

## Structure du projet

```
scoresai/
├── index.html       → Landing page SEO (page d'accueil Google)
├── match.html       → Page match complète (score live, lineups, stats, AI)
├── manifest.json    → PWA — installe l'app sur mobile comme une app native
├── sw.js            → Service Worker — offline, cache, push notifications
├── robots.txt       → Instructions pour Google (quoi indexer)
├── sitemap.xml      → Plan du site pour Google (toutes les URLs)
└── README.md        → Ce fichier
```

## Ce que fait chaque fichier

### index.html — Landing page SEO
- Page d'accueil complète avec tous les matchs du jour
- Méta tags SEO (title, description, Open Graph, Twitter Card)
- Schema JSON-LD (Google Rich Results — étoiles, FAQ)
- Boutons Betway & Bet365 cliquables sur chaque match
- Dark mode + responsive mobile

### match.html — Page match complète
- Score en direct avec minutage live
- 6 onglets : Overview / Lineups / Stats / Injuries / H2H / AI Prediction
- Terrain visuel interactif avec formations et joueurs
- Blessés et suspendus avec statut et date de retour
- Statistiques complètes (xG, possession, tirs, passes...)
- Head-to-head 5 dernières confrontations
- Analyse complète générée par Claude AI en temps réel
- Sticky bet bar Betway + Bet365 toujours visible
- News sidebar Arsenal & Chelsea

### manifest.json — PWA
- Permet d'installer ScoresAI sur mobile (sans App Store)
- Shortcuts vers Predictions et Leaderboard
- Icônes, couleurs, orientation

### sw.js — Service Worker
- Cache le site pour un chargement hors-ligne
- Gère les push notifications (alertes buts, matchs)
- Network-first pour les données live, cache-first pour le shell

### robots.txt
- Autorise Google, Bing, etc. à indexer le site
- Bloque /admin et /api/
- Pointe vers le sitemap

### sitemap.xml
- Toutes les URLs du site avec priorités
- Pages leagues : /predictions/premier-league etc.
- Pages matchs individuelles : /predictions/premier-league/arsenal-vs-chelsea-2025-05-23
- Articles blog

## Déploiement sur Vercel

1. Va sur vercel.com → crée un compte gratuit
2. New Project → glisse ce dossier
3. Deploy → tu obtiens une URL scoresai-xxx.vercel.app

## Connecter GitHub pour l'auto-deploy

1. Crée un repo "scoresai" sur github.com
2. Upload tous ces fichiers
3. Dans Vercel → connecte ton repo GitHub
4. Désormais chaque changement sur GitHub = redéploiement automatique en 30s

## APIs à connecter (prochaine étape)

| API | Usage | Prix |
|-----|-------|------|
| API-Football (RapidAPI) | Scores live, lineups, blessés, logos | Gratuit (100 calls/jour) |
| Claude API (Anthropic) | Prédictions AI + articles blog | ~5-15$/mois |
| TheSportsDB | Logos clubs, Basketball, Hockey | Gratuit |
| RSS Sky Sports / BBC | Articles news automatiques | Gratuit |

## Variables d'environnement Vercel (à ne jamais mettre sur GitHub)

```
ANTHROPIC_API_KEY=sk-ant-...
API_FOOTBALL_KEY=ton-api-key
BETWAY_AFFILIATE_ID=ton-id
BET365_AFFILIATE_ID=ton-id
```

## Prochaines features à développer

- [ ] Blog automatique (RSS → Claude → article SEO)
- [ ] Basketball NBA + Euroleague
- [ ] Hockey NHL
- [ ] Backend Vercel Serverless (api/predict.js)
- [ ] Domaine scoresai.com
- [ ] Programme affilié Betway + Bet365
- [ ] Google Search Console + Analytics
