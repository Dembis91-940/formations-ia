# ⚙️ AUTOMATISATION IA — n8n & Make : récupérez 5 à 10 heures par semaine

> **Promesse mesurable** : à la fin, vous avez **3 automatisations déployées** (une de récupération d'emails, une de suivi client, une de reporting) qui vous rendent **5 à 10 heures par semaine** — pour un coût de quelques euros par mois.
>
> **Format** : pack PDF, 6 modules, ~5 h de lecture + montage des scénarios.
> **Cible** : indépendants, gérants de TPE, assistants — les « couteaux suisses » qui passent leur temps dans les emails, les tableurs et les relances.
> **Prérequis** : aucun code. Savoir utiliser un tableur et une boîte mail. La formation 2 (agents) est un plus mais pas obligatoire.
> **Durée** : 5 h sur 1 semaine.

---

## Module 1 — Le diagnostic : trouver vos 10 heures par semaine

### Leçon

Avant d'automatiser, il faut **mesurer**. La règle d'or : on n'automatise que ce qu'on a mesuré. Pendant 3 jours, chronométrez vos tâches répétitives. La plupart des gens découvrent 10-15 h/semaine de travail reproductible.

**La grille de diagnostic** :

| Tâche | Fréquence | Temps/session | Total/semaine | Répétitive ? (oui/non) | Automatisable ? |
|---|---|---|---|---|---|
| Tri des emails | 10×/jour | 5 min | ~3 h | Oui | Oui |
| Relances clients | 5×/semaine | 15 min | 1 h 15 | Oui | Oui |
| Saisie de données (tableur) | 3×/jour | 10 min | 2 h 30 | Oui | Oui |
| Création de devis | 2×/semaine | 40 min | 1 h 20 | Partiellement | Partiellement |
| ... | | | | | |

**Les 4 critères d'une bonne automatisation** (dans l'ordre) :
1. **Fréquence** : au moins une fois par jour, sinon le temps de montage n'est pas rentabilisé.
2. **Répétitivité** : la même logique à chaque fois (le « pourquoi » ne change pas).
3. **Règle claire** : on peut écrire la règle de décision en une phrase (« si aucun paiement après 7 jours → relance »).
4. **Coût d'erreur faible** : si l'automatisation se trompe, les dégâts sont minimes (ou elle passe par validation humaine).

**Le calcul de rentabilité** : temps économisé/semaine × 4,3 semaines × 12 mois = heures/an. À 30 €/h de valeur, une tâche de 1 h/semaine vaut ~1 550 €/an. **Une automatisation qui rend 2 h/semaine s'amortit en 1 à 2 mois** — le meilleur investissement à rendement immédiat d'une TPE.

### Le piège n°1 : l'automatisation du désordre

Automatiser un processus bancal = produire des erreurs plus vite. **Si le processus manuel n'est pas fiable, on ne l'automatise pas, on le simplifie d'abord** (modèles d'emails, tableurs standardisés, règles de nommage).

### Exemple réel

Un commercial chronomètre : 3 h/semaine de tri d'emails, 2 h de relances. Total : 5 h/semaine, soit ~260 h/an (≈ 7 800 € à 30 €/h). Les deux tâches ont des règles claires (« si email contient "devis" → dossier devis » ; « si devis envoyé il y a 10 jours sans réponse → relance »). Elles passent tous les critères. C'est le point de départ des modules 3 et 4.

### Exercice pratique

1. Pendant 3 jours, tenez le journal de vos tâches répétitives avec la grille ci-dessus.
2. Calculez vos heures/semaine et leur valeur annuelle.
3. Choisissez vos **3 priorités** (les meilleurs scores fréquence + répétitivité + règle claire). Ce sont vos 3 automatisations de la formation.

---

## Module 2 — Les deux outils : n8n vs Make, comment choisir

### Leçon

Deux leaders de l'automatisation no-code, deux philosophies :

**n8n** — open source, self-hosted ou cloud.
- ✅ Gratuit en self-hosted (Docker), data reste chez vous, 400+ intégrations, très bon pour les workflows techniques (webhooks, API, LLM).
- ✅ Idéal quand on veut brancher du code, des modèles IA, ou des intégrations maison.
- ⚠️ Courbe d'apprentissage un peu plus raide, interface « technique ».

