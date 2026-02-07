# Lenses

Les Lenses sont des configurations de filtres sauvegardées qui définissent quels leads vous voyez. Chaque lens cible un segment de marché — par secteur, localisation, taille d'entreprise ou mots-clés.

Les Lenses alimentent aussi les recommandations IA : le système apprend de vos likes et de vos affaires gagnées au sein de chaque lens.

---

## Choisir une Lens

Le sélecteur de lens apparaît en haut de la page. Choisissez une lens dans le menu déroulant pour charger instantanément ses filtres et recommandations.

<figure><img src="../../.gitbook/assets/screenshot-lenses.png" alt=""><figcaption><p>Sélecteur de lens</p></figcaption></figure>

Les filtres que vous modifiez restent attachés à la lens actuellement sélectionnée. Changez de lens et les paramètres changent avec.

---

## Lenses d'organisation vs Lenses privées

Il existe deux types de lenses :

| Type | Visibilité | Qui peut modifier |
|------|-----------|-------------------|
| **Lenses d'organisation** | Partagées avec toute l'équipe | Admins |
| **Lenses privées** | Visibles uniquement par vous | Vous |

Une lens d'organisation est marquée **Current** (la lens par défaut de l'équipe). Vous pouvez promouvoir une lens privée en lens d'organisation si vous souhaitez la partager avec votre équipe.

---

## Créer et gérer les Lenses

Cliquez sur l'icône réglages (engrenage) pour ouvrir le panneau de gestion des lenses.

Depuis ce panneau, vous pouvez :

- **Créer une nouvelle lens** : saisissez un nom et cliquez sur +
- **Modifier** une lens (icône crayon) : la renommer
- **Supprimer** une lens (icône poubelle)
- **Promouvoir** une lens privée en lens d'organisation (flèche vers le haut)
- **Définir comme courante** la lens d'organisation active (flèche vers le bas)

### Lenses brouillon

Si la lens active est en **lecture seule** (ex. la lens d'organisation par défaut quand vous n'êtes pas admin), vous pouvez cliquer sur **Create draft lens** pour en faire une copie modifiable. Ajustez les filtres dans votre brouillon, puis promouvez-le si vous le souhaitez.

---

## Filtres de lens

Les filtres définissent quels leads correspondent à une lens. Tout ce que Leadbay sait d'une entreprise peut servir de critère de filtre.

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

**Exemple :** Secteurs = `Services financiers, Agriculture` + Taille = `50-100`
- Une banque avec 75 employés : **correspond** (Services financiers ET 50-100)
- Une exploitation agricole avec 200 employés : **ne correspond pas** (Agriculture mais PAS 50-100)
- Une entreprise tech avec 80 employés : **ne correspond pas** (PAS Services financiers ni Agriculture)

---

## Impact sur les recommandations IA

Chaque lens construit son propre modèle IA. Le système apprend à partir de :

- Vos leads **likés** au sein de cette lens
- Vos leads marqués comme **gagnés** au sein de cette lens
- Vos réponses aux **questions de qualification**

Le résultat est un **score de pertinence (0–99)** par lead, spécifique à la lens active. Changez de lens et les scores changent car le modèle IA est différent.

{% hint style="info" %}
Si vous vendez plusieurs produits à des marchés différents, créez une lens par produit/segment. Chaque segment aura son propre modèle IA et ses propres recommandations.
{% endhint %}
