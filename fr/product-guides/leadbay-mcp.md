# Leadbay MCP pour Claude

Donnez à Claude (Desktop, Code et Cowork) un accès direct à votre compte Leadbay. Une fois installé, Claude peut récupérer des leads, les qualifier, enrichir des contacts, journaliser les actions de prospection — en utilisant vos vraies données, avec vos permissions.

Ce guide couvre l'installation dans **Claude Cowork** via l'extension prête à l'emploi `.mcpb`. Les autres clients (Claude Desktop, Cursor, Claude Code) sont couverts dans le [README Leadbay MCP](https://github.com/leadbay/leadclaw#install).

{% hint style="info" %}
Le serveur MCP est open source et se trouve sur [github.com/leadbay/leadclaw](https://github.com/leadbay/leadclaw). Il utilise **votre** compte Leadbay, donc toute action prise par Claude est équivalente à ce que vous auriez fait vous-même dans l'application.
{% endhint %}

---

## Ce dont vous avez besoin

- Un compte Leadbay ([inscrivez-vous ici](https://leadbay.ai/) si vous n'en avez pas)
- Claude Cowork (ou tout client Claude qui supporte les extensions MCP)
- Deux minutes

---

## Étape 1 — Télécharger la dernière extension

Ouvrez la [page des releases LeadClaw](https://github.com/leadbay/leadclaw/releases/) et récupérez le dernier fichier `.mcpb` (cherchez un nom du type `leadbay-X.Y.Z.mcpb` dans la section **Assets** de la release la plus récente).

Sauvegardez-le dans un endroit facile à retrouver — votre dossier Téléchargements fonctionne.

---

## Étape 2 — Générer un bearer token Leadbay

L'extension a besoin d'un token pour parler à Leadbay en votre nom.

1. Ouvrez un terminal
2. Lancez :

   ```bash
   npx -y @leadbay/mcp@latest login --email vous@votreentreprise.com --region fr
   ```

   - Remplacez `vous@votreentreprise.com` par votre email de connexion Leadbay
   - Utilisez `--region fr` si vous vous êtes inscrit sur l'instance française, `--region us` pour l'instance US

3. Votre mot de passe vous sera demandé (utilisé une seule fois pour s'authentifier, puis jeté)
4. La CLI imprime un **bearer token** (commence par `u.`). Copiez-le — vous le collerez à l'étape 4

{% hint style="warning" %}
Traitez le token comme un mot de passe. Quiconque a ce token peut agir sur votre compte Leadbay.
{% endhint %}

---

## Étape 3 — Installer l'extension dans Cowork

Dans Claude Cowork, allez dans :

**Settings → Extensions → Advanced → Install extension**

Sélectionnez le fichier `leadbay-X.Y.Z.mcpb` que vous avez téléchargé à l'étape 1.

Un dialogue s'ouvre avec les détails de l'extension. Cliquez sur **Install**, puis confirmez avec **Install** à nouveau.

Une fois installée, basculez l'extension sur **Enabled**.

---

## Étape 4 — Configurer le token

Toujours dans **Settings → Extensions**, trouvez Leadbay dans la liste et cliquez sur **Configure**.

- Collez votre bearer token dans le champ `LEADBAY_TOKEN`
- Définissez le champ `LEADBAY_REGION` pour correspondre à celui utilisé lors du login (`us` ou `fr`)
- Sauvegardez

---

## Étape 5 — Autoriser les outils

Leadbay livre deux saveurs d'outils :

| Saveur | Ce qu'elle contient | Permission recommandée |
|--------|---------------------|------------------------|
| **Read-only** | Récupère leads, lenses, profils, contacts, taste profile, quota d'enrichissement — ne change jamais rien | **Always allow** |
| **Write / delete** | Qualifie des leads, enrichit des contacts, ajoute des notes, importe des leads, journalise des actions de prospection, affine l'audience | **Always allow** |

Les deux saveurs peuvent être en always-allow sans risque car le Leadbay MCP est **scopé à votre compte** — rien de destructif au niveau plateforme. Mettre les deux en « always allow » permet à Claude de circuler sans vous interrompre pour une permission à chaque appel.

Pour configurer : dans l'écran **Configure** de l'extension Leadbay, mettez **Always allow** à la fois pour le groupe d'outils read-only et pour le groupe write/delete.

---

## Essayez-le

Ouvrez une conversation Cowork et demandez :

> *Récupère les meilleurs leads du jour et dis-moi lesquels ouvrir en priorité ce matin.*

Claude appellera `leadbay_pull_leads`, `leadbay_get_lead_profile` et leurs amis — et répondra avec une shortlist courte et qualifiée.

Quelques prompts supplémentaires qui marchent dès le départ :

- *Recherche acme.com — est-ce que c'est un fit pour nous ?*
- *Affine mon audience pour me focaliser sur les entreprises européennes qui recrutent des commerciaux.*
- *Je viens d'envoyer un email à Jane chez Acme. Journalise-le comme action de prospection.*

La liste complète des outils et des workflows recommandés est dans le [README LeadClaw](https://github.com/leadbay/leadclaw#tools).

---

## Mettre à jour

Quand une nouvelle release sort, répétez l'**étape 1** (téléchargez le nouveau `.mcpb`) et l'**étape 3** (Install extension). Cowork remplace l'ancienne version en place ; votre token et vos permissions restent configurés.

---

## Utiliser Leadbay avec Claude Desktop

Claude Desktop est plus lent que Cowork à charger les outils MCP, donc quelques précautions supplémentaires aident.

Après avoir installé l'extension Leadbay, **quittez complètement Claude Desktop et relancez-le** (Cmd-Q sur Mac, puis rouvrez — ne vous contentez pas de fermer la fenêtre). Ouvrez un nouveau chat et attendez environ **30 secondes** avant d'envoyer votre premier message. Cela laisse à Claude le temps de charger les outils Leadbay.

Si votre premier message reçoit une réponse du genre *« Je ne vois pas d'outils Leadbay »* ou *« Je ne trouve pas Leadbay dans votre configuration »*, pas d'inquiétude — les outils sont encore en train de se charger. Envoyez n'importe quel deuxième message (même juste *« réessaie »*) et Claude les prendra en compte. À partir de là, le reste de votre session fonctionne normalement.

---

## Dépannage

| Symptôme | Solution |
|----------|----------|
| Claude dit « non authentifié » ou erreurs 401 | Le token a peut-être expiré. Refaites l'**étape 2** pour en générer un nouveau et collez-le dans **Configure** |
| Les outils n'apparaissent pas dans Cowork | Vérifiez que l'extension est bien sur **Enabled** dans Settings → Extensions |
| Les outils apparaissent mais Claude ne les appelle pas | Ouvrez **Configure** et passez les groupes d'outils en **Always allow** |
| Mauvaise région (pas de leads / 404s) | Confirmez que `LEADBAY_REGION` correspond à l'endroit où vous vous êtes inscrit (`us` vs `fr`) |
| Autre problème | Ouvrez un bug sur [github.com/leadbay/leadclaw/issues](https://github.com/leadbay/leadclaw/issues) |
