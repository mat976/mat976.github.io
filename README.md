# Site web multi-applications (GitHub Pages)

Site statique (HTML/CSS, aucun build) hébergé sur `https://mat976.github.io/`.
Chaque application vit dans **son propre sous-dossier**, ce qui permet d'en
ajouter d'autres sans toucher aux URL existantes.

## Structure

```
/
├── index.html                  Portail : liste des applications
├── privacy.html                ↳ redirection vers CryptoScan/
├── privacy-en.html             ↳ redirection
├── terms.html                  ↳ redirection
├── terms-en.html               ↳ redirection
├── data-deletion.html          ↳ redirection
├── data-deletion-en.html       ↳ redirection
└── CryptoScan/
    ├── index.html              Landing page
    ├── privacy.html            Politique de confidentialité (FR)
    ├── privacy-en.html         Privacy Policy (EN)
    ├── terms.html              CGU (FR)
    ├── terms-en.html           Terms of Service (EN)
    ├── data-deletion.html      Suppression des données (FR)
    ├── data-deletion-en.html   Data deletion (EN)
    └── assets/                 CSS, logo, favicon, captures
```

## URL à utiliser dans la Play Console

| Champ | URL |
|---|---|
| Règles de confidentialité | `https://mat976.github.io/CryptoScan/privacy.html` |
| (version EN) | `https://mat976.github.io/CryptoScan/privacy-en.html` |
| Conditions d'utilisation | `https://mat976.github.io/CryptoScan/terms.html` |
| Suppression des données | `https://mat976.github.io/CryptoScan/data-deletion.html` |
| Site web (fiche) | `https://mat976.github.io/CryptoScan/` |

Les anciennes URL à la racine (`/privacy-en.html`, `/data-deletion.html`…)
existent toujours sous forme de redirections : les liens déjà enregistrés
dans la Play Console continuent de fonctionner.

## Ajouter une nouvelle application

1. Créer un dossier au nom de l'app : `MonAppli/`
2. Y copier la structure d'une app existante (`index.html`, `privacy*.html`, `terms*.html`, `assets/`)
3. Ajouter une carte dans le `index.html` racine (bloc `<main>`)
4. Si l'ancienne app avait des pages à la racine, créer les redirections correspondantes

## Prévisualisation locale

```bash
cd on_chain_website
python3 -m http.server 8080
# → http://localhost:8080
# → http://localhost:8080/CryptoScan/
```

## Déploiement

Repo GitHub Pages (`mat976/mat976.github.io`) : un simple `git push` sur `main`
publie le site à `https://mat976.github.io/`.

## Points de conformité Google

- page Web standard (pas un PDF), accessible sans connexion ni géorestriction
- HTTPS valide (fourni par GitHub Pages)
- politique spécifique à l'app : stockage local SQLite, endpoints RPC tiers,
  SDK Google Mobile Ads / UMP, droits RGPD
- lien vers la politique également **dans l'app** (Réglages → Mentions légales)
