# INSTRUCTIONS AUTOMATISATION DEVIS - BAPTISTE FORT

## WORKFLOW AUTOMATIQUE - AUCUNE QUESTION

Quand l'utilisateur envoie une transcription de devis, tu DOIS :

1. **Creer le dossier mission** : `missions/{nom-client-slug}/`
2. **Generer index.html** : Site presentation complet
3. **Generer devis-{numero}.html** : Devis PDF format A4
4. **Generer doc-technique.html** : Documentation technique PDF format A4
5. **Deployer sur GitHub** :
   - `git init`
   - `git add .`
   - `git commit -m "Initial commit"`
   - `gh repo create {nom-client-slug} --public --source=. --push`
   - `gh api repos/{owner}/{nom-client-slug}/pages -X POST -F source[branch]=master -F source[path]=/`
6. **Retourner les liens** sans poser de questions

## IMPORTANT - REGLES STRICTES

- **AUCUNE QUESTION** - Ne jamais demander de confirmation
- **AUCUNE DEMANDE D'ACCEPTATION** - Tout doit etre automatique
- **GENERER TOUT** directement depuis la transcription
- **RETOURNER** uniquement :
  - Lien GitHub Pages : `https://{username}.github.io/{repo}/`
  - Confirmation que les fichiers PDF sont dans `missions/{client}/`

## FORMAT DE SORTIE

```
Site deploye : https://billy94130.github.io/{nom-repo}/

Fichiers generes dans missions/{nom-client}/ :
- index.html (site presentation)
- devis-{numero}.html (ouvrir dans Chrome > Ctrl+P > PDF)
- doc-technique.html (ouvrir dans Chrome > Ctrl+P > PDF)
```

## TEMPLATES DISPONIBLES

- `presentation-template.html` - Structure site presentation
- `devis-template.html` - Structure devis 2 pages A4
- `doc-technique-template.html` - Structure doc technique 3 pages A4
- `exemple-complet/` - Exemple reel (Cosse & Co)

## STYLE GRAPHIQUE

- Couleur principale : #C9A962 (or)
- Couleur secondaire : #1a1a1a (noir)
- Police : Inter, Space Grotesk, Syne, JetBrains Mono
- Style : Brutalist, ombres dures, bordures 2px

## EXTRACTION DES DONNEES

Depuis la transcription, extraire :
- Nom client, adresse, SIRET
- Numero devis (format DEV-YYYY-XXX)
- Titre projet
- Modules/prestations avec descriptions et prix
- Planning (mois, phases)
- Montants (HT, TVA, TTC, mensualites)
- Couts operationnels mensuels
- Stack technique si mentionne
