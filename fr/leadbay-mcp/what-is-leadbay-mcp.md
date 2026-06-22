# Qu'est-ce que Leadbay MCP ?

**Leadbay MCP connecte Claude à votre compte Leadbay : vous travaillez vos leads en demandant, tout simplement.**

Récupérez des leads, qualifiez-les, rédigez votre prospection, journalisez vos actions — en langage naturel. Claude agit sur vos vraies données, avec vos permissions, exactement comme vous le feriez dans l'application.

{% hint style="info" %}
**MCP** signifie *Model Context Protocol* — un standard ouvert qui permet aux assistants IA comme Claude de se connecter de façon sécurisée à des outils et des données externes. Le serveur Leadbay MCP est open source et se trouve sur [github.com/leadbay/leadclaw](https://github.com/leadbay/leadclaw).
{% endhint %}

---

## Pourquoi connecter Leadbay à Claude ?

Au lieu de basculer entre l'application Leadbay et votre flux de travail, vous travaillez en conversation :

> *Récupère les meilleurs leads du jour et dis-moi lesquels valent la peine d'être ouverts ce matin.*

> *Recherche acme.com — est-ce un bon fit pour nous ?*

> *Je viens d'envoyer un email à Jane chez Acme. Journalise-le comme action de prospection.*

Claude lit vos leads, vos lenses et votre profil de goût, raisonne dessus, et répond avec une analyse courte et qualifiée — puis effectue l'action que vous demandez.

---

## Où ça fonctionne

Leadbay MCP fonctionne avec tout assistant IA qui supporte le Model Context Protocol :

- **Claude**
- **Claude Code**
- **Codex**

---

## Concepts clés

Quelques termes Leadbay reviennent dans les prompts et les réponses. Vous n'avez besoin d'en gérer aucun pour démarrer — Claude s'occupe des détails — mais savoir ce qu'ils signifient aide :

| Terme | Ce que ça veut dire |
|------|---------------|
| **Lens** | Votre audience enregistrée — le secteur, la taille d'entreprise et les critères qui définissent quels leads Leadbay fait remonter. Vous pouvez en avoir plusieurs et basculer entre elles (« bascule sur ma lens Joinery »). |
| **Score** | Un score de fit firmographique de 0 à 100 sur chaque lead — à quel point il correspond à votre audience. Affiché sous forme de barre dans les tableaux de leads. |
| **Score IA** | Un score de qualification plus poussé sur les meilleurs leads de chaque lot, issu d'une recherche web ciblée par rapport à vos questions de qualification. La plupart des leads ont le score de base ; les meilleurs sont qualifiés par l'IA. |
| **Profil de goût** | Ce que Leadbay apprend de vos likes, dislikes et actions de prospection — il ajuste le scoring futur à votre jugement. Aimer un lead dans le chat l'entraîne. |
| **Lecture vs écriture** | Les outils en **lecture** récupèrent seulement des données (leads, profils, contacts) et ne changent jamais rien. Les outils en **écriture** effectuent une action (qualifier, enrichir, journaliser la prospection, modifier des lenses). Les deux sont limités à votre compte, et Claude confirme avant toute action qui écrit. |

Ces notions sont détaillées dans les guides produit [Lenses](../product-guides/lenses.md) et [AI Assistant](../product-guides/ai-assistant.md).

---

## Étape suivante

Prêt à connecter ? Le Démarrage rapide vous amène à vos premiers leads en environ cinq minutes.

{% content-ref url="quickstart.md" %}
[Démarrage rapide](quickstart.md)
{% endcontent-ref %}

{% content-ref url="installation.md" %}
[Installation](installation.md)
{% endcontent-ref %}