**Make (ex-Integromat)** — SaaS, interface visuelle.
- ✅ Interface intuitive, excellent pour les débutants, très bon marché pour les petits volumes (plan gratuit ~1 000 opérations/mois, puis 9-16 $/mois).
- ✅ Puissant pour les scénarios « classiques » (emails, CRM, tableurs, notifications).
- ⚠️ Data transite par leur cloud, coût qui grimpe avec le volume.

**Comment choisir (règle simple)** :
- Débutant, intégrations standard (Gmail, Sheets, Notion, Slack) → **Make** pour démarrer vite.
- Technique, intégrations IA, contrôle total, gratuit, données sensibles → **n8n self-hosted**.
- **Combiner** : Make pour le quotidien simple, n8n pour le « gros » (agents IA, webhooks, données internes). Les deux s'interconnectent.

**Les briques communes aux deux outils** (le vocabulaire) :

| Brique | n8n | Make | Rôle |
|---|---|---|---|
| Déclencheur | Trigger | Module de déclenchement | Quand ça démarre (planning, email, webhook, formulaire) |
| Action | Node | Module d'action | Ce qui s'exécute (lire, écrire, envoyer) |
| Variable | `{{ $json.champ }}` | `{{champ}}` | La donnée qui circule entre les modules |
| Condition | nœud IF | Routeur | Branche selon une règle |
| Erreur | Error Trigger | Gestion d'erreurs | Que faire si ça casse |

**Le mapping des données — la compétence clé** : dans les deux outils, chaque module produit des données (nom, email, montant, date) et le module suivant les consomme via des variables. **Apprendre à lire ce que produit un module, c'est 50 % du métier.** Astuce : exécutez toujours un scénario en mode test avec des données réelles pour VOIR ce qui sort avant de brancher la suite.

### Exemple réel

Pour un indépendant qui débute : Make avec Gmail + Sheets + Slack (plan gratuit) pour le tri d'emails et les alertes. Pour son pipeline de veille IA : n8n self-hosted (gratuit, contrôle des données). Budget total : 0 € le premier mois, puis ~15 €/mois pour la montée en charge.

### Exercice pratique

1. Créez un compte sur les deux outils (gratuits) : n8n cloud ou Docker, et Make.
2. Dans Make, connectez Gmail (ou votre boîte) et Google Sheets via OAuth.
3. Dans n8n, connectez les mêmes services.
4. Testez un module « lire le dernier email » dans chaque outil et comparez l'expérience. Notez votre préférence et pourquoi.

---

## Module 3 — Automatisation n°1 : le tri et le classement des emails (le gain immédiat)

### Leçon

Objectif : chaque email entrant est **analysé, classé et traité selon des règles** — sans que vous ouvriez votre boîte pour trier.

**Le scénario de base (règles + filtres)** — 20 minutes dans Make ou n8n :

```
Déclencheur : « Nouvel email reçu » (Gmail)
   ↓
Règle 1 : l'expéditeur est dans ma liste de contacts prioritaires ?
   → Oui : notifier sur Slack/Telegram « URGENT : email de X »
   → Non : continuer
Règle 2 : l'objet contient "devis", "facture" ou "paiement" ?
   → Oui : copier dans le dossier "Finance" (label) + ligne dans Sheets "Suivi finances"
   → Non : continuer
Règle 3 : l'email contient un lien de réunion ou "RDV" ?
   → Oui : notifier + copier dans le label "RDV"
   → Non : continuer
Fin : archiver les emails classés (labels) pour que la boîte de réception reste vide
```

**Le scénario avancé (IA + classification intelligente)** — quand les règles fixes ne suffisent plus (emails ambigus, demandes variées) :

```
Déclencheur : nouvel email
   ↓
Nœud IA (LLM) : « Classe cet email dans l'une de ces catégories :
   [devis, support, facture, spam, information, autre].
   Réponds uniquement par le nom de la catégorie. »
   ↓
IF : selon la catégorie → action correspondante
   (devis → dossier + relance auto après 48 h ; support → ticket ; spam → corbeille)
```

