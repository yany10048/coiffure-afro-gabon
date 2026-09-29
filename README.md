# Naya Hair Studio

Site vitrine du salon de coiffure mixte **Naya Hair Studio** à Libreville (Gabon) : cheveux afro, bouclés, lisses et européens.

Tout le site tient dans un seul fichier, `index.html` (HTML, CSS et JavaScript), sans dépendance à installer.

## Fonctionnalités

- 10 pages : Accueil, Coiffure Afro, Cheveux Lisses, Nos Coiffeurs, Galerie, Tarifs, Boutique, Réserver, À propos, Contact
- Formulaire de réservation qui génère le message WhatsApp
- Boutique avec panier, frais de livraison et commande sur WhatsApp
- Galerie filtrable, curseurs avant/après, avis clients
- Bouton WhatsApp flottant, responsive mobile, balises SEO

## Mise en ligne avec GitHub Pages

1. Créez un dépôt sur GitHub (par exemple `naya-hair-studio`).
2. Déposez-y `index.html` et `README.md` (bouton **Add file → Upload files**).
3. Allez dans **Settings → Pages**.
4. Dans **Source**, choisissez **Deploy from a branch**, puis la branche `main` et le dossier `/ (root)`. Cliquez sur **Save**.
5. Après une à deux minutes, le site est visible à l'adresse `https://VOTRE-PSEUDO.github.io/naya-hair-studio/`.

## À personnaliser avant la mise en service

Toutes les valeurs ci-dessous sont des exemples. Cherchez-les dans `index.html` (Ctrl+F) :

| Élément | Où le changer |
|---|---|
| Numéro WhatsApp | `const WA = "24177000000";` au début du script (format international, sans `+` ni espaces) |
| Téléphone affiché | rechercher `+241 77 00 00 00` |
| Adresse | rechercher `Boulevard Triomphal` |
| Email | rechercher `contact@nayahairstudio.ga` |
| Réseaux sociaux | rechercher `instagram.com`, `tiktok.com`, `facebook.com` |
| Prix et durées | tableaux `AFRO` et `LISSES` dans le script |
| Coiffeurs | tableau `TEAM` |
| Produits de la boutique | tableau `PRODUCTS` |
| Frais de livraison | tableau `DELIV` |
| Avis clients | tableau `REVIEWS` |
| Horaires | tableau `HRS` et le bloc « Nous trouver » du pied de page |

## Remplacer les visuels par de vraies photos

Les images actuelles sont des motifs dessinés en SVG par la fonction `art()`. Pour utiliser des photos :

1. Créez un dossier `images/` dans le dépôt et déposez-y vos photos (format `.jpg` ou `.webp`, largeur 1200 px environ).
2. Remplacez l'appel `art(...)` par une balise image, par exemple :
   ```js
   `<img src="images/knotless.jpg" alt="Knotless braids" style="width:100%;height:100%;object-fit:cover">`
   ```