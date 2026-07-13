# Configuration admin

**Pour les admins d'espace de travail et d'organisation.** Cette page vous guide pour ajouter le connecteur Leadbay une seule fois, pour toute votre organisation, afin que chaque membre puisse se connecter sans avoir besoin de droits admin lui-même.

Si vous êtes arrivé ici parce qu'un collègue vous a demandé d'« ajouter le connecteur Leadbay » — vous êtes au bon endroit. Ça prend deux minutes, il n'y a aucun jeton d'API à distribuer, et chaque membre se connecte toujours avec **son propre** compte Leadbay.

> **Êtes-vous sûr d'en avoir besoin ?** Seuls les plans **organisation** verrouillent les connecteurs personnalisés derrière un admin — **Claude** Team/Enterprise et **ChatGPT** Business/Enterprise. Sur un plan payant individuel (Claude Pro/Max, ChatGPT Plus/Pro), il n'y a pas d'étape admin ; ajoutez le connecteur vous-même via le guide [Démarrage rapide](quickstart.md) ou [Installation](installation.md).

---

## Claude (Team & Enterprise)

En tant que **propriétaire principal ou admin**, ajoutez Leadbay comme connecteur personnalisé d'**organisation**. Une fois ajouté, il apparaît dans le répertoire de chaque membre et ils se connectent individuellement.

1. **[Ajouter le connecteur Leadbay →](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Leadbay&connectorUrl=https%3A%2F%2Fmcp.leadbay.app%2Ffr%2Fmcp)** — le formulaire s'ouvre avec le nom et l'URL pré-remplis. (Il existe deux URLs de serveur : ce lien utilise celle de la France, `https://mcp.leadbay.app/fr/mcp` ; pour un espace de travail US, utilisez plutôt `https://mcp.leadbay.app/mcp`.)
2. Si Claude propose un choix de portée, choisissez **organisation** pour que chaque membre en bénéficie. Laissez les paramètres avancés tels quels (**Individual sign-in** — chaque membre utilise son propre identifiant Leadbay ; vous ne partagez pas un seul compte), puis cliquez sur **Add**.

C'est fait côté admin — Leadbay apparaît maintenant dans le répertoire de connecteurs de vos membres. (Dans un espace Team/Enterprise, les membres n'ont pas l'option **Add custom connector** eux-mêmes, c'est pourquoi cette étape existe.)

**Ce que font vos membres ensuite :** dans Claude, **Settings → Connectors → cherchez « Leadbay » → Connect**, puis connexion avec leur propre compte Leadbay. Guide complet dans le [Démarrage rapide](quickstart.md).

---

## ChatGPT (Business & Enterprise)

Sur les espaces Business et Enterprise, les connecteurs MCP personnalisés sont désactivés jusqu'à ce qu'un **propriétaire ou admin d'espace de travail** les autorise. Vous n'ajoutez pas Leadbay pour tout le monde ici — vous débloquez la possibilité, et chaque membre l'ajoute ensuite lui-même.

1. Ouvrez les **paramètres de votre espace de travail** (menu d'espace, en bas à gauche → **Settings**).
2. Sous les contrôles de connecteurs / apps, **autorisez les connecteurs personnalisés** pour l'espace de travail (c'est l'interrupteur au niveau de l'espace qui débloque les apps personnalisées en Developer mode pour les membres).
3. Prévenez vos membres qu'ils peuvent désormais ajouter Leadbay.

### Ce que font vos membres ensuite

Contrairement à Claude, les membres ChatGPT ajoutent l'application eux-mêmes une fois que vous avez autorisé les connecteurs personnalisés. Envoyez-leur la section **ChatGPT** du guide [Installation](installation.md) — chaque membre :

1. Active le **Developer mode** (Settings → Apps → Advanced settings).
2. Clique sur **Create app** et remplit **Name** `Leadbay MCP`, **Server URL** `https://mcp.leadbay.app/fr/mcp`, et **Authentication : OAuth**.
3. Clique sur **Sign in with Leadbay MCP** et se connecte avec son propre compte Leadbay.
4. Active l'application **Leadbay MCP** depuis le menu **+** / outils du composeur, puis demande des leads.

{% hint style="info" %}
La formulation et l'emplacement exacts du contrôle « autoriser les connecteurs personnalisés » évoluent avec la console admin de ChatGPT. Si vous ne le trouvez pas, cherchez **connectors** ou **apps** dans les paramètres de l'espace, ou consultez la documentation admin actuelle d'OpenAI.
{% endhint %}

{% hint style="info" %}
**Claude Code et Codex ne nécessitent aucune étape admin** — ce sont des clients CLI par utilisateur, sans verrou d'organisation. Chaque membre lance simplement la commande d'ajout en une ligne du guide [Installation](installation.md) sur sa propre machine.
{% endhint %}

---

## Et ensuite

{% content-ref url="installation.md" %}
[Installation](installation.md)
{% endcontent-ref %}

{% content-ref url="quickstart.md" %}
[Démarrage rapide](quickstart.md)
{% endcontent-ref %}
