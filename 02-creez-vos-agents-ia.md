# 🤖 CRÉEZ VOS AGENTS IA — n8n + Hermes, la stack qui travaille pour vous

> **Promesse mesurable** : à la fin, vous avez **2 agents IA fonctionnels et déployés** (un agent « assistant » et un agent « automatiseur ») qui exécutent des tâches à votre place — sans vous, sans supervision, sans coder.
>
> **Format** : pack PDF, 6 modules, ~5 h de lecture + mise en pratique.
> **Cible** : indépendants, TPE et techniciens qui veulent que l'IA « fasse », pas qu'elle « discute ».
> **Prérequis** : savoir naviguer, copier-coller, et un compte gratuit sur n8n (cloud) ou Docker installé (self-hosted). La formation 1 (LLM) est recommandée mais pas obligatoire.
> **Durée** : 5 h réparties sur 1 semaine.

---

## Module 1 — Qu'est-ce qu'un agent IA (et ce que ce n'est pas)

### Leçon

Un **agent IA** = un LLM + des **outils** + une **boucle** (il décide, agit, observe, recommence). La différence avec un simple chat :

| | Chat | Agent |
|---|---|---|
| Déclenchement | Vous écrivez | Un événement (email, formulaire, heure, fichier) |
| Action | Il répond | Il exécute (envoie un email, modifie un fichier, met à jour un CRM) |
| Supervision | Vous relisez tout | Règles + validation sur les actions sensibles |
| Répétition | Vous recommencez | Il tourne 24/7 |

Un agent, c'est **un collaborateur numérique avec un poste précis**. Pas un robot omniscient : un exécutant spécialisé, cadré par des instructions claires et des garde-fous.

Les 3 briques d'un agent :

1. **L'instruction** (le « poste ») : rôle, mission, périmètre, interdits, format de sortie. C'est 80 % de la qualité.
2. **Les outils** : ce qu'il peut faire (lire un email, chercher, écrire un fichier, appeler une API, poster sur un réseau).
3. **Le déclencheur** : quand il se met au travail (toutes les heures, à chaque nouvel email, à chaque nouvelle ligne dans un tableur).

**Architecture type d'un agent pro** :

```
Déclencheur (Trigger)
      ↓
Lecture des données (email, tableur, formulaire, base)
      ↓
Traitement LLM (analyse, rédaction, décision)
      ↓
Action (email sortant, mise à jour, enregistrement, notification)
      ↓
Journalisation (log de ce qu'il a fait — obligatoire pour faire confiance)
```

### Exemple réel

