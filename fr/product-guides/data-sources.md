# Sources de données

Leadbay fonctionne mieux quand il connaît vos leads passés. Importez vos données CRM via des fichiers CSV ou connectez vos outils via Zapier.

---

## Importer un fichier CSV

{% hint style="info" %}
Les imports sont réservés aux utilisateurs admin.
{% endhint %}

### Lors de l'onboarding

La première fois, vous êtes invité à uploader un CSV avec vos leads passés. Voir [Premiers pas](onboarding.md).

### Ajouter des données plus tard

Depuis le menu latéral, allez dans **Data Sources** et cliquez sur **Add new data source** :

1. **Uploadez votre CSV** — tout fichier avec des données d'entreprise
2. **Mappez les champs** — Leadbay détecte automatiquement les colonnes. Vérifiez ou corrigez.
3. **Mappez les statuts** — Indiquez quelles valeurs correspondent à gagné, perdu, en cours, etc.

### Importer uniquement des contacts

Pour ajouter des coordonnées (téléphones, emails) sans modifier les statuts : lors de l'import, ne mappez pas la colonne statut et ne définissez pas de statut par défaut.

### Champs personnalisés (Bêta)

Vous pouvez définir des champs personnalisés pour des données spécifiques à votre activité. Allez dans Data Sources, cliquez sur **Add new custom field**, puis mappez-le lors du prochain import.

---

## Connexion Zapier

Zapier automatise le flux de données entre Leadbay et des milliers d'applications.

### Activer la connexion

1. Ouvrez l'invitation Leadbay-Zapier : [Invitation Zapier Leadbay](https://zapier.com/developer/public-invite/186700/31de3445b74ad2736aa150f9f07f4bd3/)
2. Cliquez sur **Accept Invite and Build a Zap**

### Importer vers Leadbay (CRM → Leadbay)

1. Sur [Zapier](https://zapier.com/app/zaps) → **Create** → **New Zap**
2. **Trigger** : sélectionnez votre CRM et choisissez un événement
3. **Action** : recherchez **Leadbay**, connectez-vous si demandé
4. Mappez les champs, puis cliquez sur **Publish**

### Exporter depuis Leadbay (Leadbay → CRM)

1. Sur [Zapier](https://zapier.com/app/zaps) → **Create** → **New Zap**
2. **Trigger** : recherchez **Leadbay**, choisissez l'événement d'export
3. **Action** : sélectionnez votre CRM
4. Mappez les champs, puis cliquez sur **Publish**

{% hint style="info" %}
Vous n'avez besoin d'autoriser la connexion Leadbay-Zapier qu'une seule fois.
{% endhint %}
