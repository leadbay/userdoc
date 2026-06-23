# Référence des outils

Quand vous connectez Leadbay à Claude, le serveur expose un ensemble d'**outils** que Claude appelle pour vous. Vous ne les appelez jamais directement — vous demandez en langage naturel (« récupère les leads du jour », « recherche acme.com », « note que j'ai envoyé un email à Jane ») et Claude choisit le bon outil. Cette page est une référence de ce qui est disponible et de ce que fait chaque outil.

Les outils se répartissent en deux groupes : **lecture seule** (récupèrent des données, ne modifient jamais rien) et **écriture / activation** (effectuent une action sur votre compte).

---

## Outils en lecture seule

Ils ne modifient jamais votre compte, on peut donc les autoriser sans risque.

### Découvrir & relancer

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_pull_leads` | Récupère le lot de leads frais du jour, scoré et classé |
| `leadbay_pull_followups` | Récupère les leads qui nécessitent une action de relance |
| `leadbay_account_status` | Vérifie votre quota, vos crédits et l'état de votre compte |
| `leadbay_scan_portfolio_signals` | Scanne vos leads existants pour un signal web en une seule passe (« lesquels de mes leads ont acquis une entreprise depuis 2025 ? ») — sans consommer de quota |

### Rechercher une entreprise

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_research_lead_by_id` | Fiche de recherche détaillée pour un lead connu — regroupe détails, qualification et contacts dans une seule réponse |
| `leadbay_research_lead_by_name_fuzzy` | Retrouve un lead par nom d'entreprise ou domaine quand vous n'avez pas son ID |
| `leadbay_account_history` | Historique complet d'un compte — signaux IA actuels + toutes les notes + chronologie des interactions, en un seul appel (« pourquoi ce compte est-il revenu ? ») |
| `leadbay_prepare_outreach` | Génère un brief de prospection personnalisé pour un lead |

### Déplacements & terrain

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_followups_map` | Regroupe vos relances sur une carte pour planifier vos déplacements |
| `leadbay_tour_plan` | Construit un itinéraire de visites pour un déplacement à venir dans une ville |

### Campagnes

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_list_campaigns` | Liste vos campagnes existantes |
| `leadbay_campaign_progression` | Affiche les métriques de funnel d'une campagne |
| `leadbay_campaign_call_sheet` | Récupère la feuille d'appels d'une campagne |

### Lenses & audience

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_list_sectors` | Liste les vrais libellés de la taxonomie de secteurs — pour que vous (et Claude) nommiez les secteurs correctement |
| `leadbay_recall_ordered_titles` | Rappelle les intitulés de poste que vous avez déjà enrichis |
| `leadbay_seed_candidates` | Surface de découverte en lecture seule pour construire une lens plus large |

### Imports & jobs

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_import_status` | Vérifie l'état d'un job d'import |
| `leadbay_qualify_status` | Vérifie l'état d'un job de qualification |
| `leadbay_bulk_enrich_status` | Vérifie l'état d'un job d'enrichissement |
| `leadbay_resolve_import_rows` | Fait correspondre les lignes importées à leurs IDs de lead |
| `leadbay_list_mappable_fields` | Liste les champs CRM sur lesquels mapper un import |

### Facturation

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_create_topup_link` | Génère un lien Stripe pour recharger votre quota (vous payez dans votre navigateur — rien n'est débité automatiquement) |
| `leadbay_open_billing_portal` | Ouvre votre tableau de bord de facturation |

---

## Outils d'écriture / activation

Ils effectuent une action sur votre compte. Activés par défaut. Chaque action est une action que vous pourriez effectuer vous-même dans l'application — il n'y a rien de destructeur au niveau de la plateforme.

### Qualifier & enrichir

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_bulk_qualify_leads` | Déclenche la qualification IA sur un lot de leads |
| `leadbay_enrich_titles` | Enrichit les contacts par intitulé de poste |

### Prospection & activité

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_report_outreach` | Journalise une action de prospection (appel, email, rendez-vous) sur un lead |
| `leadbay_add_note` | Ajoute une note à un lead |
| `leadbay_like_lead` | Marque un lead comme aimé — entraîne votre profil de goût |
| `leadbay_dislike_lead` | Marque un lead comme rejeté — entraîne votre profil de goût |

### Contacts

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_add_contact` | Ajoute une personne à une entreprise (nom + LinkedIn / poste / email / téléphone optionnels) |
| `leadbay_remove_contact` | Supprime un contact que vous avez ajouté |
| `leadbay_pin_contact` | Épingle un contact comme priorité sur une entreprise |
| `leadbay_unpin_contact` | Désépingle un contact |
| `leadbay_update_contact` | Modifie les détails d'un contact (poste, email, LinkedIn…) |

### Lenses & audience

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_my_lenses` | Liste, change, renomme ou supprime vos lenses |
| `leadbay_new_lens` | Crée une lens nommée avec des critères de secteur / taille d'entreprise |
| `leadbay_adjust_audience` | Modifie l'audience d'une lens (« arrête de me montrer les entreprises de plus de 50 employés ») |
| `leadbay_extend_my_lens` | Remplit votre lens actuelle avec plus de leads à la demande (soumis à un quota de recharge quotidien) |
| `leadbay_refine_prompt` | Affine le prompt de qualification qui score vos leads |
| `leadbay_answer_clarification` | Répond à une question de clarification posée par Leadbay sur votre audience |

### Imports & campagnes

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_import_leads` | Importe une liste de domaines d'entreprises |
| `leadbay_import_and_qualify` | Importe une liste et la qualifie immédiatement |
| `leadbay_create_custom_field` | Crée un champ CRM personnalisé (ex. pour préserver un ID système source) |
| `leadbay_create_campaign` | Crée une nouvelle campagne |
| `leadbay_add_leads_to_campaign` | Ajoute des leads à une campagne |
| `leadbay_remove_leads_from_campaign` | Retire des leads d'une campagne |

### Retours

| Outil | Ce qu'il fait |
|------|--------------|
| `leadbay_send_feedback` | Envoie un message à l'équipe Leadbay (même boîte que le formulaire de feedback de l'application) |
| `leadbay_report_friction` | Signale qu'un outil n'a pas livré ce dont vous aviez besoin — aide à améliorer le produit |

---

## Comment Claude choisit un outil

Vous ne choisissez pas les outils — vous décrivez le résultat. Quelques exemples de correspondance :

| Vous dites… | Claude appelle… |
|----------|---------------|
| « Montre-moi les leads du jour » | `leadbay_pull_leads` |
| « Quels leads dois-je relancer ? » | `leadbay_pull_followups` |
| « Parle-moi de acme.com » | `leadbay_research_lead_by_name_fuzzy` |
| « Je vais à Lyon la semaine prochaine — planifie mes visites » | `leadbay_tour_plan` |
| « Je viens d'appeler Jane chez Acme — journalise-le » | `leadbay_report_outreach` |
| « Crée une lens appelée Joinery pour la fintech » | `leadbay_new_lens` |
| « Arrête de me montrer les entreprises de plus de 50 personnes » | `leadbay_adjust_audience` |

Voir la page [Exemples de prompts](example-prompts.md) pour une bibliothèque plus complète à copier-coller.

---

## Étape suivante

{% content-ref url="example-prompts.md" %}
[Exemples de prompts](example-prompts.md)
{% endcontent-ref %}
