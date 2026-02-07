# Sources de données

Leadbay fonctionne mieux quand il connaît vos leads passés. Importez vos données CRM via des fichiers CSV ou connectez vos outils via Zapier.

---

## Importer un fichier CSV

{% hint style="info" %}
Les imports sont réservés aux utilisateurs admin.
{% endhint %}

### Lors de l'onboarding

La première fois que vous configurez Leadbay, vous êtes invité à uploader un CSV avec vos leads passés. Voir [Premiers pas](onboarding.md) pour le détail étape par étape.

### Ajouter des données plus tard

Depuis le menu latéral, allez dans **Data Sources** et cliquez sur **Add new data source**. Le processus est le même que lors de l'onboarding :

1. **Uploadez votre CSV** — tout fichier avec des données d'entreprise (nom, localisation, statut, etc.)
2. **Mappez les champs** — Leadbay détecte automatiquement les colonnes. Vérifiez ou corrigez le mapping.
3. **Mappez les statuts** — Indiquez quelles valeurs de statut correspondent à gagné, perdu, en cours, etc.

**Conseils :**

- Le champ **Status** est le plus important : il indique à l'IA quels leads ont bien performé
- Plus de données = de meilleures recommandations, mais même un petit fichier aide
- Vous pouvez importer plusieurs fichiers au fil du temps

### Importer uniquement des contacts

Si vous voulez ajouter des coordonnées personnelles (téléphones, emails) pour des leads existants sans modifier leurs statuts : lors de l'import, ne mappez pas la colonne statut et laissez le statut par défaut vide. Vos données de contact seront ajoutées aux fiches leads sans impacter les statuts.

### Champs personnalisés (Bêta)

Vous pouvez définir des champs personnalisés pour des données spécifiques à votre activité (ex. ligne de produits, type de contrat). Allez dans Data Sources et cliquez sur **Add new custom field**, puis mappez-le lors du prochain import.

---

## Connexion Zapier

Zapier automatise le flux de données entre Leadbay et des milliers d'applications — y compris votre CRM.

### Activer la connexion

1. Ouvrez l'invitation Leadbay-Zapier : [Invitation Zapier Leadbay](https://zapier.com/developer/public-invite/186700/31de3445b74ad2736aa150f9f07f4bd3/)
2. Cliquez sur **Accept Invite and Build a Zap**

### Importer vers Leadbay (CRM → Leadbay)

1. Sur [Zapier](https://zapier.com/app/zaps) → **Create** → **New Zap**
2. **Trigger** : sélectionnez votre CRM (ex. HubSpot, Salesforce) et choisissez un événement (nouvelle entreprise, changement de statut)
3. **Action** : recherchez **Leadbay**, connectez-vous si demandé
4. Mappez les champs de votre CRM vers les champs Leadbay (nom, localisation, statut, etc.)
5. Cliquez sur **Publish**

### Exporter depuis Leadbay (Leadbay → CRM)

1. Sur [Zapier](https://zapier.com/app/zaps) → **Create** → **New Zap**
2. **Trigger** : recherchez **Leadbay**, choisissez l'événement d'export
3. **Action** : sélectionnez votre CRM et choisissez « Create Company » (ou équivalent)
4. Mappez les champs Leadbay vers les colonnes de votre CRM
5. Cliquez sur **Publish**

{% hint style="info" %}
Vous n'avez besoin d'autoriser la connexion Leadbay-Zapier qu'une seule fois. Après quoi, tous vos Zaps peuvent l'utiliser.
{% endhint %}
