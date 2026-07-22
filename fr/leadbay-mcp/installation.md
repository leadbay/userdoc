# Installation

Choisissez votre client ci-dessous. Chacun prend deux minutes et **aucun ne nécessite de jeton d'API** — vous ajoutez une URL de serveur, vous vous connectez une fois avec votre compte Leadbay dans le navigateur, et c'est relié.

Il existe **deux URLs de serveur** — choisissez celle correspondant à l'instance Leadbay sur laquelle se trouve votre compte :

| Région | URL du serveur |
|---|---|
| 🇫🇷 France / UE | `https://mcp.leadbay.app/fr/mcp` |
| 🇺🇸 US | `https://mcp.leadbay.app/mcp` |

Les étapes ci-dessous montrent l'URL France — sur l'instance US, remplacez simplement par `/mcp`.

Il vous faut un [compte Leadbay](https://leadbay.ai/) (le même identifiant que l'application web) et l'un des assistants ci-dessous.

---

## Claude.ai (web)

Ajoutez Leadbay comme **connecteur personnalisé**.

1. **[Ajouter le connecteur Leadbay →](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Leadbay&connectorUrl=https%3A%2F%2Fmcp.leadbay.app%2Ffr%2Fmcp)** — le formulaire s'ouvre avec le nom et l'URL pré-remplis. Laissez les paramètres avancés tels quels, puis cliquez sur **Add**.
2. Ouvrez le connecteur **Leadbay** dans le répertoire (cherchez « Leadbay » sous **Custom connectors**), cliquez sur **Connect** et connectez-vous.

Les outils Leadbay deviennent disponibles dans vos chats. Vous pouvez les cadrer par projet dans Claude Projects.

> **Pas admin de l'organisation ?** Les membres ne peuvent pas ajouter un connecteur personnalisé — votre admin l'ajoute une fois (étape 1), puis vous faites **Connect** (étape 2). Voir [Configuration admin](admin-setup.md). Les connecteurs personnalisés nécessitent un plan Claude payant (Pro, Max, Team ou Enterprise).

---

## Claude Desktop

Même **connecteur personnalisé** que Claude.ai, même URL.

1. **Settings → Connectors → + → Add custom connector**
2. **Name :** `Leadbay` · **URL :** `https://mcp.leadbay.app/fr/mcp` → cliquez sur **Add**
3. Ouvrez le connecteur **Leadbay**, cliquez sur **Connect**, connectez-vous.

Si votre premier message reçoit _« Je ne vois aucun outil Leadbay »_, les outils sont encore en train de se charger — envoyez n'importe quel deuxième message et Claude les détectera. Pas admin de l'organisation ? L'admin ajoute le connecteur d'abord (voir [Configuration admin](admin-setup.md)), ou utilisez la solution de repli par extension ci-dessous.

### Solution de repli : installer l'extension

Pas d'option **Add custom connector**, ou pas admin de l'organisation ? Contournez le connecteur et installez Leadbay comme **extension `.dxt`** — une installation par utilisateur en double-clic, sans droits admin.

1. **[⬇ Télécharger l'extension Leadbay (.dxt)](https://github.com/leadbay/mcp/releases/latest/download/leadbay-latest.dxt)**
2. Double-cliquez dessus → **Install** → basculez sur **Enabled**.
3. Ouvrez un nouveau chat, cliquez sur **Connect** sur l'extension, connectez-vous.

Le double-clic n'ouvre pas Claude ? Installez depuis l'application : **Settings → Extensions → Advanced → Install extension**, puis sélectionnez le `.dxt` téléchargé. À chaque nouvelle release, téléchargez et réinstallez — Claude remplace l'ancienne version sur place et votre connexion reste valide.

---

## Claude Code

Une seule commande enregistre Leadbay pour tous vos projets :

```bash
claude mcp add --scope user --transport http leadbay https://mcp.leadbay.app/fr/mcp
```

1. Lancez `/mcp` dans Claude Code.
2. Sélectionnez **leadbay → Authenticate** — votre navigateur s'ouvre pour la connexion.
3. Connectez-vous et approuvez. Le statut passe à **connected** et les outils se chargent.

Vous avez lancé `add` dans une session ouverte ? Redémarrez-la une fois pour que le serveur apparaisse dans `/mcp`. Supprimez-le à tout moment avec `claude mcp remove leadbay -s user`.

---

## Codex

Codex a une commande intégrée pour les serveurs MCP distants :

```bash
codex mcp add leadbay --url https://mcp.leadbay.app/fr/mcp
```

Codex détecte OAuth automatiquement et ouvre votre navigateur pour le flux **Se connecter avec Leadbay** — connectez-vous et approuvez. Vérifiez avec `codex mcp list` (vous devriez voir `leadbay` avec **Status: enabled**, **Auth: OAuth**). Supprimez-le avec `codex mcp remove leadbay`.

---

## ChatGPT

Ajoutez Leadbay comme connexion de plugin personnalisée (connecteur MCP).

1. Activez le mode développeur : ouvrez **Settings → Security and Login**, descendez tout en bas, puis activez **Developer mode**.
2. Ouvrez **Plugins** dans ChatGPT.
3. Cliquez sur **+** pour ajouter une nouvelle connexion.
4. **Name :** `Leadbay`
5. **Connection URL :** utilisez l'URL correspondant à votre espace Leadbay :
   - France / UE : `https://mcp.leadbay.app/fr/mcp`
   - US : `https://mcp.leadbay.app/mcp`
6. Cliquez sur **Connect**, puis connectez-vous avec votre compte Leadbay et approuvez.

Dans un chat, activez **Leadbay** depuis le menu **+** / plugins du composeur pour que ChatGPT puisse appeler ses outils.

> Les connecteurs MCP personnalisés nécessitent un plan ChatGPT payant (Plus, Pro, Business ou Enterprise). Sur Business/Enterprise, un admin peut devoir autoriser les plugins/connecteurs personnalisés d'abord. Si Leadbay se déconnecte, ouvrez **Plugins**, sélectionnez **Leadbay**, puis reconnectez-vous.

---

## Après la connexion — vos premiers leads

Quel que soit le client utilisé, ouvrez une nouvelle conversation et essayez :

> _Montre-moi les leads du jour et dis-moi lesquels valent la peine d'être ouverts en premier._

Une réponse réussie est une **liste classée** — chaque lead avec un score de fit, une raison en une ligne « pourquoi ça correspond », et le meilleur contact. Si vous voyez ça, vous êtes complètement connecté. 🎉

{% content-ref url="example-prompts.md" %}
[Exemples de prompts](example-prompts.md)
{% endcontent-ref %}

---

## Dépannage

| Symptôme | Solution |
|---------|-----|
| Erreurs « Non authentifié » / 401 | Votre connexion a expiré ou a été révoquée. Déclenchez n'importe quel outil Leadbay à nouveau et approuvez l'invite **Se connecter avec Leadbay**. |
| Connecté, mais « montre-moi les leads » renvoie une liste vide | Vous êtes bien connecté — il n'y a simplement rien à afficher pour l'instant. Demandez _« montre-moi mes lenses »_ pour vérifier quelle audience est active. |
| Les outils n'apparaissent pas après la connexion | Ouvrez un nouveau chat et attendez quelques secondes ; envoyez un deuxième message et les outils finissent de se charger. |
| Les outils apparaissent mais l'assistant ne les appelle pas | Ouvrez les paramètres du connecteur et réglez les groupes d'outils Leadbay sur **Always allow** (Claude) ou activez le plugin Leadbay dans le composeur (ChatGPT). |
| Option de connecteur/plugin personnalisé absente (Claude.ai / Claude Desktop / ChatGPT) | Les connecteurs/plugins personnalisés nécessitent un plan payant, et votre admin d'organisation peut devoir les activer — voir [Configuration admin](admin-setup.md). Sur **Claude Desktop**, vous pouvez contourner le connecteur avec la [solution de repli par extension `.dxt`](#solution-de-repli-installer-lextension). |
| Autre problème | Signalez un bug sur [github.com/leadbay/mcp/issues](https://github.com/leadbay/mcp/issues). |

---

## Et ensuite

{% content-ref url="what-is-leadbay-mcp.md" %}
[Qu'est-ce que Leadbay MCP ?](what-is-leadbay-mcp.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Référence des outils](tools-reference.md)
{% endcontent-ref %}
