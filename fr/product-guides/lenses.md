# Lenses

Les Lenses sont des configurations de filtres sauvegardées qui définissent quels leads vous voyez. Chaque lens cible un segment de marché — par secteur, localisation, taille d'entreprise ou mots-clés.

Les Lenses alimentent aussi les recommandations IA : le système apprend de vos likes et de vos affaires gagnées au sein de chaque lens.

---

## Choisir une Lens

Le sélecteur de lens apparaît en haut de la page. Choisissez une lens dans le menu déroulant pour charger instantanément ses filtres et recommandations.

<figure><img src="../../.gitbook/assets/Capture d'écran 2025-08-20 à 10.53.45.png" alt="" width="375"><figcaption><p>Sélecteur de lens</p></figcaption></figure>

---

## Lenses d'organisation vs Lenses privées

| Type | Visibilité | Qui peut modifier |
|------|-----------|-------------------|
| **Lenses d'organisation** | Partagées avec toute l'équipe | Admins |
| **Lenses privées** | Visibles uniquement par vous | Vous |

Une lens d'organisation est marquée **Current** (la lens par défaut de l'équipe). Vous pouvez promouvoir une lens privée en lens d'organisation.

---

## Créer et gérer les Lenses

Cliquez sur l'icône réglages (engrenage) pour ouvrir le panneau de gestion.

- **Créer** : saisissez un nom et cliquez sur +
- **Modifier** (icône crayon) : renommer
- **Supprimer** (icône poubelle)
- **Promouvoir** une lens privée en lens d'organisation (flèche vers le haut)

### Lenses brouillon

Si la lens active est en **lecture seule**, cliquez sur **Create draft lens** pour en faire une copie modifiable.

---

## Filtres

### Types de filtres disponibles

| Filtre | Exemple |
|--------|---------|
| **Localisation** | Paris, Lyon, Occitanie |
| **Secteur** | Services financiers, Agriculture |
| **Taille** | 10–200 employés |
| **Mots-clés** | SaaS, B2B, énergie renouvelable |

### Combinaison des filtres

**Au sein d'un même type** (ex. plusieurs secteurs) : logique **OU**. Un lead correspondant à *n'importe lequel* des secteurs sélectionnés est retenu.

**Entre types différents** (ex. secteur + taille) : logique **ET**. Un lead doit correspondre à *tous* les types de filtres.

---

## Impact sur les recommandations IA

Chaque lens construit son propre modèle IA à partir de vos leads **likés**, de vos leads **gagnés** et de vos **réponses de qualification**.

Le résultat est un **score (0–99)** par lead, spécifique à la lens active. Changez de lens et les scores changent.

{% hint style="info" %}
Si vous vendez plusieurs produits à des marchés différents, créez une lens par produit/segment. Chaque segment aura son propre modèle IA.
{% endhint %}