**La règle de sécurité** : l'IA ne décide jamais seule d'une action irréversible (supprimer, payer). Pour le spam, mettez en corbeille + notification (vous validez), pas de suppression définitive automatique.

### Le piège : les faux positifs

Un email légitime marqué « spam » ou un client prioritaire ignoré = crédibilité endommagée. Toujours garder une **notification** de ce qui a été classé, et commencer en mode « labels + brouillons », jamais en mode destructif.

### Exemple réel

Un formateur indépendant reçoit 60 emails/jour. Son scénario : les emails contenant « formation », « inscription » ou « paiement » → label "Business" + ligne dans le suivi Sheets ; les autres → label "Lecture". La boîte de réception reste à zéro, il traite 2 fois par jour le label Business. Gain : 2 h 30/semaine. Coût : 0 € (plan gratuit).

### Exercice pratique

1. Montez le scénario de base (règles) sur votre boîte.
2. Testez avec 10 de vos vrais emails (mode test).
3. Si certains emails échappent aux règles, ajoutez le nœud IA de classification.
4. Faites tourner 3 jours en mode « labels seulement ». Ajustez les règles selon les cas vus.

---

## Module 4 — Automatisation n°2 : les relances clients qui n'oublient jamais

### Leçon

Objectif : **aucun devis, aucune facture, aucun client n'est plus jamais oublié** — les relances partent à la bonne date, avec le bon message, sans que vous y pensiez.

**Le scénario « relance de devis »** (le plus rentable des scénarios) :

```
Déclencheur : planifié, toutes les heures (ou sur événement)
   ↓
Lire la feuille "Devis" (Sheets/Excel) : lignes où :
   - statut = "ENVOYÉ"
   - date d'envoi > 10 jours
   - nombre de relances < 2
   ↓
Pour chaque ligne :
   → Envoyer l'email de relance n°1 (template personnalisé avec le numéro de devis)
   → Mettre à jour la ligne : statut = "RELANCE 1", date de relance = aujourd'hui
   ↓
(À 20 jours sans réponse) : relance n°2, ton différent, offre un créneau d'appel
   ↓
(À 30 jours) : notification humaine « devis à clôturer » — l'humain décide
```

**Les 3 règles d'or de la relance automatique** :
1. **Toujours un template humain** : personnalisé (nom, projet, référence), jamais « bonjour cher client ».
2. **Toujours une limite** : 2 relances max, puis on remonte à l'humain. Une relance infinie détruit la relation.
3. **Toujours un CTA clair** : une seule action demandée (répondre, choisir un créneau, confirmer le devis).

**Le même moteur pour d'autres relances** : paiement en retard (facture +7 jours), client inactif (plus de contact depuis 90 jours → email de réengagement), prospect (email reçu il y a 15 jours sans réponse → relance de valeur, pas de vente).

### Le piège : la relance qui tue la relation

Un client qui a déjà répondu reçoit une relance automatique → il se sent ignoré. **Le statut doit être mis à jour dès qu'un humain intervient** : toute réponse réelle (email, appel) passe la ligne en « TRAITÉ » avant que la relance ne parte. Astuce technique : le scénario ne relance que les lignes au statut exact « ENVOYÉ » ou « RELANCE 1 » — jamais les autres.

### Exemple réel

Un freelance envoie 15 devis/mois. Avant : il oubliait la moitié des relances, perdant des contrats. Après : son scénario relance systématiquement à J+10 et J+20, avec templates personnalisés. Résultat : +2 à +3 devis conclus par mois (≈ +30 % de conversion), pour 30 minutes de montage initiales. Le client qui paye cette formation se la rembourse sur sa première relance.

### Exercice pratique

