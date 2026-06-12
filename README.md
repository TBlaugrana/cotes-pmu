# TBlaugrana BOT — GitHub Pages Edition

Bot de surveillance des cotes PMU, version **standalone navigateur**.  
Aucun serveur Python requis. Fonctionne directement depuis GitHub Pages ou un simple double-clic sur `index.html`.

---

## 🚀 Mise en ligne sur GitHub Pages

1. Crée un nouveau dépôt GitHub (public ou privé avec Pages activé)
2. Dépose le fichier `index.html` à la racine du dépôt
3. Dans les paramètres du dépôt → **Pages** → source : `main` / `root`
4. Ton bot sera accessible à l'adresse :
   ```
   https://<ton-pseudo>.github.io/<nom-du-repo>/
   ```

---

## 💻 Utilisation hors-ligne (sans internet → PMU seulement)

Double-clique simplement sur `index.html` dans ton explorateur de fichiers.  
Le navigateur ouvrira le bot localement.

> ⚠️ **Internet reste nécessaire pour récupérer les cotes PMU** — le bot appelle l'API PMU en temps réel. "Hors-ligne" signifie ici : pas besoin de Python ni de serveur local.

---

## ⚙️ Proxy CORS

L'API PMU bloque les appels directs depuis un navigateur (protection CORS).  
Le bot essaie automatiquement 3 proxies publics dans l'ordre :

| Priorité | Proxy |
|----------|-------|
| 1 | `corsproxy.io` |
| 2 | `allorigins.win` |
| 3 | `codetabs.com` |

Si le proxy 1 est surchargé, le bot bascule automatiquement sur le suivant.  
Le proxy actif est affiché en haut à gauche de l'interface.

---

## 🔧 Paramètres (dans `index.html`)

Modifie la section **PARAMETRES UTILISATEUR** en haut du `<script>` :

```js
const AUTO_ADVANCE_MIN = 5;   // Minutes avant passage auto à la course suivante
const REFRESH_SEC      = 5;   // Intervalle entre deux appels API (secondes)
const COTE_MIN         = 1.0; // Cote minimale surveillée
const COTE_MAX         = 10.0;// Cote maximale surveillée
const DROP_ALERT       = 10.0;// Seuil de chute (%) pour alerte
```

---

## 🔔 Différences avec la version Python locale

| Fonctionnalité | Version Python | Version GitHub Pages |
|---|---|---|
| Alertes Telegram | ✅ | ❌ (pas de backend) |
| Fonctionne sans Python | ❌ | ✅ |
| Accessible depuis mobile | ❌ | ✅ |
| Hébergement | Local (port 8765) | GitHub Pages / navigateur |

---

## 📁 Structure du dépôt

```
/
└── index.html   ← tout-en-un, rien d'autre nécessaire
```