Un agent « réponse devis » chez un artisan : chaque email entrant est analysé → s'il ressemble à une demande de devis, l'agent extrait le besoin, rédige une réponse type personnalisée et la place dans le brouillon (pas d'envoi automatique). L'artisan valide en 30 secondes au lieu de rédiger 15 minutes. Résultat : 15 minutes → 30 secondes, et aucune demande oubliée.

### Exercice pratique

1. Listez 5 tâches répétitives de votre semaine (email, mise à jour de tableur, veille, relance, classement de fichiers).
2. Pour chacune, notez : déclencheur / données / traitement / action / fréquence.
3. Choisissez celle qui vous coûte le plus de temps : ce sera votre premier agent (module 5).

---

## Module 2 — La stack : n8n (le chef d'orchestre) + Hermes (le cerveau)

### Leçon

Deux outils, deux rôles complémentaires :

**n8n** est un **orchestrateur de workflows** (open source, self-hosted ou cloud). Il connecte des applications entre elles (email, tableurs, API, bases de données, Slack, etc.) via des nœuds visuels. C'est lui qui : écoute les déclencheurs, transporte les données, enchaîne les étapes, gère les erreurs et les plannings.

**Hermes** (Hermes Agent, de Nous Research) est un **agent personnel** exécutable en ligne de commande : il reçoit une mission, réfléchit, utilise ses outils (terminal, fichiers, recherche web, envoi d'emails, etc.) et produit un résultat. C'est lui qui fait le « travail de cerveau » : rédiger, analyser, décider, exécuter sur votre machine.

**Pourquoi cette combinaison est celle d'un pro** :

- n8n gère les **événements et les intégrations** (le « quand » et le « où ») — il vit dans le cloud ou sur un serveur.
- Hermes gère la **tâche intellectuelle et locale** (le « quoi ») — il vit sur votre machine, accède à vos fichiers, votre terminal, vos outils.
- n8n appelle Hermes comme un service (webhook, ligne de commande via SSH) et récupère son résultat.

**L'alternative simple pour démarrer** : n8n seul, avec un nœud LLM intégré (OpenAI/Claude/Grok). Hermes intervient quand la tâche exige un raisonnement multi-étapes, des outils locaux (vos fichiers, votre terminal) ou une boucle de réflexion.

### Installation réelle (30 minutes)

**Option A — n8n cloud (le plus rapide)** : rendez-vous sur n8n.io, créez un compte gratuit (crédits offerts), choisissez « Create workflow ». C'est suffisant pour tous les exercices de cette formation.

**Option B — n8n self-hosted avec Docker (le plus puissant, gratuit)** :

```bash
# Installer Docker (macOS : https://docs.docker.com/desktop/install/mac/)
# Puis, dans un terminal :
docker volume create n8n_data
docker run -d --name n8n \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  n8nio/n8n
# Ouvrir http://localhost:5678 dans le navigateur
```

**Option C — Hermes (pour la partie « cerveau »)** : installer l'agent Hermes sur votre machine (macOS/Linux) via la méthode officielle du projet (voir la documentation Nous Research). Une fois installé, testez-le :

```bash
hermes run "Résume les 3 tâches les plus urgentes dans mon dossier ~/Documents"
```

Si la commande répond : vous avez un agent local opérationnel.

### Piège n°1 à connaître

Les clés API (OpenAI, Anthropic, etc.) se configurent dans n8n et Hermes **une seule fois**, et se stockent chiffrées. Ne les collez jamais dans un nœud en clair ni dans un fichier partagé.

### Exercice pratique

1. Installez n8n (option A ou B) et Hermes (option C).
2. Dans n8n, créez un workflow vide et ajoutez un nœud « Manual Trigger » puis un nœud « AI Agent » (ou LLM) avec votre clé. Testez : « Dis bonjour et décris ta mission. »
3. Lancez `hermes run "Explique en 2 phrases ce que tu peux faire"`.
4. Vous avez maintenant les deux briques de la stack. Notez dans un fichier `ma-stack.md` : versions, URL, clés configurées (sans les clés !).

---

## Module 3 — Votre premier agent dans n8n (pas à pas, 45 min)

### Leçon

On construit un agent **« assistant de lecture »** : il lit le contenu d'une URL ou d'un fichier, le résume, et envoie le résumé par email. C'est le « hello world » des agents, mais déjà 100 % utile.

**Étape 1 — Le déclencheur** : ajoutez un nœud « Schedule Trigger » (tous les jours à 8 h) OU « Manual Trigger » pour tester. Un agent pro a toujours un déclencheur automatique.

**Étape 2 — La lecture** : ajoutez un nœud « HTTP Request » avec la méthode GET sur l'URL à lire, ou un nœud « Read/Write Files from Disk » si le contenu est un fichier local. Résultat : le contenu brut arrive dans le workflow.

**Étape 3 — Le cerveau** : ajoutez un nœud « AI Agent » (ou « Basic LLM Chain ») configuré avec votre clé OpenAI/Anthropic/Grok. Dans le champ « Prompt/System » :

```
Tu es un assistant de lecture. Résume le contenu reçu en 5 puces maximum,
en français, en gardant les chiffres et les décisions importantes.
Si le contenu est vide, réponds simplement : CONTENU VIDE.
```

Le contenu du nœud précédent est injecté automatiquement via `{{ $json.content }}`.

**Étape 4 — L'action** : ajoutez un nœud « Email » (SMTP ou Gmail OAuth). Sujet : `Résumé du [date]`. Corps : le résumé du nœud LLM via `{{ $json.output }}`.

**Étape 5 — La robustesse** : ajoutez un nœud « IF » après la lecture : si `content` est vide → nœud « NoOp » (ne rien faire) ; sinon → suite. Et activez « Continue On Fail » sur les nœuds critiques. Un agent qui échoue doit **échouer proprement**, pas spammer d'erreurs.

**Étape 6 — Le test** : exécutez le workflow manuellement une fois (bouton « Execute Workflow »), vérifiez l'email reçu, puis activez le déclencheur planifié.

### Exemple réel

Le workflow complet en un schéma :

```
Schedule (8h) → HTTP Request (lire le briefing du jour) → IF (non vide ?)
→ AI Agent (résumé 5 puces) → Email (résumé à vous-même) → Log
```

C'est exactement ce que fait un « briefing quotidien » automatisé : un email prêt à 8 h 05, chaque matin, coût ~0,01 € par exécution.

### Exercice pratique

1. Reproduisez le workflow ci-dessus avec votre propre source (un site d'actualité, votre veille, un document).
2. Testez avec 2 contenus différents, dont un volontairement vide (pour vérifier le nœud IF).
3. Faites varier le prompt système : ajoutez « sous forme de liste avec titres en gras » puis observez la différence.
4. Activez le déclencheur planifié. L'agent tourne maintenant sans vous.

---

## Module 4 — Donner des outils à votre agent : la différence « agent » vs « chat »

### Leçon

Un agent n'est puissant que par ses **outils**. n8n propose deux familles :

1. **Les nœuds d'intégration** (200+) : Gmail, Google Sheets, Notion, Slack, Airtable, Stripe, Telegram, etc. Chacun = une capacité (lire/écrire) que vous branchez en quelques clics avec OAuth (connexion officielle sans partager de mot de passe).
2. **Les outils LLM** (mode « AI Agent » avancé) : le modèle peut **choisir lui-même** quel nœud appeler selon la question. C'est le vrai comportement « agent » : on lui donne un ensemble d'outils et une mission, il décide du chemin.

**Le pattern « RAG » (Récupération augmentée)** — le secret des agents qui répondent avec VOS données :

```
Question → recherche dans votre base (Google Sheets, Notion, fichiers) → 
contexte trouvé → LLM rédige la réponse avec CE contexte → réponse
```

Concrètement dans n8n : nœud « Google Sheets — Get Many » (lire votre base clients/produits/FAQs) → « AI Agent » avec le contenu en contexte → réponse. L'agent répond sur vos données réelles, pas sur ses connaissances générales.

**Le pattern « mémoire »** : pour que l'agent se souvienne des conversations, ajoutez un nœud de stockage (Google Sheets, Notion, SQLite) où chaque échange est enregistré, et lisez l'historique au début du workflow. Sans ça, chaque exécution repart de zéro.

**Le pattern « validation humaine »** : sur les actions sensibles (envoi, paiement, publication), faites passer l'action par une **approbation** : l'agent prépare (brouillon, proposition), l'humain valide, l'action part. C'est la différence entre un assistant fiable et un robot dangereux.

### Exemple réel

Un agent « support client » pour une formation en ligne : chaque email entrant → recherche dans la FAQ (Sheets) → si la réponse existe, l'agent répond directement ; sinon, il crée un ticket Notion et prévient l'humain. Résultat : 60 % des questions courantes traitées sans intervention, les autres triées et priorisées. Avec la validation humaine sur l'envoi au début, puis sans (une fois les réponses vérifiées).

### Exercice pratique

1. Créez une feuille Google Sheets « Base de connaissances » avec 5 questions/réponses de votre activité.
2. Ajoutez à votre workflow du module 3 : lecture de la feuille → réponse basée sur cette base.
3. Ajoutez un pattern « validation humaine » sur une action (ex. : le résumé part en brouillon, pas en envoi direct).
4. Testez : posez une question dont la réponse est dans la feuille, puis une question hors base. Observez la différence.

---

## Module 5 — Passer à Hermes : l'agent qui travaille sur votre machine

### Leçon

Quand la tâche dépasse l'intégration (raisonner sur vos fichiers, exécuter des commandes, rédiger un livrable complet, gérer plusieurs sources), on passe la main à un agent **local** : Hermes. Deux façons de l'utiliser :

**Mode 1 — En direct (interactif)** : vous lui donnez une mission, il l'exécute avec ses outils et vous rend compte.

```bash
hermes run "Analyse le dossier ~/Documents/devis et classe les 5 meilleures opportunités, avec un email de relance pour chacune"
```

**Mode 2 — En automatique (programmé)** : Hermes tourne en tâche planifiée (cron) et produit des livrables à heure fixe. Exemple concret : chaque matin à 7 h, un cron job fait la veille, la résume et dépose le rapport dans un dossier — vous le lisez au café.

```bash
# Exemple de tâche planifiée (cron) :
0 7 * * * hermes run "Fais la veille de la nuit sur les outils IA, écris un résumé de 10 lignes dans ~/Documents/veille/"
```

**Mode 3 — En binôme avec n8n** : n8n détecte un événement (email reçu, formulaire rempli) et **appelle Hermes** via un webhook ou une commande distante ; Hermes exécute le travail de fond sur la machine (accès fichiers, terminal, outils) et renvoie le résultat que n8n envoie où il faut. C'est la stack complète de cette formation :

```
Événement (email/formulaire/planning)
   ↓ n8n (orchestration, intégrations)
Hermes (raisonnement + outils locaux + livrables)
   ↓
Résultat → n8n → Gmail/Sheets/Notion/Slack (action finale)
```

**La règle des responsabilités** : n8n = routage et intégrations ; Hermes = intelligence et actions locales. Chacun fait ce qu'il fait le mieux.

### Les garde-fous obligatoires d'un agent pro

1. **Instructions claires** (mission, périmètre, interdits, format de sortie).
2. **Validation sur les actions irréversibles** (envoi, paiement, suppression, publication).
3. **Journalisation** : chaque exécution laisse une trace (rapport, log, fichier daté).
4. **Test sur données réelles** avant de passer en automatique, puis supervision la première semaine.
5. **Limites de coût** : surveillez la consommation API la première semaine (quelques centimes à quelques euros par mois pour un usage individuel).

### Exemple réel

Le workflow « compte-rendu de réunion » : à la fin d'une visio, l'enregistrement est déposé dans un dossier → n8n détecte le fichier → Hermes le transcrit et rédige le compte-rendu (décisions, actions, responsables) → n8n envoie le PDF à tous les participants. Sans transcription : 30 minutes de notes à la main. Avec : 0, avec un compte-rendu uniforme et daté.

### Exercice pratique

1. Donnez à Hermes une mission réelle sur vos fichiers : *« Classe les fichiers de ~/Documents/en-attente et propose un plan d'action »*.
2. Configurez une tâche planifiée (cron) pour une veille quotidienne qui écrit son rapport dans un dossier.
3. Schématisez sur papier votre futur workflow complet n8n → Hermes (déclencheur, mission, action finale).
4. Vérifiez vos 5 garde-fous sur ce schéma. Complétez ce qui manque.

---

## Module 6 — Déployer, surveiller, fiabiliser : de l'agent « démo » à l'agent « en production »

### Leçon

La différence entre un hobby et un système fiable tient en 4 pratiques :

**1. La gestion d'erreurs** : dans n8n, activez « Continue On Fail » sur les nœuds secondaires, et ajoutez un nœud « Error Trigger » qui vous notifie (Telegram/email) quand le workflow échoue. Un agent muet qui échoue depuis 3 jours, c'est un agent qui n'existe plus.

**2. Les tests de non-régression** : gardez 3-5 scénarios de test (dont un cas limite : contenu vide, format inattendu). Après chaque modification du workflow, exécutez les 5 tests avant de re-activer. C'est la même discipline qu'un développeur.

**3. La journalisation** : faites écrire un log à chaque exécution (fichier CSV ou Sheets : date, statut, coût, erreur éventuelle). Une fois par semaine, lisez le log : coût total, taux d'échec, choses à corriger.

**4. L'évolution** : un agent n'est jamais fini. Planifiez une revue mensuelle : la mission est-elle toujours exacte ? Les interdits suffisent-ils ? Le prompt a-t-il besoin d'être affiné avec les cas vus ce mois-ci ? Les meilleurs agents sont **nourris des erreurs passées**.

**Le coût réel d'un agent** (à connaître avant de déployer) : pour un usage personnel, comptez **0,01-0,10 € par exécution** selon le modèle et la longueur des textes (gpt-4o-mini / claude-haiku : quelques centimes ; gros modèle : davantage). 30 exécutions/jour = 0,30-3 €/jour. Choisissez le plus petit modèle qui fait le travail.

### Les 5 signes qu'un agent est « en production »

1. Il tourne sur un déclencheur automatique (pas manuel).
2. Il échoue proprement et vous prévient.
3. Il journalise chaque exécution.
4. Quelqu'un a validé ses actions sensibles la première semaine.
5. Son coût mensuel est connu et suivi.

### Exemple réel

Le « pipeline de veille » d'un indépendant, 3 mois après lancement : 2 workflows n8n + 1 cron Hermes, ~2 €/mois, 4 h/semaine rendues. Le journal mensuel montre : 96 % d'exécutions réussies, 3 incidents (API en panne, format de source changé) tous détectés par les notifications. La revue mensuelle a ajouté 2 nouvelles sources et 1 interdit au prompt.

### Exercice pratique

1. Appliquez les 4 pratiques (erreurs, tests, journal, revue) à VOS 2 agents.
2. Créez votre journal d'exécution (feuille CSV ou Sheets) et faites tourner une semaine.
3. Fin de semaine : calculez votre coût réel et votre temps gagné. Consignez le résultat.
4. Planifiez votre revue mensuelle (date + 3 questions à vous poser).

---

## ✅ Checklist de fin de formation

- [ ] n8n installé (cloud ou Docker) et testé
- [ ] Hermes installé et fonctionnel (`hermes run "..."` répond)
- [ ] Agent 1 déployé : workflow de lecture/résumé avec déclencheur planifié
- [ ] Agent 2 déployé : agent avec base de connaissances (Sheets) et validation humaine
- [ ] Pattern RAG compris et appliqué sur vos données
- [ ] Les 5 garde-fous appliqués sur chaque agent
- [ ] Gestion d'erreurs + notification d'échec configurées
- [ ] Journal d'exécution en place, 1 semaine de données
- [ ] Coût mensuel estimé et noté
- [ ] Revue mensuelle planifiée

**Résultat mesurable** : au moins une tâche répétitive (1-5 h/semaine) est désormais exécutée par vos agents, avec un coût inférieur à quelques euros par mois et une trace de chaque exécution.

---

## 💰 Prix conseillés

| Formule | Contenu | Prix |
|---|---|---|
| **Pack PDF** | Les 6 modules + checklists + schémas d'architecture | **37 €** |
| **Pack complet** | Pack PDF + **5 templates de workflows n8n prêts à importer** (veille, briefing quotidien, réponse devis, support FAQ, compte-rendu) + 10 prompts d'agent (system prompts pro) + accès au fichier de journalisation CSV | **67 €** |

**Note de vente** : c'est la formation la plus « outillage » du catalogue — le pack complet se vend sur le gain de temps immédiat (les templates s'importent en 5 min). Le PDF seul à 37 € reste rentable pour qui veut construire lui-même. Cette formation est aussi le meilleur cheval de Troie vers Agentia (module 6 = exactement ce que l'on vend aux PME).
