# Démarrage rapide

Connectez Leadbay à Claude et obtenez vos premiers leads qualifiés en environ cinq minutes. Choisissez votre client, installez, connectez-vous, et demandez — sans coder, sans jeton à copier.

{% hint style="info" %}
Il vous faut un [compte Leadbay](https://leadbay.ai/) et un assistant IA qui supporte MCP (Claude Desktop, Claude Cowork, Claude Code ou Cursor — Codex aussi). C'est tout — aucun jeton d'API à copier ou coller. _Le support de ChatGPT arrive bientôt._
{% endhint %}

---

## Étape 1 — Installer

L'URL du serveur Leadbay pour la France est :

```
https://mcp.leadbay.app/fr/mcp
```

**Sur Claude (web / Desktop) — connecteur personnalisé** (recommandé) :

1. **[Ajouter le connecteur Leadbay →](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Leadbay&connectorUrl=https%3A%2F%2Fmcp.leadbay.app%2Ffr%2Fmcp)**, puis cliquez sur **Add**.
2. Ouvrez le connecteur **Leadbay**, cliquez sur **Connect** et connectez-vous.

**Sur Claude Code ou Codex — une commande :**

```bash
claude mcp add --scope user --transport http leadbay https://mcp.leadbay.app/fr/mcp
```

(Pour Codex : `codex mcp add leadbay --url https://mcp.leadbay.app/fr/mcp`.)

**Sur Claude Desktop sans connecteur — extension `.dxt`** (aucun droit admin requis) :

1. **[⬇ Télécharger l'extension Leadbay (.dxt)](https://github.com/leadbay/mcp/releases/latest/download/leadbay-latest.dxt)**
2. Double-cliquez dessus → **Install** → basculez sur **Enabled**. Claude ne s'ouvre pas ? **Settings → Extensions → Advanced → Install extension**, puis sélectionnez le fichier.

---

## Étape 2 — Se connecter (cela se fait automatiquement)

Vous ne configurez rien à la main. Dès que vous installez — ou la première fois que Claude utilise un outil Leadbay — une page **Se connecter avec Leadbay** **s'ouvre automatiquement dans votre navigateur** :

1. La page de connexion Leadbay apparaît d'elle-même.
2. Connectez-vous (ou confirmez votre session existante).
3. Cliquez sur **Approuver** pour relier Claude à votre compte.
4. L'onglet se ferme tout seul et Claude est prêt.

C'est toute la connexion. Aucun jeton, aucun fichier de config. Claude est désormais relié à **votre** compte, avec tous les leads que vous avez déjà dans Leadbay. Vous pouvez révoquer l'accès à tout moment depuis **Paramètres → Applications connectées**.

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

<figure><img src="../../.gitbook/assets/mcp-pull-leads-shortlist.png" alt="Un tableau de prospects classés avec fit, raison de qualification et contact, plus le choix par Claude des deux premiers à ouvrir"><figcaption><p>Une première réponse réussie : un tableau de prospects classés, puis les deux qui valent la peine d'être ouverts en premier.</figcaption></figure>

---

## Étape 5 — Continuez

Une fois vos premiers leads affichés, essayez ceci :

> *Recherche le meilleur pour moi — est-ce un bon fit ?*

> *Rédige-moi un email de prospection pour lui.*

> *Je viens de lui envoyer un email. Journalise-le comme prospection.*

Claude se souvient des leads qu'il a fait remonter, vous pouvez donc continuer à parler du « meilleur » sans vous répéter.

---

## Utiliser Leadbay avec Claude Desktop

Claude Desktop charge les outils MCP plus lentement que Cowork, donc quelques précautions supplémentaires aident.

Après avoir installé l'extension Leadbay, **quittez complètement et relancez Claude Desktop** (Cmd-Q sur Mac, puis rouvrez — pas seulement fermer la fenêtre). Ouvrez un nouveau chat et attendez environ **30 secondes** avant d'envoyer votre premier message. Cela laisse à Claude le temps de charger les outils Leadbay.

Si votre premier message reçoit une réponse du type *« Je ne vois aucun outil Leadbay »* ou *« Je ne trouve pas Leadbay dans votre configuration »*, pas d'inquiétude — les outils sont encore en train de se charger. Envoyez n'importe quel deuxième message (même juste *« réessaie »*) et Claude les détectera. À partir de là, le reste de votre session fonctionne normalement.

---

## Mise à jour

Pour l'**extension `.dxt`**, quand une nouvelle release sort, répétez l'**Étape 1** (téléchargez le nouveau `.dxt`, double-cliquez, Install). Claude remplace l'ancienne version sur place ; votre connexion reste valide, vous n'avez donc pas à vous ré-authentifier.

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

---

## Et ensuite

{% content-ref url="example-prompts.md" %}
[Exemples de prompts](example-prompts.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Référence des outils](tools-reference.md)
{% endcontent-ref %}
