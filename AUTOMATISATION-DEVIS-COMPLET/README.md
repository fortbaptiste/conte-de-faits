# AUTOMATISATION DEVIS - BAPTISTE FORT

## WORKFLOW AUTOMATIQUE

Quand tu envoies une transcription de devis, le systeme genere automatiquement :

1. **Site presentation** (index.html) → deploye sur GitHub Pages
2. **Devis PDF** (devis-XXX.html) → a imprimer en PDF via Chrome
3. **Doc technique PDF** (doc-technique.html) → a imprimer en PDF via Chrome

## STRUCTURE DES DOSSIERS

```
SUIVIE MISSION BONAPARTE/
├── missions/
│   └── {nom-client-projet}/
│       ├── index.html        # Site presentation (GitHub Pages)
│       ├── devis-XXX.html    # Devis PDF
│       └── doc-technique.html # Doc technique PDF
├── templates/
│   ├── presentation-template.html
│   ├── devis-template.html
│   └── doc-technique-template.html
└── automation/
    └── (scripts)
```

## COMMENT GENERER LES PDF

1. Ouvrir le fichier .html dans Chrome
2. Ctrl+P (ou Cmd+P sur Mac)
3. Destination : "Enregistrer au format PDF"
4. Cocher : "Graphiques d'arriere-plan"
5. Marges : "Aucune"
6. Enregistrer

## LIENS GITHUB PAGES

Format : `https://{username}.github.io/{nom-repo}/`

Exemple : `https://billy94130.github.io/cosse-co-prestashop-ia/`

## VARIABLES DES TEMPLATES

### presentation-template.html
- {{TITRE_PROJET}}
- {{NUMERO_DEVIS}}
- {{MARQUEE_TEXT}}
- {{TITRE_H1_LIGNE1}}, {{TITRE_H1_LIGNE2}}
- {{DESCRIPTION_INTRO}}, {{DESCRIPTION_ACCENT}}
- {{MONTANT_TTC}}, {{MENSUALITE}}, {{DETAIL_MENSUALITE}}
- {{DATE_DEMARRAGE}}, {{DATE_LIVRAISON}}
- {{MODULES_CONTENT}}
- {{CLIENT_NOM}}, {{CLIENT_ADRESSE}}, {{CLIENT_SIRET}}

### devis-template.html
- {{NUMERO_DEVIS}}, {{DATE_DEVIS}}
- {{TITRE_PROJET}}, {{SOUS_TITRE}}
- {{CLIENT_NOM}}, {{CLIENT_ADRESSE}}, {{CLIENT_SIRET}}
- {{PRESTATIONS_ROWS}}
- {{TOTAL_HT}}, {{TVA}}, {{TOTAL_TTC}}
- {{MODALITES_PAIEMENT}}
- {{TIMELINE_COLS}}, {{TIMELINE_ITEMS}}
- {{CHECKLIST_ITEMS}}
- {{COUTS_MENSUELS_ROWS}}, {{TOTAL_MENSUEL}}

### doc-technique-template.html
- {{TITRE_PROJET}}, {{NUMERO_DEVIS}}
- {{CLIENT_NOM}}, {{PERIODE_PROJET}}
- {{DESCRIPTION_PROJET}}
- {{SCHEMA_ARCHITECTURE}}
- {{STACK_TECHNIQUE_ROWS}}
- {{MODULES_PAGE_1}}, {{MODULES_PAGE_2}}
- {{SPECS_SERVEUR_ROWS}}, {{WORKFLOWS_ROWS}}
- {{COUTS_OPERATIONNELS_ROWS}}, {{TOTAL_MENSUEL}}
- {{FORMATION_ITEMS}}

---

Baptiste Fort - Automatisation & IA
