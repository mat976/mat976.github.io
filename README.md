# CryptoScan — Site web & politique de confidentialité

Site statique (HTML/CSS, aucun build, aucune dépendance) pour l'application
**CryptoScan — On Chain Tracker** (`com.cryptoscan.com`).

## Contenu

| Fichier             | Rôle                                                        |
|---------------------|-------------------------------------------------------------|
| `index.html`        | Landing page (présentation, fonctionnalités, réseaux)       |
| `terms.html`        | Conditions Générales d'Utilisation (CGU en français)        |
| `terms-en.html`     | Terms of Service (EN — version anglaise pour Google Play)   |
| `privacy.html`      | Politique de confidentialité (FR) — URL pour la Play Console |
| `privacy-en.html`   | Privacy Policy (EN) — version anglaise pour la review Google |
| `assets/logo.svg`   | Logo officiel On Chain Wallet / CryptoScan                  |

## Prévisualisation locale

```bash
cd on_chain_website
python3 -m http.server 8080
# → http://localhost:8080
```

## Mise en ligne (au choix)

### Option A — GitHub Pages (recommandé, gratuit, HTTPS inclus)

```bash
cd on_chain_website
git init && git add -A && git commit -m "Site CryptoScan"
git remote add origin git@github.com:<ton-compte>/cryptoscan-site.git
git push -u origin main
```

Puis dans GitHub : **Settings → Pages → Source : main / root**.
URL obtenue : `https://<ton-compte>.github.io/cryptoscan-site/`

### Option B — Netlify / Cloudflare Pages

Glisser-déposer le dossier sur <https://app.netlify.com/drop> ou connecter le
repo sur Cloudflare Pages. HTTPS et disponibilité mondiale inclus.

## Play Console

Une fois le site en ligne :
- Dans **Fiche Play Store → Règles de confidentialité** :
  ```
  https://<ton-domaine>/privacy.html
  ```
  (ou `privacy-en.html` en anglais)
- Si demandé dans la fiche ou pour les conditions d'utilisation :
  ```
  https://<ton-domaine>/terms.html
  ```
  (ou `terms-en.html` en anglais)

Points de conformité Google vérifiés :

- page Web standard (pas de PDF), accessible sans connexion ni géorestriction ;
- HTTPS valide (GitHub Pages / Netlify / Cloudflare le fournissent) ;
- politique spécifique à l'app : collecte locale SQLite, endpoints RPC tiers,
  SDK Google Mobile Ads / UMP, droits RGPD ;
- prévoir aussi un lien vers cette URL **dans l'app** (écran Réglages / Mentions
  légales) : Google l'exige sur la fiche *et* dans l'application.

## À personnaliser

- `matisse.demontis@proton.me` : adresse de contact indiquée dans la politique —
  remplacer par l'adresse réelle du compte développeur si différente.
- Date « Dernière mise à jour » : ajuster au jour de publication.
- `assets/logo.svg` : remplacer par le futur logo si l'icône de l'app change.
