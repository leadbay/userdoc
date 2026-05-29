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
- Une minute

---

## Étape 1 — Télécharger la dernière extension

Ouvrez la [page des releases LeadClaw](https://github.com/leadbay/leadclaw/releases/) et récupérez le dernier fichier `.mcpb` (cherchez un nom du type `leadbay-X.Y.Z.mcpb` dans la section **Assets** de la release la plus récente).

Sauvegardez-le dans un endroit facile à retrouver — votre dossier Téléchargements fonctionne.

---

## Étape 2 — Installer l'extension dans Cowork

Dans Claude Cowork, allez dans :

**Settings → Extensions → Advanced → Install extension**

Sélectionnez le fichier `leadbay-X.Y.Z.mcpb` que vous avez téléchargé à l'étape 1.

Un dialogue s'ouvre avec les détails de l'extension. Cliquez sur **Install**, puis confirmez avec **Install** à nouveau.

Une fois installée, basculez l'extension sur **Enabled**.

---

## Étape 3 — Se connecter avec Leadbay

La première fois que Claude appelle un outil Leadbay, il déclenche un flux **Se connecter avec Leadbay** en un clic :

1. Une page de connexion Leadbay s'ouvre dans votre navigateur
2. Connectez-vous (ou confirmez votre session existante)
3. Cliquez sur **Approuver** pour donner à Claude l'accès à votre compte
4. L'onglet du navigateur se ferme tout seul et Claude poursuit la conversation

Et voilà — aucun token à générer, copier, coller ou faire tourner. La connexion est scopée à votre compte et vous pouvez la révoquer à tout moment depuis **Settings → Connected apps** dans Leadbay.

{% hint style="info" %}
Si vous avez accès aux deux instances de Leadbay (US et EU), connectez-vous sur celle que vous voulez que Claude utilise. Vous pouvez changer plus tard en vous déconnectant depuis l'extension Leadbay dans Cowork et en vous reconnectant sur l'autre instance.
{% endhint %}

---

## Étape 4 — Autoriser les outils

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

Quand une nouvelle release sort, répétez l'**étape 1** (téléchargez le nouveau `.mcpb`) et l'**étape 2** (Install extension). Cowork remplace l'ancienne version en place ; votre connexion reste valide, donc pas besoin de vous ré-authentifier.

---

## Utiliser Leadbay avec Claude Desktop

Claude Desktop est plus lent que Cowork à charger les outils MCP, donc quelques précautions supplémentaires aident.

Après avoir installé l'extension Leadbay, **quittez complètement Claude Desktop et relancez-le** (Cmd-Q sur Mac, puis rouvrez — ne vous contentez pas de fermer la fenêtre). Ouvrez un nouveau chat et attendez environ **30 secondes** avant d'envoyer votre premier message. Cela laisse à Claude le temps de charger les outils Leadbay.

Si votre premier message reçoit une réponse du genre *« Je ne vois pas d'outils Leadbay »* ou *« Je ne trouve pas Leadbay dans votre configuration »*, pas d'inquiétude — les outils sont encore en train de se charger. Envoyez n'importe quel deuxième message (même juste *« réessaie »*) et Claude les prendra en compte. À partir de là, le reste de votre session fonctionne normalement.

---

## Dépannage

| Symptôme | Solution |
|----------|----------|
| Claude dit « non authentifié » ou erreurs 401 | Votre connexion a peut-être expiré ou été révoquée. Déclenchez n'importe quel outil Leadbay et Claude vous reproposera le flux **Se connecter avec Leadbay** |
| Les outils n'apparaissent pas dans Cowork | Vérifiez que l'extension est bien sur **Enabled** dans Settings → Extensions |
| Les outils apparaissent mais Claude ne les appelle pas | Ouvrez **Configure** et passez les groupes d'outils en **Always allow** |
| Mauvaise instance (pas de leads / 404s) | Déconnectez-vous depuis l'extension Leadbay et reconnectez-vous sur la bonne instance (US ou EU) |
| Autre problème | Ouvrez un bug sur [github.com/leadbay/leadclaw/issues](https://github.com/leadbay/leadclaw/issues) |
