# Qu'est-ce que Leadbay MCP ?

Leadbay MCP donne à Claude un accès direct à votre compte Leadbay. Une fois connecté, vous pouvez demander à Claude — en langage naturel — de récupérer des leads, les qualifier, enrichir des contacts, rédiger des messages de prospection et journaliser vos actions. Claude effectue le travail avec **vos** vraies données et **vos** permissions, comme si vous l'aviez fait vous-même dans l'application.

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

## Ce que Claude peut faire

Leadbay expose ses capacités à Claude sous forme d'**outils**, regroupés en deux familles :

| Famille | Ce qu'elle couvre | Exemples |
|--------|---------------|----------|
| **Lecture seule** | Récupère des données, ne modifie jamais rien | Récupérer des leads, parcourir les lenses, lire des profils de lead, rechercher des contacts, consulter le quota d'enrichissement |
| **Écriture / activation** | Effectue des actions sur votre compte | Qualifier des leads, enrichir des contacts, ajouter des notes, importer des leads, journaliser la prospection, affiner votre audience |

Tout est **limité à votre compte** — il n'y a rien de destructeur au niveau de la plateforme, et toute action prise par Claude est une action que vous pourriez prendre vous-même dans l'application.

{% hint style="info" %}
La liste complète et à jour des outils ainsi que les workflows recommandés se trouvent dans le [README LeadClaw](https://github.com/leadbay/leadclaw#tools).
{% endhint %}

---

## Où ça fonctionne

Leadbay MCP fonctionne avec tout assistant IA qui supporte le Model Context Protocol :

- **Claude Desktop**
- **Claude Code**
- **Claude Cowork**
- **Cursor**
- **ChatGPT**

---

## Comment fonctionne la connexion

Vous n'avez jamais à copier, coller ou renouveler de jetons d'API. La première fois que Claude appelle un outil Leadbay, une page **Se connecter avec Leadbay** s'ouvre dans votre navigateur — vous vous connectez, cliquez sur **Approuver**, et Claude est relié à votre compte. Vous pouvez révoquer l'accès à tout moment depuis **Paramètres → Applications connectées** dans Leadbay.

---

## Étape suivante

Prêt à connecter ? Rendez-vous sur le guide d'installation.

{% content-ref url="installation.md" %}
[installation.md](installation.md)
{% endcontent-ref %}
