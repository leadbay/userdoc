# Connecteur SFTP

Importez automatiquement des leads depuis un fichier CSV hébergé sur votre serveur SFTP. Leadbay se connecte au serveur, lit le fichier et maintient vos données synchronisées.

{% hint style="info" %}
Le connecteur SFTP est réservé aux utilisateurs **admin**. Voir [Équipe & Organisation](team-management.md) pour le détail des rôles.
{% endhint %}

---

## Quand utiliser le SFTP

Utilisez le connecteur SFTP lorsque votre CRM ou système interne exporte les données leads sous forme de fichier CSV vers un serveur SFTP. Au lieu de télécharger et ré-uploader le fichier manuellement à chaque fois, Leadbay se connecte directement et synchronise automatiquement.

---

## Configurer une connexion

1. Depuis le menu latéral, allez dans **Data Sources**
2. Cliquez sur **Add new integration**
3. Sélectionnez **SFTP** dans la liste

<figure><img src="../../.gitbook/assets/screenshot-sftp-connector.png" alt="Formulaire du connecteur SFTP"><figcaption><p>Le formulaire de connexion SFTP</p></figcaption></figure>

Remplissez le formulaire de connexion :

| Champ | Description |
|-------|-------------|
| **Host** | Adresse du serveur SFTP (ex. `sftp.votreentreprise.com`) |
| **Port** | Port du serveur (par défaut : `22`) |
| **Username** | Identifiant SFTP |
| **Password** | Mot de passe SFTP |
| **File Path** | Chemin complet vers le fichier CSV sur le serveur (ex. `/exports/leads.csv`) |

### Tester avant de connecter

Cliquez sur **Test connection** pour vérifier que Leadbay peut atteindre le serveur et trouver le fichier. Une coche verte confirme que la connexion fonctionne.

Une fois le test réussi, cliquez sur **Connect** pour créer le connecteur. Leadbay lance immédiatement une première synchronisation.

---

## Fonctionnement de la synchronisation

- Leadbay vérifie le fichier SFTP périodiquement
- Le fichier n'est ré-importé que si son contenu a changé (détection par somme de contrôle)
- Chaque synchronisation analyse le CSV et importe les leads en utilisant vos mappings de champs et de statuts — les mêmes que pour un import CSV classique

{% hint style="info" %}
Votre fichier CSV doit suivre le même format qu'un import CSV Leadbay classique — au minimum une colonne avec le nom d'entreprise. Voir [Sources de données](data-sources.md) pour les colonnes acceptées et le détail du mapping.
{% endhint %}

---

## Modifier ou supprimer un connecteur

Pour mettre à jour les paramètres de connexion, ouvrez le connecteur depuis votre liste d'intégrations et modifiez les champs. Pour le supprimer, supprimez le connecteur depuis le même écran.
