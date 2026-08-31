# 🧠 MAÎTRISEZ LES LLM — GPT, Claude, Grok

> **Promesse mesurable** : à la fin, vous savez choisir le bon modèle pour chaque tâche, rédiger un prompt qui donne le bon résultat du premier coup, et automatiser vos tâches répétitives avec les API — vous gagnez **5 heures par semaine** sur votre travail documentaire.
>
> **Format** : pack PDF, 7 modules, ~4 h de lecture + exercices.
> **Cible** : professionnels (commerciaux, rédacteurs, assistants, techniciens) qui utilisent déjà ChatGPT « comme Google » et veulent passer au niveau supérieur.
> **Prérequis** : savoir utiliser un navigateur et copier-coller. Zéro code requis (l'API est optionnelle, module 7).
> **Durée** : 4 h (2 h de théorie + 2 h d'exercices), à faire en 1 semaine.

---

## Module 1 — Qu'est-ce qu'un LLM, vraiment (et pourquoi ça change vos prompts)

### Leçon

Un LLM (Large Language Model) est un modèle de **prédiction de texte statistique** entraîné sur des centaines de milliards de tokens. Il ne « sait » pas : il calcule, à chaque mot, la probabilité du prochain mot le plus plausible. C'est la raison de ses deux forces et de son défaut majeur :

- **Force 1** : il a absorbé une partie immense de la connaissance publique (jusqu'à sa date de coupe). Il est excellent pour reformuler, résumer, traduire, structurer.
- **Force 2** : il comprend l'intention derrière vos mots, pas seulement les mots. D'où l'importance du **contexte**.
- **Défaut** : il **hallucine** quand il ne sait pas. Il préfère inventer une réponse plausible plutôt que dire « je ne sais pas ». Parfois, la date de coupe le rend obsolète.

Conséquences pratiques :

1. **Ne demandez jamais un fait précis sans vérification** (chiffres, dates, citations, articles de loi). Demandez d'abord, vérifiez ensuite.
2. **Donnez le contexte complet** : rôle, objectif, public, format, contraintes. Un LLM sans contexte est un stagiaire sans brief.
3. **Le modèle détermine la qualité de base**, mais **le prompt détermine 80 % du résultat**. Un bon prompt sur un modèle moyen bat un mauvais prompt sur le meilleur modèle.

### Les 4 grands modèles, quand les utiliser

| Modèle | Forces | À éviter | Coût d'accès |
|---|---|---|---|
| **GPT-4o / GPT-4.1** (OpenAI) | Raisonnement solide, écosystème API le plus complet, outils (fonctions, vision) | Tâches triviales (cher) | 20 $/mois (ChatGPT Plus) ; API payante |
| **Claude** (Anthropic) | Écriture longue de qualité (rapports, code, analyses), respect des instructions longues, fenêtre de contexte énorme (200k-1M) | Tâches très courtes et répétitives | 20 $/mois (Claude Pro) ; API payante |
| **Grok** (xAI) | Actualité récente (données temps réel via X), ton direct, bon marché en API | Rédaction longue nuancée | Inclus X Premium ; API bon marché |
| **Modèles open source** (Llama, Mistral, Qwen via Ollama) | Gratuit, données privées restent chez vous, hors-ligne | Tâches complexes, français moyen selon les modèles | Gratuit (serveur local) |

**Règle du pro** : le meilleur modèle n'existe pas — il existe le **bon modèle pour la tâche**. Longue rédaction → Claude. Tâches courtes et structurées → GPT. Actualité → Grok. Confidentialité → local.

### Exemple réel

Mauvais prompt : *« Résume ce texte. »*
Bon prompt : *« Tu es un assistant commercial. Résume ce compte-rendu de réunion en 5 puces, en français, en gardant les décisions et les responsables. Si une décision est ambiguë, écris "(à clarifier)". »*

Le deuxième donne un résultat exploitable directement, le premier donne un pavé générique.

### Exercice pratique

1. Prenez un texte professionnel que vous avez sous la main (email long, rapport, article).
2. Faites-le résumer par GPT, Claude et Grok avec le même prompt « pauvre ».
3. Faites-le résumer avec le même prompt « riche » (rôle + objectif + format + contrainte).
4. Comparez les 4 résultats : notez la différence entre les modèles et entre les prompts. Écrivez 3 lignes sur ce que vous retenez.

---

## Module 2 — La conversation : votre premier outil de travail

### Leçon

Un LLM en chat n'est pas une calculatrice, c'est un **collaborateur avec mémoire de session**. Utilisez cette mémoire :

1. **Ouvrez une session par projet** (pas un méli-mélo). La mémoire de la session, c'est le contexte gratuit.
2. **Corrigez plutôt que reformulez** : au lieu de réécrire tout le prompt, dites *« non, garde le ton mais raccourcis les phrases de moitié »*. Le modèle itère sur la session.
3. **Demandez des questions avant la production** : *« Avant d'écrire, pose-moi les 3 questions qui changeraient tout. »* Un pro pose 30 secondes de questions, gagne 20 minutes de correction.
4. **Exigez des sources ou un signal d'incertitude** : *« Si tu n'es pas sûr d'un chiffre, écris [VÉRIFIER] à la place. »*

### Les 7 rôles qui marchent

Démarrez vos prompts par un rôle précis. Voici les 7 rôles les plus rentables au quotidien :

1. **Le réviseur** : « Corrige ce texte : orthographe, grammaire, style. Propose 2 versions : une formelle, une directe. »
2. **Le traducteur** : « Traduis en anglais commercial, pas littéral. »
3. **L'analyste** : « Quels sont les 3 risques de ce contrat/projet ? Justifie. »
4. **Le formateur** : « Explique-moi X comme à un débutant, avec une analogie. »
5. **Le contradicteur** : « Trouve les 5 faiblesses de mon argumentation. »
6. **Le rédacteur de brief** : « À partir de cette idée, écris un brief complet de 10 lignes pour un prestataire. »
7. **Le synthétiseur** : « Transforme cette discussion en compte-rendu avec décisions, actions et responsables. »

### Exemple réel

Un technicien doit préparer un point d'avancement : il colle la conversation complète du support dans la session, puis demande : *« Tu es mon assistant. Résume cette conversation client en : contexte, problème, actions faites, prochaine étape. Ajoute une section "risque si on ne fait rien". »* Résultat : un compte-rendu prêt en 2 minutes au lieu de 30.

### Exercice pratique

Prenez votre dernière réunion (ou un échange client) et produisez : un compte-rendu avec le rôle 7, puis une version « email au client » de 8 lignes maximum. Mesurez le temps gagné.

---

## Module 3 — Le prompt en 6 briques (framework C.O.N.T.E.X.T.)

### Leçon

Un prompt professionnel se construit comme un brief. Mémorisez les 6 briques :

| Lettre | Brique | Question à se poser | Exemple |
|---|---|---|---|
| **C** | Contexte | De quoi parle-t-on ? | « Nous sommes une TPE de 6 personnes » |
| **O** | Objectif | Quel est le livrable ? | « un argumentaire de vente » |
| **N** | Nature | Quel format ? | « un document d'une page, 6 sections » |
| **T** | Ton | Quel style ? | « direct, sans jargon, tutoiement » |
| **E** | Exemple | Un modèle de sortie ? | « comme cet email que je joins » |
| **X** | eXigences | Contraintes, interdits ? | « sans promesse de résultat garanti, max 400 mots » |

Le **E** (exemple) est la brique la plus puissante : montrer un exemple vaut mieux que décrire. Le **X** est la plus négligée : sans interdits, le modèle part dans son sens.

### Le framework avancé : le prompt « en trois temps »

Pour les tâches importantes, ne demandez pas la production directe :

1. **Phase 1 — Compréhension** : « Voici le sujet. Reformule ce que tu as compris et pose-moi tes questions. »
2. **Phase 2 — Plan** : « Voici les réponses. Propose un plan de [livrable] avec le contenu de chaque section en une ligne. »
3. **Phase 3 — Production** : « Le plan est validé. Rédige maintenant. »

Cela coûte 3 messages au lieu d'un, mais élimine 90 % des résultats à jeter.

### Exemple réel

Prompt complet : *« C. Je suis consultant indépendant, je vends des formations IA aux PME. O. Rédige un email de relance pour un prospect qui a reçu mon devis il y a 10 jours sans réponse. N. Email de 120 mots max. T. Courtois, direct, sans agressivité. E. [collez un email que vous avez déjà envoyé et qui a marché]. X. Pas de rabais, une seule relance mentionnée, CTA clair : un créneau de 15 min. »*

### Exercice pratique

1. Écrivez un prompt C.O.N.T.E.X.T. complet pour une tâche réelle de votre semaine (email, rapport, analyse).
2. Faites la version « trois temps ».
3. Comparez les résultats avec votre prompt habituel. Conservez le gagnant dans un fichier `mes-prompts.md` que vous allez construire tout au long de la formation.

---

## Module 4 — Récupérer de l'information : téléverser des fichiers

### Leçon

Les modèles modernes (GPT-4o, Claude, Grok) acceptent des **fichiers joints** : PDF, images, tableurs, code. C'est votre raccourci n°1 : ne recopiez plus jamais un document, **téléversez-le**.

Ce que ça débloque :

- **PDF** : résumé, extraction des points clés, recherche de clauses, comparaison de deux contrats.
- **Tableurs (CSV/XLSX)** : analyse de données, détection d'anomalies, préparation de rapports.
- **Images** : lecture de captures d'écran, OCR, description d'un schéma, lecture d'un graphique.
- **Code** : explication, débogage, traduction d'un langage à un autre.

Limites à connaître : la **date de coupe** (le modèle ne connaît pas le futur), la **taille** (certains modèles limitent le volume), et la **confidentialité** (les données envoyées à un service cloud ne sont pas « chez vous » — vérifiez les CGU pour des données sensibles, et utilisez un modèle local dans ce cas).

### La technique du « double questionnement »

Sur un document long, ne demandez jamais tout d'un coup. Deux passes :

1. **Passe panoramique** : « Résume ce document en 10 puces. Quelles sont les 3 idées principales ? »
2. **Passe chirurgicale** : « Dans la section 3, quels sont exactement les montants et les échéances ? »

La passe 2 est beaucoup plus fiable quand elle s'appuie sur la passe 1 (le modèle sait déjà où chercher).

### Exemple réel

Un gérant reçoit un contrat de 40 pages d'un fournisseur. Il téléverse le PDF : *« Résume en 10 puces, puis liste toutes les clauses qui m'engagent financièrement ou dans la durée, avec le numéro de page de chacune. »* En 5 minutes, il a la carte des risques — et les pages à montrer à son avocat.

### Exercice pratique

1. Prenez un PDF professionnel que vous avez (devis, contrat, rapport) et téléversez-le.
2. Faites la passe panoramique puis la passe chirurgicale.
3. Vérifiez une information précise de la passe 2 en ouvrant le PDF à la page indiquée. Notez dans `mes-prompts.md` le prompt qui a donné la meilleure précision.

---

## Module 5 — Générer : emails, posts, rapports, traductions

### Leçon

La génération est le cœur de l'usage pro. Les 4 grands types de production, avec leur recette :

**1. L'email (la recette la plus rentable)**
Toujours fournir : destinataire, relation (prospect/client/collègue), objectif, ton, longueur, CTA. Et **toujours relire et personnaliser** : un email 100 % généré se sent à 100 mètres.

**2. Le post LinkedIn / X**
Fournir : sujet, promesse, longueur (X : < 280 caractères ; LinkedIn : 150-250 mots), ton, CTA, et 1-3 « hooks » au choix. Le hook est la première ligne : c'est elle qui décide du scroll ou du clic.

**3. Le rapport / compte-rendu**
Technique du « document à trous » : demandez le squelette (sections + questions), remplissez les données vous-même, puis demandez la rédaction complète. Vous gardez le contrôle des faits, le modèle gagne le temps de rédaction.

**4. La traduction**
Précisez toujours « traduction adaptée, pas littérale » et le registre (commercial, technique, familier). Les modèles traduisent mieux que 90 % des humains sur les textes professionnels — et c'est gratuit.

### Les 5 erreurs qui font un résultat « robot »

1. Prompt trop court sans contexte → texte générique.
2. Pas d'exemple → style par défaut du modèle.
3. Pas d'interdit → des phrases vides (« dans le monde d'aujourd'hui »).
4. Demander « parfait » sans itération → on jette au lieu de corriger.
5. Copier-coller sans relire → fautes, erreurs factuelles, ton faux.

**Règle d'or** : le LLM produit une **première version**. Le pro passe 30 % du temps à demander, 70 % à diriger les corrections.

### Exemple réel

Prompt : *« Écris un email de 100 mots à un client qui a acheté ma formation il y a 3 mois : je propose un rappel gratuit de 20 min pour l'aider à appliquer. Ton : utile, pas commercial. CTA : 3 créneaux proposés. Interdit : mot "relance", emojis. »* Résultat : un email d'entretien de client, pas de spam.

### Exercice pratique

Générez : (1) un email de suivi de devis, (2) un post LinkedIn sur votre métier avec 3 hooks au choix, (3) la traduction anglaise de votre offre. Corrigez chaque version en 2 itérations. Conservez les 3 prompts gagnants.

---

## Module 6 — Les pièges : hallucination, biais, données sensibles

### Leçon

Un utilisateur avancé connaît les limites mieux que les capacités. Les 5 pièges :

**1. L'hallucination** — le modèle invente avec aplomb (chiffres, citations, articles de loi, références). Antidote : demandez des sources, exigez « [VÉRIFIER] » quand incertain, vérifiez les faits critiques vous-même. Ne demandez JAMAIS à un LLM un montant, une date limite ou une clause juridique sans vérification externe.

**2. La date de coupe** — le modèle ne connaît pas le présent. Pour de l'actualité : Grok (temps réel), ou activez la recherche web si l'outil le propose. Vérifiez toujours ce qui date de moins de 2 ans.

**3. Les biais** — le modèle reproduit les biais de ses données d'entraînement (stéréotypes, angles morts culturels). Antidote : demandez explicitement plusieurs points de vue : « Donne aussi la vision opposée. »

**4. La confidentialité** — ne mettez jamais dans un chat public ou une API sans accord : données clients identifiables, mots de passe, documents stratégiques non publiés, secrets industriels. Pour le sensible : modèle local (Ollama), ou un abonnement avec clause de non-utilisation des données (Claude Pro / API avec « zero data retention »).

**5. La surconfiance** — le résultat est fluide donc il paraît vrai. Antidote : traitez chaque sortie comme un brouillon d'un stagiaire brillant mais faillible.

### La checklist anti-hallucination (à coller dans vos prompts sensibles)

> « Tu n'es pas autorisé à inventer. Pour chaque chiffre, citation, date ou référence : écris [VÉRIFIER] si tu n'es pas certain à 95 %. À la fin, liste les 3 informations les plus risquées à vérifier. »

### Exemple réel

Un étudiant demande à ChatGPT un résumé de la loi qui s'applique à son projet, avec les articles cités. Le modèle produit un texte impeccable... avec deux articles inexistants. Le réflexe pro : croiser avec le site officiel (legifrance.gouv.fr) avant toute utilisation. Le LLM a gagné 30 minutes de rédaction, l'humain garde la responsabilité du contenu.

### Exercice pratique

1. Posez au modèle une question factuelle précise (date, chiffre, loi) sans lui demander de vérifier. Puis la même question avec la checklist anti-hallucination.
2. Comparez : où sont les [VÉRIFIER] ?
3. Classez les données de votre activité en 3 catégories : « OK à envoyer », « OK avec précautions », « jamais » (ex. : mots de passe, données clients).

---

## Module 7 — Passer à l'API : automatiser vos tâches répétitives (optionnel, sans code requis)

### Leçon

L'interface chat est manuelle. **L'API transforme le LLM en service automatique** : votre boîte mail, votre CRM ou un script peut appeler le modèle à la demande. C'est ce qui se cache derrière tous les « agents » et automatisations modernes.

Le principe : une requête HTTP avec votre clé, vous recevez la réponse du modèle. Les fournisseurs (OpenAI, Anthropic, xAI) offrent tous la même logique : `model`, `messages` (rôle + contenu), `temperature` (créativité 0-2, défaut 1). Le prix se compte en tokens (≈ 750 mots).

**Votre premier appel (OpenAI, 5 minutes)** :
1. Créez un compte sur platform.openai.com, ajoutez un crédit (5-10 $ suffisent pour tester des semaines).
2. Générez une clé API (Settings → API keys).
3. Copiez ce script dans un fichier `test-api.py` (Python 3, installer avec `pip install openai`) :

```python
from openai import OpenAI
client = OpenAI(api_key="VOTRE_CLE")

reponse = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "system", "content": "Tu résumes des emails en 3 puces, en français."},
        {"role": "user", "content": "Résume : [COLLEZ VOTRE EMAIL ICI]"}
    ],
    temperature=0.3
)
print(reponse.choices[0].message.content)
```

4. Lancez `python3 test-api.py`. Si le terminal affiche le résumé : **félicitations, vous venez d'automatiser une tâche**. Ce code, branché sur votre boîte mail (via n8n, IFTTT, Zapier ou Make), tourne sans vous.

**Sécurité de la clé** : une clé API, c'est un mot de passe. Ne la partagez jamais, ne la collez jamais dans un chat public, ne la mettez jamais dans un fichier envoyé. Stockez-la dans un gestionnaire de secrets (Keychain sur Mac, gestionnaire de mots de passe) ou un fichier `.env` jamais commité.

### Exemple réel

Un indépendant reçoit 30 emails de devis par semaine. Il branche n8n : chaque email entrant → appel API → résumé en 3 puces → le résumé arrive dans sa messagerie. Coût : ~0,01 $ par email, soit 0,30 $/semaine. Gain : 1 h 30 de lecture. **Le retour sur investissement d'une API se compte en centimes.**

### Exercice pratique

1. Créez votre compte OpenAI (ou Anthropic/xAI), ajoutez un crédit minimal, générez une clé.
2. Exécutez le script ci-dessus sur un vrai email.
3. Identifiez **une** tâche répétitive de votre semaine (résumé, traduction, reformulation) et notez comment vous la brancheriez sur une API. C'est votre premier projet d'automatisation.

---

## ✅ Checklist de fin de formation

- [ ] Je sais différencier les 4 grands modèles et choisir selon la tâche
- [ ] J'utilise les rôles et la mémoire de session dans mes chats
- [ ] Je construis mes prompts avec les 6 briques C.O.N.T.E.X.T.
- [ ] Je fais la méthode « trois temps » pour les tâches importantes
- [ ] Je téléverse des fichiers et fais les deux passes (panoramique/chirurgicale)
- [ ] J'ai généré et corrigé : 1 email, 1 post LinkedIn, 1 traduction
- [ ] J'ai ma checklist anti-hallucination dans mes prompts sensibles
- [ ] J'ai classé mes données en 3 catégories de confidentialité
- [ ] Mon fichier `mes-prompts.md` contient au moins 5 prompts gagnants réutilisables
- [ ] J'ai fait mon premier appel API (même minimal) : `python3 test-api.py` fonctionne

**Résultat mesurable** : une tâche documentaire qui vous prenait 1 h vous prend désormais 10-15 min, et vous avez une bibliothèque de prompts réutilisables.

---

## 💰 Prix conseillés

| Formule | Contenu | Prix |
|---|---|---|
| **Pack PDF** | Les 7 modules + checklist | **27 €** |
| **Pack complet** | Pack PDF + `mes-prompts.md` (50 prompts pro prêts à copier) + 10 templates d'emails + 1 h de Q&A en visio | **47 €** |

**Note de vente** : le pack PDF seul justifie 15 € minimum ; à 27 €, il se positionne en « outil de travail » (pas un cours), ce qui justifie le prix face à la masse de contenu gratuit. Le pack complet à 47 € porte le vrai chiffre d'affaires : chaque vente complète = presque 2× le pack simple, pour un coût marginal nul.
