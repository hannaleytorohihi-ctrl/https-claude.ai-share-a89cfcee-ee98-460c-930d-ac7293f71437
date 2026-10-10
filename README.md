# La jefa — site

Site vitrine de **La jefa** : réussite personnelle et professionnelle. Une seule page (`index.html`), sans outil de compilation ni dépendance à installer. Les polices viennent de Google Fonts.

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `index.html` | Le site entier : pages, styles et scripts. |
| `404.html` | Page affichée si une adresse n'existe pas. |
| `.nojekyll` | Dit à GitHub Pages de publier les fichiers tels quels. |
| `README.md` | Cette notice. |

## Publier sur GitHub Pages

1. Dépôt **public** (le plan gratuit de GitHub l'exige pour Pages).
2. **Settings → Pages**.
3. *Build and deployment* → Source : **Deploy from a branch**.
4. Branche **main**, dossier **/ (root)** → **Save**.
5. Attends une à deux minutes : l'adresse apparaît en haut de la page Pages (`https://utilisateur.github.io/nom-du-depot/`).

Chaque modification poussée sur `main` met le site à jour toute seule.

## Ce qu'il faut renseigner avant d'ouvrir au public

Tout se règle dans `index.html`, dans deux blocs que tu trouves en cherchant `const CFG=` puis `const LEGAL=` :

- `CFG.checkout` : adresse de ta page de paiement (hébergée par ton prestataire). Vide, la vente n'est pas ouverte.
- `CFG.price`, `CFG.email`, `CFG.social` : prix affiché, e-mail de réception, profils sociaux. Vide, l'élément reste inactif.
- `LEGAL` : nom de l'éditeur, statut, numéro d'immatriculation, adresse, hébergeur, tribunal compétent. Ces champs alimentent les mentions légales, les CGU et la page données. Tant qu'ils sont vides, les pages légales sont incomplètes.

## Référencement

Le site est volontairement **non indexé** (`<meta name="robots" content="noindex, nofollow">` dans `index.html`). Supprime cette ligne quand les pages légales sont complètes.

## Limites à connaître

- **GitHub Pages est un hébergement statique.** Il n'y a ni base de données, ni serveur. Conséquences : l'inscription et la connexion y sont un **aperçu** (rien n'est envoyé ni enregistré), il n'y a pas d'espace administrateur, et le mur des engagements partagé n'est pas disponible. Le reste du site fonctionne.
- Pour de vrais comptes sur GitHub Pages, il faut un service externe (Supabase, Firebase, Clerk, Auth0…), branché dans `CFG.auth.signup`. Le mot de passe ne doit voyager qu'en HTTPS vers ce service, jamais être stocké dans la page.
- **Le dépôt est public : tout ce qu'il contient est lisible par tout le monde.** N'y mets jamais de mot de passe, de clé d'API, de fichier d'ebook à vendre, ni de données de clients.

## Droits

Contenu, textes et identité visuelle : © La jefa, tous droits réservés.