1. Créez votre feuille "Devis" (colonnes : client, email, montant, date d'envoi, statut, nb relances).
2. Montez le scénario relance (J+10 / J+20 / notification à J+30).
3. Testez avec 2 lignes réelles (mode test d'abord, puis envoi réel sur vos propres emails).
4. Ajoutez le scénario « facture impayée » (même logique, ton adapté).

---

## Module 5 — Automatisation n°3 : le reporting automatique (le tableau de bord qui se remplit tout seul)

### Leçon

Objectif : **les chiffres de votre activité arrivent tout seuls, chaque semaine, dans un format prêt à lire** — sans copier-coller, sans tableur à remplir.

**Le scénario « rapport hebdomadaire »** :

```
Déclencheur : tous les lundis à 9 h
   ↓
Récupérer les données (selon votre activité) :
   - Ventes : lignes ajoutées dans la feuille "Ventes" (montant, date, source)
   - Emails : volume de la semaine (Gmail/API)
   - Devis : statuts des lignes (feuille "Devis")
   - Site : visites (si formulaire connecté ou analytics)
   ↓
Nœud IA : « Résume ces données en un rapport de 15 lignes :
   chiffre d'affaires de la semaine, variation vs semaine précédente,
   3 faits marquants, 1 recommandation. »
   ↓
Envoyer le rapport : email à vous-même + copie dans le dossier "Reporting"
   ↓
(Option) : mettre à jour le tableau de bord Sheets "Suivi activité"
```

**Le tableau de bord « vivant »** : une feuille Sheets qui se remplit automatiquement à chaque événement (chaque vente ajoute une ligne, chaque email important ajoute une ligne). C'est la base de données de votre activité — et c'est elle qu'on analyse, pas les emails.

**Le pattern « capture + consolidation »** (le plus utile en TPE) :
1. **Capture** : chaque événement (vente, devis, email, appel) ajoute une ligne dans sa feuille, en automatique.
2. **Consolidation** : une fois par semaine, le rapport lit toutes les feuilles et produit le résumé.
3. **Décision** : vous lisez le rapport en 5 minutes et décidez.

### Le piège : les données sales

Une automatisation qui écrit des données non normalisées (dates en 3 formats, montants avec ou sans TVA) produit des rapports faux. **Règle : définissez le format exact de chaque colonne au moment de la capture** (date = JJ/MM/AAAA, montant = HT, statut = liste fermée). L'automatisation qui écrit est aussi importante que celle qui lit.

### Exemple réel

Un vendeur de formations : chaque vente (paiement reçu) ajoute une ligne à "Ventes" (date, produit, montant, source) ; chaque email de lead ajoute une ligne à "Leads" ; chaque lundi, le rapport compare la semaine à la précédente et envoie : CA, nb ventes, taux de transformation, top produit. Il lit son activité en 5 minutes au lieu de 1 h de reconstitution.

### Exercice pratique

1. Définissez vos 3 feuilles de capture (ex. : Ventes, Leads, Devis) avec des formats stricts.
2. Montez le scénario de capture pour au moins un événement (le plus fréquent de votre activité).
3. Montez le rapport hebdomadaire (lecture + résumé IA + envoi email).
4. Faites tourner 2 semaines, puis améliorez le prompt de résumé avec ce que vous avez appris.

---

## Module 6 — Fiabiliser : erreurs, coûts, sécurité, et le passage à l'échelle

### Leçon

Une automatisation « en production » se juge sur sa fiabilité, pas sur sa démo. Les 5 pratiques non négociables :

**1. La gestion des erreurs.** Dans Make : onglet « Gestion d'erreurs » sur chaque module (ignorer / arrêter / reprendre) + module « Notification d'erreur » (email ou Telegram). Dans n8n : « Continue On Fail » + « Error Trigger ». Règle : **toute erreur doit arriver quelque part où un humain la voit**, dans l'heure.

**2. La notification d'échec.** Un scénario qui échoue en silence pendant 5 jours, c'est 5 jours de promesses non tenues. La première chose à configurer : « si le scénario échoue → email/Telegram à moi ». 2 minutes, non négociable.

**3. Le coût.** Suivez vos opérations : Make (plan gratuit ≈ 1 000 opérations/mois ; un scénario d'emails consomme 5-20 opérations par exécution — faites le calcul avant d'activer). n8n self-hosted : gratuit, mais le coût des API LLM (si utilisées) s'additionne. **Règle : connaître le coût de chaque scénario avant de l'activer**, puis vérifier le relevé mensuel.

**4. La sécurité des données.** OAuth pour les connexions (jamais de mot de passe dans les modules), pas de données clients sensibles dans les brouillons d'erreur, et révoquer les accès inutilisés. Pour les données sensibles : n8n self-hosted.

**5. La revue mensuelle.** Une heure par mois : quels scénarios tournent ? Lequel ne sert plus ? Quel volume réel ? Quelles règles à ajuster ? Les automatisations, comme les employés, doivent avoir un entretien mensuel.

### Le passage à l'échelle : du « je » au « système »

Quand vos 3 automatisations tournent : ajoutez une **vision globale** (le tableau de bord du module 5 devient votre cockpit hebdomadaire) puis étendez **par famille** : la relance devis devient relance générique (devis + factures + prospects) ; le tri d'emails devient routage vers des agents spécialisés. Vous construisez un **système**, pas une collection de scénarios.

### Le piège final : l'automatisation pour l'automatisation

Un scénario qui fait gagner 10 minutes mais coûte 2 h de maintenance par mois est une perte. **Règle de suppression** : si un scénario n'a pas sauvé plus d'1 h/semaine après 2 mois, on le supprime ou on le simplifie. Le but n'est pas d'avoir beaucoup d'automatisations, c'est d'avoir du temps libre.

### Exemple réel

6 mois après le début : un indépendant a 5 scénarios actifs (tri emails, relance devis, relance factures, rapport hebdo, capture leads). Coût : 0 € (plans gratuits, pas d'API LLM). 8 h/semaine rendues. Revue mensuelle : 1 scénario supprimé (inutile), 2 ajustés (nouvelles catégories d'emails). Le système est stable et il connaît son coût exact : 0 €.

### Exercice pratique

1. Configurez la notification d'échec sur vos 3 scénarios. Testez-la (cassez volontairement un module).
2. Calculez le coût mensuel estimé de chaque scénario (opérations × fréquence).
3. Révisez les accès connectés : retirez ce qui ne sert pas.
4. Planifiez votre revue mensuelle (date + liste des scénarios + 3 questions).

---

## ✅ Checklist de fin de formation

- [ ] Diagnostic réalisé : mes tâches répétitives mesurées (h/semaine)
- [ ] 3 priorités choisies selon les 4 critères (fréquence, répétitivité, règle, coût d'erreur)
- [ ] Outil choisi (Make et/ou n8n) et services connectés (OAuth)
- [ ] Scénario 1 : tri/classement des emails, testé 3 jours
- [ ] Scénario 2 : relance devis (J+10/J+20/limite J+30), testé avec données réelles
- [ ] Scénario 3 : capture + rapport hebdomadaire, 2 semaines de données
- [ ] Notification d'échec configurée et testée sur les 3 scénarios
- [ ] Coût mensuel estimé et suivi
- [ ] Feuilles de capture avec formats stricts (dates, montants, statuts)
- [ ] Revue mensuelle planifiée

**Résultat mesurable** : 3 automatisations en production, 5 à 10 h/semaine récupérées, aucun devis/facture/client oublié, un rapport hebdomadaire qui arrive tout seul — pour moins de 15 €/mois.

---

## 💰 Prix conseillés

| Formule | Contenu | Prix |
|---|---|---|
| **Pack PDF** | Les 6 modules + grille de diagnostic + checklists | **27 €** |
| **Pack complet** | Pack PDF + **5 scénarios Make/n8n prêts à importer** (tri emails, relance devis, relance factures, rapport hebdo, capture leads) + modèles d'emails de relance (6 templates) + 1 h de Q&A en visio | **47 €** |

**Note de vente** : la promesse « 5-10 h/semaine » est la plus vendeuse du catalogue (le ROI se calcule en 1 minute : à 30 €/h, 5 h/semaine = 7 800 €/an). Le pack complet avec scénarios pré-montés est le best-seller potentiel : il promet un résultat en 1 journée, pas en 1 mois.
