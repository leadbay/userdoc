# Installation

Connecter Leadbay à Claude prend environ une minute. Il y a trois façons de se connecter — choisissez celle qui correspond à votre client :

- **Option A — Connecteur hébergé :** collez une URL, rien à installer. Idéal pour **Claude Desktop** et **ChatGPT**.
- **Option B — Installateur en une commande :** un assistant guidé. Idéal pour **Claude Desktop**, **Claude Code** et **Cursor**.
- **Option C — Extension `.dxt` manuelle :** téléchargez et installez à la main. Requis pour **Claude Cowork**.

La configuration avancée et les autres clients sont couverts dans le [README Leadbay MCP](https://github.com/leadbay/leadclaw#install).

{% hint style="info" %}
Le serveur MCP utilise **votre** compte Leadbay, donc toute action prise par Claude est équivalente à ce que vous auriez fait vous-même dans l'application.
{% endhint %}

---

## Ce dont vous avez besoin

- Un compte Leadbay ([inscrivez-vous ici](https://leadbay.ai/) si vous n'en avez pas)
- Un assistant IA qui supporte MCP — Claude Desktop, Claude Cowork, Claude Code, Cursor ou ChatGPT
- Une minute

---

## Option A — Connecteur hébergé (sans installation)

La façon la plus rapide : Leadbay héberge un serveur MCP, vous ajoutez donc une URL de connecteur sans rien à télécharger, mettre à jour ou maintenir. Choisissez l'URL qui correspond à votre instance Leadbay :

| Votre instance Leadbay | URL du connecteur |
|---|---|
| UE / France | `https://leadbay-mcp-prod.fly.dev/fr/mcp` |
| US | `https://leadbay-mcp-prod.fly.dev/mcp` |

{% hint style="info" %}
Vous ne savez pas sur quelle instance vous êtes ? La plupart des comptes sont en UE/France — commencez par l'URL `/fr/mcp`. Si la connexion ne trouve pas votre compte, utilisez l'URL US.
{% endhint %}

**Dans Claude Desktop :**

1. Ouvrez **Settings → Connectors → Add custom connector**.
2. Collez l'URL de votre instance et confirmez.
3. La première fois que Claude utilise un outil Leadbay, une page **Se connecter avec Leadbay** s'ouvre dans votre navigateur — connectez-vous et cliquez sur **Approuver**.

**Dans ChatGPT :**

1. Ouvrez **Settings → Apps → Add app**.
2. Collez la même URL et suivez l'invite de connexion.

Aucun jeton à copier ou renouveler. Vous pouvez révoquer l'accès à tout moment depuis **Paramètres → Applications connectées** dans Leadbay.

---

## Option B — Installateur en une commande

Vous préférez une installation locale, ou vous utilisez **Claude Code** ou **Cursor** ? Une seule commande installe Leadbay et vous connecte. Il vous faut [Node.js](https://nodejs.org) 22 ou plus récent.

```bash
npx -y -p @leadbay/mcp@latest installer
```

Cela ouvre un assistant guidé qui détecte vos clients installés (Claude Desktop, Claude Code, Cursor), ajoute Leadbay à ceux que vous choisissez, et lance le flux **Se connecter avec Leadbay**.

Pour retirer Leadbay plus tard de tous les clients configurés par l'installateur :

```bash
npx -y -p @leadbay/mcp@latest installer --uninstall
```

---

## Option C — Extension `.dxt` manuelle (Cowork)

Claude Cowork installe les outils MCP à partir d'un fichier d'extension téléchargé. Utilisez cette méthode pour Cowork (elle fonctionne aussi pour Claude Desktop).

### Étape 1 — Télécharger la dernière extension

Ouvrez la [page des releases LeadClaw](https://github.com/leadbay/leadclaw/releases/) et récupérez le dernier fichier `.dxt` (cherchez un nom du type `leadbay-X.Y.Z.dxt` dans la section **Assets** de la release la plus récente).

Sauvegardez-le dans un endroit facile à retrouver — votre dossier Téléchargements fonctionne.

---

### Étape 2 — Installer l'extension dans Cowork

Dans Claude Cowork, allez dans :

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
Si vous avez accès aux instances US et UE de Leadbay, connectez-vous sur l'instance que vous voulez que Claude utilise. Vous pouvez changer plus tard en vous déconnectant de l'extension Leadbay dans Cowork et en vous reconnectant sur l'autre instance.
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

Le connecteur hébergé (**Option A**) exécute toujours la dernière version — il n'y a rien à mettre à jour.

Pour l'extension `.dxt` manuelle (**Option C**), quand une nouvelle release sort, répétez l'**Étape 1** (télécharger le nouveau `.dxt`) et l'**Étape 2** (Install extension). Cowork remplace l'ancienne version sur place ; votre connexion reste valide, vous n'avez donc pas à vous ré-authentifier.

---

## Dépannage

| Symptôme | Solution |
|---------|-----|
| Claude dit « non authentifié » ou erreurs 401 | Votre connexion a peut-être expiré ou été révoquée. Déclenchez n'importe quel outil Leadbay à nouveau et Claude relancera le flux **Se connecter avec Leadbay** |
| Le connecteur hébergé ne se connecte pas (« échec d'enregistrement » ou « compte introuvable ») | Vérifiez que l'URL correspond à votre instance — `/fr/mcp` pour UE/France, `/mcp` pour US |
| Les outils n'apparaissent pas dans Cowork | Vérifiez que l'extension est bien sur **Enabled** dans Settings → Extensions |
| Les outils apparaissent mais Claude ne les appelle pas | Ouvrez **Configure** et basculez les groupes d'outils sur **Always allow** |
| Mauvaise instance (aucun lead / erreurs 404) | Déconnectez-vous de l'extension Leadbay et reconnectez-vous sur la bonne instance (US ou UE) |
| Autre problème | Signalez un bug sur [github.com/leadbay/leadclaw/issues](https://github.com/leadbay/leadclaw/issues) |
