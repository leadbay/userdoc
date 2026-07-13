# Démarrage rapide

Reliez Leadbay à Claude et obtenez vos premiers leads qualifiés en environ cinq minutes. Ce guide utilise **Claude** (Claude.ai ou Claude Desktop) — le chemin le plus simple. Vous utilisez un autre assistant ? Voir [Installation](installation.md) pour la configuration pas à pas de Claude Code, ChatGPT et Codex.

{% hint style="info" %}
Il vous faut un [compte Leadbay](https://leadbay.ai/) et Claude (Pro, Max, Team ou Enterprise). C'est tout — aucun jeton d'API à copier ou coller ; vous ajoutez une URL et vous vous connectez avec votre navigateur.
{% endhint %}

---

## D'abord — vous êtes dans quel cas ?

Ajouter un connecteur personnalisé nécessite un **plan Claude payant**, et dans un **espace de travail d'entreprise, seul un admin peut l'ajouter**. Trouvez votre situation, puis suivez les étapes ci-dessous :

| Votre situation | Que faire |
|---|---|
| **Solo / plan payant personnel** (pas dans un espace d'entreprise) | Ajoutez-le vous-même — suivez l'Étape 1 ci-dessous. |
| **Dans un espace d'entreprise, et vous êtes l'admin** | Ajoutez-le vous-même (Étape 1) — vos collègues n'ont plus qu'à faire **Connect**. |
| **Dans un espace d'entreprise, pas admin** | Vous ne pouvez pas l'ajouter vous-même. Envoyez à votre admin le guide [Configuration admin](admin-setup.md) ; une fois qu'il l'a ajouté, passez directement à l'**Étape 2 — Se connecter**. |
| **Impossible d'ajouter un connecteur / pas d'admin à qui demander** | Sur **Claude Desktop**, installez plutôt l'[extension `.dxt`](installation.md#solution-de-repli-installer-lextension) — une installation par utilisateur, sans verrou admin. |

---

## Étape 1 — Ajouter le connecteur Leadbay

**[Ajouter le connecteur Leadbay →](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Leadbay&connectorUrl=https%3A%2F%2Fmcp.leadbay.app%2Ffr%2Fmcp)**, puis cliquez sur **Add**. Il existe deux URLs de serveur — ce lien utilise celle de la France, `https://mcp.leadbay.app/fr/mcp`. Sur l'instance US, utilisez plutôt `https://mcp.leadbay.app/mcp`.

{% hint style="info" %}
Vous préférez des captures d'écran pas à pas, ou vous êtes sur un autre assistant (Claude Desktop, Claude Code, ChatGPT, Codex) ? Voir le guide complet d'[Installation](installation.md).
{% endhint %}

---

## Étape 2 — Se connecter

1. Ouvrez le nouveau connecteur **Leadbay** et cliquez sur **Connect**.
2. Une page **Se connecter avec Leadbay** s'ouvre dans votre navigateur — connectez-vous (ou confirmez votre session existante) et cliquez sur **Approuver**.
3. L'onglet se ferme tout seul et Claude est connecté.

C'est toute la connexion — aucun jeton, aucun fichier de config. Claude est désormais relié à **votre** compte Leadbay, avec tous les leads que vous avez déjà. Vous pouvez révoquer l'accès à tout moment depuis **Paramètres → Applications connectées**.

---

## Étape 3 — Demandez vos premiers leads

Ouvrez une nouvelle conversation et tapez :

> _Montre-moi les leads du jour et dis-moi lesquels valent la peine d'être ouverts en premier._

Claude appelle vos outils Leadbay et répond avec une courte liste classée — entreprise, pourquoi elle correspond, et le meilleur contact à joindre.

{% hint style="info" %}
Votre premier message reçoit _« Je ne vois aucun outil Leadbay »_ ? Les outils sont encore en train de se charger. Envoyez n'importe quel deuxième message (même juste _« réessaie »_) et Claude les détectera.
{% endhint %}

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

> _Recherche le meilleur pour moi — est-ce un bon fit ?_

> _Rédige-moi un email de prospection pour lui._

> _Je viens de lui envoyer un email. Journalise-le comme prospection._

Claude se souvient des leads qu'il a fait remonter, vous pouvez donc continuer à parler du « meilleur » sans vous répéter.

---

## Vous utilisez un autre assistant ?

{% content-ref url="installation.md" %}
[Installation](installation.md)
{% endcontent-ref %}

Configuration pas à pas pour **Claude.ai**, **Claude Desktop**, **Claude Code**, **ChatGPT** et **Codex**. Les comptes France / UE utilisent `https://mcp.leadbay.app/fr/mcp` ; les comptes US utilisent `https://mcp.leadbay.app/mcp`.

---

## Et ensuite

{% content-ref url="example-prompts.md" %}
[Exemples de prompts](example-prompts.md)
{% endcontent-ref %}

{% content-ref url="tools-reference.md" %}
[Référence des outils](tools-reference.md)
{% endcontent-ref %}
