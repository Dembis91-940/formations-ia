# 🛠️ SaaS IA SANS CODE — créez et lancez votre SaaS avec le vibe coding

> **Promesse mesurable** : à la fin, vous avez **un SaaS fonctionnel en ligne, avec page de vente, paiement et livraison automatique** — lancé en 2 à 4 semaines, pour moins de 50 € de frais, sans écrire une ligne de code à la main.
>
> **Format** : pack PDF, 7 modules, ~6 h de lecture + construction pas à pas.
> **Cible** : entrepreneurs solo, freelances et indépendants qui ont une idée de produit numérique ou de service IA et veulent la lancer sans développeur.
> **Prérequis** : savoir utiliser un navigateur, une boîte mail et un tableur. Aucune compétence technique requise — le vibe coding fait le code, vous faites la vision.
> **Durée** : 6 h réparties sur 2 semaines (construction réelle comprise).

---

## Module 1 — Le vibe coding : de quoi on parle, et pourquoi c'est crédible

### Leçon

Le **vibe coding** (codage par l'ambiance, terme popularisé en 2025 par Andrej Karpathy) : on décrit ce qu'on veut en langage naturel à un assistant de code IA (Claude, ChatGPT avec agents de code, Cursor, Replit Agent), et l'IA écrit, corrige et améliore le code. Le créateur **pilote, valide et teste** — il ne tape pas le code.

**La révolution** : un produit qui demandait 6 mois et 30 000 € de développement se construit en 2-4 semaines pour moins de 50 €/mois d'outils. Le goulot d'étranglement n'est plus le code : c'est la **définition du produit** (ce qu'on construit, pour qui, pour résoudre quoi).

**Ce que le vibe coding est VRAIMENT** (pour éviter les illusions) :

| C'est | Ce n'est pas |
|---|---|
| Construire des produits web (pages, formulaires, tableaux de bord, mini-apps) | Un remplacement des applications complexes (bases distribuées, sécurité bancaire) |
| Un produit qui résout UN problème précis, simplement | Un clone d'Amazon en 2 semaines |
| Un processus itératif : décrire → tester → corriger | Une baguette magique : l'IA ne devine pas une vision floue |
| 80 % de la valeur pour 10 % du coût d'un dev traditionnel | Zéro maintenance (il y a toujours de la maintenance) |

**Les 4 piliers du succès d'un SaaS vibe-codé** :
1. **Un problème réel et précis** (votre douleur ou celle d'un secteur que vous connaissez).
2. **Un périmètre minuscule** : une fonctionnalité principale, faite parfaitement.
3. **Une boucle de feedback rapide** : vous testez avec de vrais utilisateurs dès la semaine 1.
4. **Un modèle de revenus simple** : un paiement unique ou un abonnement, mis en place dès le jour 1 — jamais « on verra plus tard ».

**Le piège n°1 : l'idée large**. « Une plateforme pour les coachs » = rien. « Un outil qui génère le compte-rendu de séance d'un coach sportif en 1 clic » = un produit. **Rétrécissez jusqu'à ce que vous puissiez décrire le produit en une phrase** : « Qui, avec quel besoin, obtient quoi, en combien de temps ? »

### Exemple réel

CoachFlow (exemple concret de cette méthode) : au lieu de « un SaaS pour coachs sportifs », le produit est « l'outil qui transforme les notes de séance d'un coach en compte-rendu client + plan de séance en 1 clic ». Une page de vente, un formulaire de paiement, une livraison par email. Lancé en 3 semaines, modifié chaque semaine selon les retours.

### Exercice pratique

1. Écrivez votre idée en une phrase : « [QUI] avec [BESOIN] obtient [RÉSULTAT] en [TEMPS] ».
2. Listez les 3 douleurs que vous avez vécues vous-même dans votre travail (les meilleures idées viennent de là).
3. Choisissez LA plus douloureuse et la plus fréquente. C'est votre produit. Notez : les 3 pires solutions actuelles (le marché que vous attaquez).

---

## Module 2 — L'architecture d'un SaaS minimal (le squelette en 6 pièces)

### Leçon

Tout SaaS « solo » se réduit à 6 pièces. Les connaître vous évite de payer un développeur pour réinventer la roue :

```
1. LA PAGE DE VENTE  → la promesse, les preuves, le prix, le bouton d'achat
2. LE PAIEMENT       → encaisser (Stripe, Lemon Squeezy, Gumroad, PayPal)
3. LA LIVRAISON      → délivrer l'accès (email automatique avec le lien/le produit)
4. L'ESPACE PRODUIT  → ce que le client utilise (formulaire, générateur, tableau de bord)
5. LE SUIVI          → les données (qui a acheté, qui utilise, qui a besoin de relance)
6. L'EMAIL           → confirmation d'achat, onboarding, relances (automatiques)
```

**Le choix des outils (la stack type d'un SaaS sans code)** :

| Pièce | Outils recommandés | Coût |
|---|---|---|
| Page de vente | Site statique (HTML/CSS généré par IA) hébergé sur GitHub Pages, ou Carrd/Webflow | 0-20 €/mois |
| Paiement | Lemon Squeezy ou Stripe (via leur lien de paiement ou un formulaire) | ~3-5 % par vente |
| Livraison | Email automatique via l'outil de paiement (Lemon Squeezy délivre les produits numériques tout seul) ou EmailJS | inclus |
| Espace produit | Page web statique avec formulaire + un peu de JS (généré par l'IA), ou un outil no-code (Glide, Softr) | 0-25 €/mois |
| Suivi | Google Sheets (chaque vente = une ligne) | 0 € |
| Email | EmailJS (transactions) + Gmail / séquence simple | 0-15 €/mois |

**La règle d'or des premiers euros** : **encaisser AVANT de perfectionner**. La version 1 peut être laide ; elle doit être fonctionnelle : une page qui vend, un bouton qui encaisse, un email qui livre. Tout le reste s'améliore après les premières ventes.

**Le piège n°2 : construire l'espace produit avant la vente**. L'ordre correct : **vendre d'abord, construire ensuite**. Une page de vente + une promesse testées sur 5-10 personnes valident le produit avant que vous passiez 3 semaines à le construire. On ne construit pas un restaurant avant d'avoir vérifié que les gens ont faim.

### Exemple réel

Le squelette d'un « générateur de fiches produit IA » : page de vente (promesse + 3 preuves + 27 €), bouton → Lemon Squeezy, email automatique avec le lien de l'outil, l'outil = une page avec un formulaire (coller le produit → générer la fiche via API IA) + une feuille Sheets qui enregistre chaque vente pour le suivi. Total : ~2 semaines de construction, ~4 € par vente de frais.

### Exercice pratique

1. Dessinez votre squelette : les 6 pièces de VOTRE produit (quelles pages, quel paiement, quelle livraison, quelle feuille de suivi).
2. Créez vos comptes : GitHub (Pages), Lemon Squeezy ou Stripe, EmailJS (gratuit), Google Sheets.
3. Notez le coût total mensuel de votre stack. S'il dépasse 50 €, simplifiez.

---

## Module 3 — Générer votre site avec l'IA : la page de vente qui convertit

### Leçon

La page de vente est votre vendeur 24/7. Structure éprouvée (celle des meilleures pages solo) :

```
1. HERO : titre = promesse (résultat), sous-titre = qui c'est pour, bouton = acheter
2. PROBLÈME : le coût de ne rien faire (émotion + chiffres)
3. SOLUTION : votre produit en 3 bénéfices concrets
4. PREUVES : 3 témoignages ou résultats chiffrés (même 2-3 beta testeurs)
5. FONCTIONNEMENT : comment ça marche (3 étapes simples)
6. PRIX : 1 à 2 formules, prix barré si lancement, garantie
7. FAQ : 4-6 objections (prix, compétence, délai, résultat)
8. CTA FINAL : rappel de la promesse + bouton + garantie
```

**Le prompt de génération de page (vibe coding)** — le « brief » que vous donnez à l'IA :

```
Crée une page de vente complète en HTML/CSS (un seul fichier, design moderne,
responsive, couleurs [VOS COULEURS], police système).

PRODUIT : [description en une phrase]
CIBLE : [qui]
PROMESSE : [résultat mesurable]
PRIX : [prix] €, prix barré [ancien prix] €
GARANTIE : [garantie]
STRUCTURE : hero, problème, solution, preuves, fonctionnement, prix, FAQ, CTA final
TON : direct, français, sans blabla, tutoiement

Le bouton d'achat doit pointer vers [LIEN DE PAIEMENT].
Écris le HTML complet, je vais le mettre en ligne tel quel.
```

**Les règles de conversion** :
1. **Une seule action demandée** : acheter. Pas de « téléchargez notre brochure » à côté du bouton d'achat.
2. **La promesse mesurable** : « gagnez 5 h/semaine », pas « devenez plus efficace ».
3. **La preuve avant le prix** : on montre la valeur avant de révéler le coût.
4. **La garantie** réduit le risque : « satisfait ou remboursé 14 jours » (les remboursements réels sont < 5 % et la garantie augmente les ventes de 10-20 %).
5. **Un prix, pas dix** : 2 formules max au lancement.

**Le piège n°3 : le design avant le fond**. Une belle page qui ne vend pas est une belle perte de temps. Validez la promesse et le texte AVANT le design. L'IA génère le HTML, vous testez le message.

### Exemple réel

Prompt envoyé à l'IA (résumé) : « Page de vente pour un outil qui génère les compte-rendus de séance des coachs sportifs. Promesse : 1 clic = compte-rendu envoyé au client. Prix 47 € (barré 87 €). Garantie 14 jours. » L'IA produit la page en 1 fichier HTML. L'entrepreneur la met sur GitHub Pages, pointe le bouton vers son lien Lemon Squeezy, et l'envoie à 5 coachs de son réseau. 2 achats le premier week-end → le produit est validé avant même d'être construit.

### Exercice pratique

1. Rédigez votre promesse mesurable (une phrase, chiffrée).
2. Lancez le prompt ci-dessus avec votre IA de code préférée (Claude, ChatGPT, Cursor).
3. Itérez 3 fois : « rends le hero plus direct », « ajoute une preuve », « raccourcis la FAQ ».
4. Mettez la page en ligne (GitHub Pages : poussez le fichier index.html dans un dépôt, activez Pages dans les réglages — ou utilisez Netlify Drop : glisser-déposer le fichier, gratuit).
5. Envoyez la page à 5 personnes de votre cible et demandez : « L'achèterais-tu ? Pourquoi ? » Notez TOUTES les objections.

---

## Module 4 — Le paiement et la livraison automatique (encaisser sans stress)

### Leçon

Trois solutions réalistes pour encaisser sans code :

**Option 1 — Lemon Squeezy (recommandée pour les produits numériques)** :
- Créez le produit, fixez le prix, collez le lien d'achat sur votre page.
- **Livraison automatique** : si le produit est un fichier (PDF, pack), Lemon Squeezy le délivre par email après paiement — zéro code.
- Si le produit est un accès (lien vers un outil), l'email de confirmation peut contenir le lien d'accès.
- Gère la TVA numérique (importante en France/UE) et les remboursements.

**Option 2 — Stripe (Payment Links)** : lien de paiement simple, plus orienté « paiement » que « livraison » — il faut un email automatique à côté (EmailJS ou une séquence Gmail).

**Option 3 — Le formulaire + EmailJS (la méthode « zéro abonnement »)** : le formulaire de paiement/commande de votre page envoie la commande vers votre Gmail (via EmailJS, service gratuit) ET la feuille Sheets de suivi. Vous livrez vous-même (ou avec une automatisation Make/n8n — voir formation 4). Parfait pour démarrer à 0 € de frais fixes.

**Le flux complet à vérifier avant lancement** :

```
Clic "Acheter" → page de paiement (Stripe/LS) → paiement réussi
   → email de confirmation client (automatique)
   → ligne dans la feuille de suivi (automatique)
   → accès au produit (lien dans l'email / fichier délivré)
```

**Les 3 vérifications obligatoires** (faites-les vous-même, en conditions réelles) :
1. Payer 1 € sur votre propre lien (test réel, remboursable) → vérifier la réception de l'email.
2. Vérifier la ligne dans la feuille de suivi.
3. Vérifier que le lien d'accès fonctionne depuis un autre navigateur (pas votre session).

**Le piège n°4 : le « paiement simulé »**. Un formulaire qui dit « merci, votre commande est enregistrée » sans encaisser réellement = une promesse non tenue et une perte de crédibilité. **La règle de Demba : zéro simulateur** — si la page vend, le paiement DOIT encaisser, l'email DOIT partir, le produit DOIT être livré. Testez en réel avant de lancer.

### Exemple réel

Un créateur de templates vend un pack à 29 € : bouton → Lemon Squeezy (paiement carte, TVA gérée) → email automatique avec le PDF + le lien d'accès aux mises à jour. Test : il achète son propre pack avec une carte de test, vérifie email et fichier, puis rembourse. Le tout : 20 minutes de mise en place.

### Exercice pratique

1. Choisissez votre solution de paiement (LS recommandé, Stripe, ou EmailJS).
2. Créez le produit (nom, prix, fichier ou lien d'accès).
3. Branchez le bouton de votre page de vente.
4. Réalisez le test réel complet (paiement → email → livraison → suivi). Documentez le résultat. **C'est votre preuve que le produit est vendable.**

---

## Module 5 — Construire l'outil : le cœur du SaaS (formulaire + IA + résultat)

### Leçon

La plupart des SaaS vibe-codés se résument à : **un formulaire en entrée, une IA au milieu, un résultat en sortie** (avec parfois une sauvegarde). Exemples : coller un texte → obtenir un résumé/une fiche/un email ; répondre à 5 questions → obtenir un devis/un plan/un compte-rendu.

**L'architecture type** :

```html
<!-- Page outil : un formulaire -->
<form id="generateur">
  <textarea id="entree" placeholder="Collez votre texte ici..."></textarea>
  <button type="submit">Générer</button>
</form>
<div id="resultat"></div>

<script>
// Appel à l'API IA (exemple : OpenAI, appel direct depuis le navigateur)
// ⚠️ SECURITÉ : la clé API ne doit JAMAIS être dans une page publique.
// Solution sûre pour démarrer : passer par un petit backend
// (Cloudflare Workers gratuit, ou n8n comme passerelle).
</script>
```

**Le point technique critique : la clé API**. Une clé OpenAI/Claude collée dans le HTML d'une page publique est **volée en quelques heures** (les robots scannent le web en continu). Les 2 solutions sûres pour un débutant :

1. **n8n comme passerelle** (recommandé, gratuit) : la page appelle un webhook n8n ; c'est n8n qui détient la clé API et appelle le LLM ; le résultat revient à la page. Votre clé n'est jamais exposée.
2. **Cloudflare Workers** (gratuit, 100 000 requêtes/jour) : un mini-script qui détient la clé et sert d'intermédiaire. L'IA de code vous le génère en 10 minutes.

**Le prompt de génération de l'outil** :

```
Crée une page web (HTML/CSS/JS, un fichier) : un formulaire avec [champ d'entrée],
un bouton "Générer", et une zone de résultat.
Quand l'utilisateur clique : envoie l'entrée à [URL DU WEBHOOK/PASSERELLE]
(avec fetch POST, format JSON), affiche la réponse dans la zone de résultat.
Design : [votre style], responsive, français.
```

**Les 3 états de l'interface** (à ne jamais oublier) :
1. **Chargement** : « Génération en cours... » (sinon l'utilisateur croit que c'est cassé).
2. **Succès** : le résultat affiché + un bouton « copier ».
3. **Erreur** : un message clair (« Réessayez dans une minute »), jamais une page blanche.

### Exemple réel

« PreuveIA » (exemple) : un outil où le client colle un texte → l'outil le passe à n8n → n8n appelle le LLM avec le prompt d'analyse → renvoie le verdict + le rapport. La page affiche le résultat avec un bouton copier. L'entrepreneur n'a JAMAIS mis une clé API dans son site : tout passe par la passerelle.

### Exercice pratique

1. Rédigez la spécification de votre outil : entrée (quoi), traitement (quelle logique/prompt), sortie (quoi).
2. Mettez en place la passerelle : n8n (webhook + nœud LLM) ou Cloudflare Workers.
3. Faites générer la page outil par l'IA, branchez la passerelle.
4. Testez le flux complet depuis un navigateur « propre » (fenêtre de navigation privée). Corrigez jusqu'à ce que ça marche sans votre aide.

---

## Module 6 — Le suivi : savoir qui achète, qui revient, qui a besoin d'une relance

### Leçon

Un SaaS sans données, c'est un avion sans instruments. Le suivi minimal se fait en 3 feuilles (voir formation 4 pour l'automatisation complète) :

**Feuille 1 — VENTES** : chaque achat = une ligne (date, client, email, produit, montant, source). Remplie automatiquement par votre outil de paiement (Stripe/LS exportent, ou EmailJS ajoute la ligne).

**Feuille 2 — UTILISATION** : chaque usage de l'outil = une ligne (date, email, nb de générations). Ajoutée par la passerelle (n8n écrit dans Sheets). **L'usage est la vraie preuve de valeur** : un client qui utilise = un client satisfait ; un client qui n'utilise pas = un client à réactiver.

**Feuille 3 — PROSPECTS** : chaque lead/email reçu = une ligne (email, source, date, statut). C'est votre pipeline.

**Les 5 indicateurs d'un SaaS solo** (à regarder chaque semaine) :
1. **Ventes** : combien, quel montant, quelle source ?
2. **Taux de conversion** : visiteurs → acheteurs (≥ 1-2 % est correct au début).
3. **Utilisation** : % de clients qui ont utilisé l'outil la semaine de l'achat (l'objectif : > 50 %).
4. **Demandes de remboursement** : si > 5 %, le produit ne tient pas sa promesse.
5. **Demandes de support** : chaque question = une amélioration de page ou de produit.

**Le réflexe de la semaine 1** : contactez PERSONNELLEMENT chaque acheteur (« Merci, comment puis-je améliorer l'outil ? »). Les 10 premiers clients vous disent plus que 1 000 suppositions. Répondez en 24 h à tout email — c'est votre avantage face aux gros.

### Exemple réel

ScoreCoach (exemple) : chaque vente ajoute une ligne Ventes (source : LinkedIn / bouche-à-oreille / SEO) ; chaque utilisation ajoute une ligne Usage. Au bout d'un mois, la lecture des feuilles montre : la source LinkedIn convertit 3× mieux, et 40 % des acheteurs n'ont jamais utilisé l'outil → action : email de réactivation (automatique, 3 jours après l'achat : « 3 exemples d'utilisation ») et plus de contenu sur la source gagnante.

### Exercice pratique

1. Créez vos 3 feuilles (Ventes, Utilisation, Prospects) avec des formats stricts.
2. Branchez au moins 1 flux automatique (vente → ligne, ou usage → ligne).
3. Définissez vos 5 indicateurs et un format de relevé hebdomadaire (même manuel au début : 10 minutes le lundi).
4. Préparez votre email de bienvenue personnalisé aux 10 premiers clients.

---

## Module 7 — Lancer, améliorer, encaisser : le plan des 30 premiers jours

### Leçon

Le lancement n'est pas un événement, c'est un **processus de 30 jours** avec une priorité absolue chaque semaine :

**Semaine 1 — Valider (0 € de dépense)** :
- [ ] La promesse en une phrase est testée auprès de 5-10 personnes de la cible
- [ ] Page de vente en ligne (même brute)
- [ ] Paiement réel branché et testé (votre propre achat de test)
- [ ] 3 personnes ont vu la page et donné leur retour

**Semaine 2 — Construire** :
- [ ] L'outil fonctionne (entrée → IA → résultat), testé en navigation privée
- [ ] Livraison automatique vérifiée (email + accès)
- [ ] Feuilles de suivi en place
- [ ] Première version « imparfaite mais fonctionnelle » envoyée à 2 clients pilotes

**Semaine 3 — Vendre** :
- [ ] Le produit est annoncé (post LinkedIn/X : valeur d'abord, pas de pub)
- [ ] 10 emails personnalisés envoyés à des prospects directs (dont votre réseau)
- [ ] Chaque acheteur reçoit un email personnel de bienvenue
- [ ] Toutes les objections reçues sont ajoutées à la FAQ

**Semaine 4 — Itérer** :
- [ ] Lecture des 5 indicateurs
- [ ] 3 améliorations issues des retours réels (pas de suppositions)
- [ ] Re-publication + relance des prospects chauds
- [ ] Décision : continuer, pivoter ou arrêter (un échec rapide et appris vaut mieux qu'un succès imaginaire)

**Les 3 décisions de la semaine 4** (soyez brutal) :
1. **Des gens ont payé ?** → continuez, augmentez la distribution.
2. **Des gens ont utilisé l'outil (même sans payer) ?** → le problème est la vente : améliorez la page.
3. **Ni payé ni utilisé ?** → le problème est le produit : changez la promesse ou le segment — ne « poussez » pas un produit dont personne ne veut.

**Le piège n°5 : l'amélioration infinie**. « Encore une fonctionnalité et ça décollera » est la phrase qui tue les SaaS solo. Un produit vendable se reconnaît : 3 utilisateurs satisfaits. En dessous, on n'ajoute rien, on corrige ce qui bloque. **L'excellence, c'est une promesse tenue à 100 %, pas 50 fonctionnalités.**

### Exemple réel

Les 30 premiers jours d'un SaaS de fiches produit IA : S1, promesse testée sur 8 e-commerçants (2 sceptiques sur le prix → prix ajusté) ; S2, outil construit via n8n + clé API (aucune clé exposée) ; S3, 1 post LinkedIn + 10 emails personnalisés → 4 ventes, 2 utilisateurs actifs ; S4, indicateurs lus (conversion 1,3 %, 2 remboursements demandés → FAQ + démo vidéo ajoutées). Mois 2 : 11 ventes, 350 €, produit amélioré selon 3 retours réels.

### Exercice pratique

1. Écrivez votre plan des 30 jours (les 4 semaines, avec les cases ci-dessus).
2. Pour la semaine 1 : préparez vos 3 questions de validation (« Qu'est-ce qui te ferait acheter ? » / « Qu'est-ce qui te bloque ? »).
3. Identifiez vos 10 premiers prospects (votre réseau + les personnes qui ont déjà votre problème).
4. Notez la règle en gros : « Encaisse avant de perfectionner. »

---

## ✅ Checklist de fin de formation

- [ ] Mon produit tient en une phrase : QUI + BESOIN + RÉSULTAT + TEMPS
- [ ] Mon squelette en 6 pièces est dessiné (vente, paiement, livraison, outil, suivi, email)
- [ ] Ma page de vente est en ligne (structure en 8 sections)
- [ ] Le paiement encaisse réellement (test d'achat fait et vérifié)
- [ ] La livraison automatique fonctionne (email reçu, accès vérifié depuis un autre navigateur)
- [ ] Mon outil fonctionne de bout en bout (formulaire → IA → résultat)
- [ ] Ma clé API est protégée (passerelle n8n/Workers — jamais dans la page)
- [ ] Mes 3 feuilles de suivi sont en place (Ventes, Utilisation, Prospects)
- [ ] Mes 5 indicateurs sont définis
- [ ] Mon plan des 30 jours est écrit, semaine par semaine

**Résultat mesurable** : un SaaS en ligne, encaissant réellement, livrant automatiquement, avec suivi des ventes — construit en 2-4 semaines pour moins de 50 €/mois, et les premières ventes réelles réalisées (ou au minimum les premières validations client).

---

## 💰 Prix conseillés

| Formule | Contenu | Prix |
|---|---|---|
| **Pack PDF** | Les 7 modules + plan des 30 jours + checklists | **37 €** |
| **Pack complet** | Pack PDF + **les 6 prompts de génération IA prêts à copier** (page de vente, outil, formulaire, email de livraison, email de bienvenue, email de réactivation) + template du plan des 30 jours + 1 h de Q&A en visio | **57 €** |

**Note de vente** : c'est la formation « projet » du catalogue — les acheteurs ne paient pas un cours, ils paient leur prochain revenu. Le pack complet à 57 € se justifie car il vaut plus cher que n'importe quelle prestation de développement. C'est aussi le produit d'appel parfait pour vendre Agentia ensuite (module 7 = exactement la preuve de compétence).
