# Démarrage rapide

Connectez Leadbay à Claude et obtenez vos premiers leads qualifiés en environ cinq minutes. C'est la voie rapide — choisissez votre client, installez, connectez-vous, et demandez. Les options détaillées et le dépannage sont dans le guide d'[Installation](installation.md).

{% hint style="info" %}
Il vous faut un [compte Leadbay](https://leadbay.ai/) et un assistant IA qui supporte MCP (Claude Desktop, Claude Code, Claude Cowork, Cursor ou ChatGPT). C'est tout — aucun jeton d'API à copier ou coller.
{% endhint %}

---

## Étape 1 — Installer

La voie recommandée est l'**extension `.dxt`** — téléchargez un fichier et installez-le. (Les détails complets et les autres options sont dans le guide d'[Installation](installation.md).)

| Votre client | Voie recommandée |
|---|---|
| **Claude Desktop** ou **Claude Cowork** | **Extension `.dxt`** — téléchargez depuis les releases et installez |
| **Claude Code** ou **Cursor** | **Installateur en une commande** — `npx -y -p @leadbay/mcp@latest installer` |

**Extension `.dxt`** (recommandé) : téléchargez le dernier `leadbay-X.Y.Z.dxt` depuis la [page des releases LeadClaw](https://github.com/leadbay/leadclaw/releases/), puis dans Claude ouvrez **Settings → Extensions → Advanced → Install extension** et sélectionnez le fichier.

**Installateur en une commande** (alternative — Code / Cursor, nécessite [Node.js](https://nodejs.org) 22+) :

```bash
npx -y -p @leadbay/mcp@latest installer
```

---

## Étape 2 — Se connecter (cela se fait automatiquement)

Vous ne configurez rien à la main. Dès que vous installez — ou la première fois que Claude utilise un outil Leadbay — une page **Se connecter avec Leadbay** **s'ouvre automatiquement dans votre navigateur** :

1. La page de connexion Leadbay apparaît d'elle-même.
2. Connectez-vous (ou confirmez votre session existante).
3. Cliquez sur **Approuver** pour relier Claude à votre compte.
4. L'onglet se ferme tout seul et Claude est prêt.

C'est toute la connexion. Aucun jeton, aucun fichier de config. Claude est désormais relié à **votre** compte, avec tous les leads et lenses que vous avez déjà dans Leadbay. Vous pouvez révoquer l'accès à tout moment depuis **Paramètres → Applications connectées**.

{% hint style="info" %}
Si vous avez à la fois un compte US et UE, connectez-vous sur l'instance que vous voulez que Claude utilise. Vous pouvez changer plus tard en vous déconnectant puis en vous reconnectant sur l'autre instance.
{% endhint %}

---

## Étape 3 — Demandez vos premiers leads

Ouvrez une nouvelle conversation et tapez :

> *Montre-moi les leads du jour et dis-moi lesquels valent la peine d'être ouverts en premier.*

Claude appelle vos outils Leadbay et répond avec une courte liste classée — entreprise, pourquoi elle correspond, et le meilleur contact à joindre.

---

## Étape 4 — Ce que vous devriez voir

Une première réponse réussie ressemble à un **tableau de leads classés**, pas à un pavé de texte. Pour chaque lead vous obtenez :

- un **score** (à quel point il correspond à votre audience),
- une **raison** en une ligne,
- le **meilleur contact** avec un lien quand il est disponible.

Si Claude répond avec des leads comme ça, vous êtes complètement connecté. 🎉

---

## Étape 5 — Continuez

Une fois vos premiers leads affichés, essayez ceci :

> *Recherche le meilleur pour moi — est-ce un bon fit ?*

> *Rédige-moi un email de prospection pour lui.*

> *Je viens de lui envoyer un email. Journalise-le comme prospection.*

Claude se souvient des leads qu'il a fait remonter, vous pouvez donc continuer à parler du « meilleur » sans vous répéter.

---

## Et ensuite

{% content-ref url="what-is-leadbay-mcp.md" %}
[Qu'est-ce que Leadbay MCP ?](what-is-leadbay-mcp.md)
{% endcontent-ref %}

{% content-ref url="example-prompts.md" %}
[Exemples de prompts](example-prompts.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Référence des outils](tools-reference.md)
{% endcontent-ref %}
