# LP3D Studio — site vitrine

Site statique de LP3D Studio (LP3D Studio, LP3D Medical, LP3D Aerospace), publié avec GitHub Pages sur **https://lp3d-studio.com**.

## Contenu

| Dossier / fichier | Rôle |
|---|---|
| `index.html` | Accueil (français, langue par défaut) |
| `studio/`, `medical/`, `aerospace/`, `salon/` | Pages produits et offre salon |
| `defense/` | Ancienne adresse de LP3D Defense, renvoie vers `aerospace/` |
| `support/`, `conditions/`, `confidentialite/`, `mentions-legales/` | Support et pages légales |
| `en/`, `it/`, `es/`, `de/`, `ja/`, `zh/`, `ar/` | Versions traduites |
| `assets/` | Feuille de style, script, polices, logos et captures |
| `404.html` | Page d’erreur (servie automatiquement par GitHub Pages) |
| `sitemap.xml`, `robots.txt` | Référencement |
| `CNAME` | Domaine personnalisé `lp3d-studio.com` |
| `_i18n/` | Textes sources des traductions (non publiés : GitHub Pages ignore les dossiers commençant par `_`) |

Aucune étape de compilation : les fichiers sont servis tels quels.

## Publication sur GitHub Pages

1. Créer un dépôt sur GitHub (par exemple `lp3d-studio-site`).
2. Pousser ce dossier :
   ```bash
   git remote add origin https://github.com/<compte>/lp3d-studio-site.git
   git push -u origin main
   ```
3. Sur GitHub : **Settings → Pages → Build and deployment** : *Deploy from a branch*, branche `main`, dossier `/ (root)`.
4. Dans **Settings → Pages → Custom domain**, vérifier `lp3d-studio.com`, puis cocher **Enforce HTTPS** une fois le certificat émis.
5. Chez le registraire du domaine (zone DNS de lp3d-studio.com) :
   - 4 enregistrements `A` sur `@` : `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` ;
   - un enregistrement `CNAME` `www` → `<compte>.github.io`.

Sans domaine personnalisé (adresse `<compte>.github.io/lp3d-studio-site/`), supprimer `CNAME` : la page 404 utilise des liens absolus (`/assets/...`) qui ne fonctionnent qu’à la racine d’un domaine.

## Mise à jour

Modifier les fichiers, puis :
```bash
git add -A && git commit -m "Mise à jour du site" && git push
```
GitHub Pages republie le site en une à deux minutes.

---
Éditeur : Louis Petroff, LP3D Studio — contact@lp3d-studio.com — 29 octobre 2026
