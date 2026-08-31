# Formations IA — Le catalogue canonique des 7 formations

> De zéro à expert IA : 7 formations PDF 100 % actionnables pour maîtriser les LLM,
> construire des agents IA, automatiser avec n8n/Make, créer un SaaS sans code,
> vendre l'IA aux PME et mettre en place des systèmes RAG.
> Test de niveau gratuit inclus — 8 questions, 2 minutes.

**Statut** : ✅ EN LIGNE — catalogue unique fusionné (2026-09). Zéro simulateur : EmailJS réel, PDF réels, outil réel.
**Site** : https://dembis91-940.github.io/formations-ia/
**Dossier** : `~/Documents/livrables/catalogue-formations-ia/` (canonique)
**Historique** : fusion des 3 anciens catalogues (formations-ia + formations-catalogue + formations) en un seul.

---

## 1. Les 7 formations (contenu)

| # | Formation | Prix solo |
|---|---|---|
| 01 | Maîtrisez les LLM (GPT, Claude, Grok) | 19 € |
| 02 | Créez vos agents IA (n8n + Hermes) | 37 € |
| 03 | Prompt Engineering avancé | 19 € |
| 04 | Automatisation IA (n8n & Make) | 29 € |
| 05 | SaaS IA sans code | 39 € |
| 06 | Vendez des agents IA aux PME | 27 € |
| 07 | Systèmes RAG & bases de données | 29 € |

Chaque formation = **5-7 modules** (leçon dense + exemple réel + exercice pratique) + **checklist de fin de formation**. Sources Markdown : `01-*.md` → `07-*.md`. PDF : `pdf/`.

### 2. Les offres (3 niveaux)

| Offre | Prix | Contenu |
|---|---|---|
| **Solo** | 19-39 € | 1 formation PDF au choix |
| **Pack Complet** | **97 €** | Les 7 formations (au lieu de 7 × solo ≈ 199 €) |
| **Pack Direction** | **147 €** | Les 7 formations + session individuelle 45 min (upsell humain) |

---

## 3. Structure du livrable

```
catalogue-formations-ia/
├── index.html          Landing catalogue : héro, 7 formations, 3 packs, commande EmailJS, FAQ
├── outil.html          Test de niveau IA gratuit (8 questions → profil + formation recommandée)
├── chatbot.js          Widget FAQ + capture de leads (autonome, sans backend)
├── chatbot-config.js   Configuration du chatbot (nom, accents, FAQ, prix, EmailJS)
├── pdf/                7 PDF (sources = 01-*.md)
├── 01-*.md … 07-*.md   Sources Markdown des 7 formations
└── README.md           Ce fichier
```

### Pages & fonctionnalités
- **index.html** — héro + 3 arguments + catalogue 7 cartes (prix solo + mention Pack Complet) + section Packs 3 formules (Solo / Pack Complet / Pack Direction) + formulaire de commande EmailJS + FAQ accordéon. Schema.org : Product (9 offres) + FAQPage.
- **outil.html** — test de niveau réel, 8 questions, 100 % local (aucune donnée envoyée). Profil Débutant / Opérationnel / Avancé + formation recommandée + mention packs.
- **EmailJS** — réel et branché : `service_cy1ytdb` / `template_xpo58cv` / clé publique `8Pui4ZEqxW2jRVF7h`. Les boutons « Commander » pré-remplissent le sélecteur (`choisirOffre()` inline), le formulaire envoie `{site, name, email, question}`.

---

## 4. Zéro simulateur — vérifications effectuées

| Élément | Vérification | Statut |
|---|---|---|
| PDF (7) | Identiques dans les 3 anciens dossiers (md5) + présents dans `pdf/` | ✅ |
| Prix | Cohérents entre landing, JSON-LD, chatbot, outil de test (19-39 / 97 / 147) | ✅ |
| EmailJS | Identifiants réels + test d'envoi (status 200) | ✅ |
| Test de niveau | 8 questions → profil → recommandation, 100 % local | ✅ |
| Orthographe | Script de vérification française (espaces avant , .) | ✅ |
| Page en ligne | HTTP 200 sur GitHub Pages | ✅ |

---

## 5. Plan de lancement

| Étape | Action |
|---|---|
| 1. Déjà fait | Catalogue unique publié sur `formations-ia`, `formations-catalogue` archivé (redirection mentale) |
| 2. À connecter | **Payment Link Stripe** (Vague 1) — remplacer « virement ou message privé » par un lien de paiement réel par offre |
| 3. Contenu | 1 post X + 1 post LinkedIn par formation (kit promo agent commercial), CTA vers le test de niveau |
| 4. SEO | L'outil de test = lead magnet (note 7/10). Articles blog LLM/agents/RAG pour capter la recherche |
| 5. KPI | 200 leads test de niveau → 20-40 commandes → 15 % de Pack Complet, 5 % de Pack Direction |

---

## 6. Déploiement

Le site est 100 % statique, hébergé sur **GitHub Pages** :
```
https://dembis91-940.github.io/formations-ia/
```
Repo : `Dembis91-940/formations-ia` (branche `main`, Pages activé).
Redéployer : `git push` sur `main` → Pages rebuild automatiquement.

---

*Catalogue canonique créé par fusion des 3 catalogues (formations-ia, formations-catalogue, formations) — orchestré par Hermes, profil business-builder. Septembre 2026.*
