# Installation

Connecter Leadbay à Claude prend environ une minute. La méthode recommandée est l'**extension `.dxt`** — téléchargez un fichier et installez-le. Si vous préférez automatiser la configuration, l'**installateur en une commande** est une alternative.

La configuration avancée et les autres clients sont couverts dans le [README Leadbay MCP](https://github.com/leadbay/leadclaw#install).

{% hint style="info" %}
Le serveur MCP utilise **votre** compte Leadbay, donc toute action prise par Claude est équivalente à ce que vous auriez fait vous-même dans l'application.
{% endhint %}

---

## Ce dont vous avez besoin

- Un compte Leadbay ([inscrivez-vous ici](https://leadbay.ai/) si vous n'en avez pas)
- Un assistant IA qui supporte MCP — Claude, Claude Code ou Codex
- Une minute

---

## Installer l'extension `.dxt` (recommandé)

La configuration la plus simple : téléchargez un seul fichier d'extension et installez-le.

### Étape 1 — Télécharger la dernière extension

Ouvrez la [page des releases LeadClaw](https://github.com/leadbay/leadclaw/releases/) et récupérez le dernier fichier `.dxt` (cherchez un nom du type `leadbay-X.Y.Z.dxt` dans la section **Assets** de la release la plus récente).

Sauvegardez-le dans un endroit facile à retrouver — votre dossier Téléchargements fonctionne.

---

### Étape 2 — Installer l'extension

Dans Claude, allez dans :

**Settings → Extensions → Advanced → Install extension**

Sélectionnez le fichier `leadbay-X.Y.Z.dxt` que vous avez téléchargé à l'étape 1.

Un dialogue s'ouvre avec les détails de l'extension. Cliquez sur **Install**, puis confirmez avec **Install** à nouveau.

Une fois installée, basculez l'extension sur **Enabled**.

---

### Étape 3 — Se connecter avec Leadbay

La première fois que Claude appelle un outil Leadbay, il déclenche un flux **Se connecter avec Leadbay** en un clic :

1. Une page de connexion Leadbay s'ouvre dans votre navigateur
2. Connectez-vous (ou confirmez votre session existante)
3. Cliquez sur **Approuver** pour accorder à Claude l'accès à votre compte
4. L'onglet du navigateur se ferme tout seul et Claude poursuit la conversation

C'est tout — aucun jeton à générer, copier, coller ou renouveler. La connexion est limitée à votre compte et vous pouvez la révoquer à tout moment depuis **Paramètres → Applications connectées** dans Leadbay.

{% hint style="info" %}
Si vous avez accès aux instances US et UE de Leadbay, connectez-vous sur l'instance que vous voulez que Claude utilise. Vous pouvez changer plus tard en vous déconnectant de l'extension Leadbay et en vous reconnectant sur l'autre instance.
{% endhint %}

---

### Étape 4 — Autoriser les outils

Leadbay propose deux familles d'outils :

| Famille | Ce qu'elle contient | Permission recommandée |
|--------|--------------|------------------------|
| **Lecture seule** | Récupère leads, lenses, profils, contacts, profil de goût, quota d'enrichissement — ne modifie jamais rien | **Toujours autoriser** |
| **Écriture / suppression** | Qualifie des leads, enrichit des contacts, ajoute des notes, importe des leads, journalise la prospection, affine l'audience | **Toujours autoriser** |

Les deux familles peuvent être autorisées en permanence sans risque, car le Leadbay MCP est **limité à votre compte** — il n'y a rien de destructeur au niveau de la plateforme. Régler les deux sur « toujours autoriser » permet à Claude de travailler en continu sans vous interrompre à chaque appel.

Pour configurer : dans l'écran **Configure** de l'extension Leadbay, réglez **Always allow** pour le groupe d'outils en lecture seule et pour le groupe en écriture/suppression.

---

## Alternative — installateur en une commande

Vous préférez automatiser la configuration, ou vous utilisez **Claude Code** ou **Cursor** ? Une seule commande installe Leadbay et vous connecte. Il vous faut [Node.js](https://nodejs.org) 22 ou plus récent.

```bash
npx -y -p @leadbay/mcp@latest installer
```

Cela ouvre un assistant guidé qui détecte vos clients installés (Claude Desktop, Claude Code, Cursor), ajoute Leadbay à ceux que vous choisissez, et lance le flux **Se connecter avec Leadbay**.

Pour retirer Leadbay plus tard de tous les clients configurés par l'installateur :

```bash
npx -y -p @leadbay/mcp@latest installer --uninstall
```

---

## Essayez

Ouvrez une conversation et demandez :

> *Récupère les meilleurs leads du jour et dis-moi lesquels valent la peine d'être ouverts ce matin.*

Claude appellera `leadbay_pull_leads`, `leadbay_get_lead_profile`, et consorts — et répondra avec une liste courte et qualifiée.

Quelques autres prompts qui fonctionnent d'emblée :

- *Recherche acme.com — est-ce un bon fit pour nous ?*
- *Affine mon audience pour cibler les entreprises de l'UE qui recrutent des commerciaux.*
- *Je viens d'envoyer un email à Jane chez Acme. Journalise-le comme action de prospection.*

La liste complète des outils et les workflows recommandés se trouvent dans le [README LeadClaw](https://github.com/leadbay/leadclaw#tools).

---

## Utiliser Leadbay avec Claude Desktop

Claude Desktop charge les outils MCP plus lentement que Cowork, donc quelques précautions supplémentaires aident.

Après avoir installé l'extension Leadbay, **quittez complètement et relancez Claude Desktop** (Cmd-Q sur Mac, puis rouvrez — pas seulement fermer la fenêtre). Ouvrez un nouveau chat et attendez environ **30 secondes** avant d'envoyer votre premier message. Cela laisse à Claude le temps de charger les outils Leadbay.

Si votre premier message reçoit une réponse du type *« Je ne vois aucun outil Leadbay »* ou *« Je ne trouve pas Leadbay dans votre configuration »*, pas d'inquiétude — les outils sont encore en train de se charger. Envoyez n'importe quel deuxième message (même juste *« réessaie »*) et Claude les détectera. À partir de là, le reste de votre session fonctionne normalement.

---

## Mise à jour

Pour l'**extension `.dxt`**, quand une nouvelle release sort, répétez l'**Étape 1** (télécharger le nouveau `.dxt`) et l'**Étape 2** (Install extension). Claude remplace l'ancienne version sur place ; votre connexion reste valide, vous n'avez donc pas à vous ré-authentifier.

L'**installateur en une commande** exécute toujours la dernière version — il n'y a rien à mettre à jour.

---

## Dépannage

| Symptôme | Solution |
|---------|-----|
| Claude dit « non authentifié » ou erreurs 401 | Votre connexion a peut-être expiré ou été révoquée. Déclenchez n'importe quel outil Leadbay à nouveau et Claude relancera le flux **Se connecter avec Leadbay** |
| Les outils n'apparaissent pas après l'installation | Vérifiez que l'extension est bien sur **Enabled** dans Settings → Extensions |
| Les outils apparaissent mais Claude ne les appelle pas | Ouvrez **Configure** et basculez les groupes d'outils sur **Always allow** |
| Connecté, mais « montre-moi les leads » renvoie une liste vide | Vous êtes bien connecté — il n'y a simplement rien à afficher pour l'instant. Demandez *« montre-moi mes lenses »* pour confirmer quelle audience est active et basculer si besoin, ou vérifiez que vous êtes sur la bonne instance (US vs UE) |
| Mauvaise instance (aucun lead / erreurs 404) | Déconnectez-vous de l'extension Leadbay et reconnectez-vous sur la bonne instance (US ou UE) |
| Autre problème | Signalez un bug sur [github.com/leadbay/leadclaw/issues](https://github.com/leadbay/leadclaw/issues) |
