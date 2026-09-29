# Somatrans Inter

Site de **Somatrans Inter**, entreprise de transit, transport, manutention et logistique basée à Libreville / Owendo (Gabon).

Tout le site tient dans un seul fichier, `index.html` (HTML, CSS et JavaScript), sans dépendance à installer.

## Pages

Accueil · Nos services · Transit & Douane · Transport · Manutention · Conteneurs · Logistique · Import / Export · Location d'engins · Demande de devis · À propos · Nos moyens · Réalisations · Contact

Les pages sont servies depuis le même fichier grâce aux ancres : `index.html#transit`, `index.html#devis`, etc.

## Mise en ligne avec GitHub Pages

1. Créez un dépôt sur GitHub (par exemple `somatrans-inter`).
2. Déposez `index.html` et `README.md` (**Add file → Upload files**).
3. Allez dans **Settings → Pages**, choisissez **Deploy from a branch**, branche `main`, dossier `/ (root)`, puis **Save**.
4. Après une à deux minutes, le site est en ligne sur `https://VOTRE-PSEUDO.github.io/somatrans-inter/`.

## Recevoir les devis par email (optionnel)

Par défaut, le bouton « Envoyer ma demande de devis » prépare le message et propose de l'envoyer sur WhatsApp.

Pour recevoir les demandes par email, **avec les pièces jointes** (facture, BL, packing list, photo) :

1. Créez un compte gratuit sur [formspree.io](https://formspree.io) et un nouveau formulaire.
2. Copiez l'adresse fournie (du type `https://formspree.io/f/abcdwxyz`).
3. Dans `index.html`, collez-la sur la ligne `const FORM_ENDPOINT = "";`, entre les guillemets.

Le bouton WhatsApp continue de fonctionner en parallèle.

## À personnaliser avant la mise en service

Toutes ces valeurs sont des exemples. Cherchez-les dans `index.html` (Ctrl+F) :

| Élément | Où le changer |
|---|---|
| Numéro WhatsApp | `const WA = "24166000000";` (format international, sans `+` ni espaces) |
| Téléphone affiché et liens d'appel | rechercher `+241 66 00 00 00` et `tel:+24166000000` |
| Email | rechercher `contact@somatrans-inter.ga` |
| Adresse | rechercher `zone portuaire d'Owendo` et `quartier Glass` |
| Réseaux sociaux | rechercher `facebook.com`, `linkedin.com`, `instagram.com`, `tiktok.com` |
| Chiffres clés | attributs `data-count="2500"`, `data-count="180"`, `data-count="12"` |
| Véhicules | tableau `FLEET` |
| Engins et disponibilités | tableau `ENGINS` (`st:"ok"` disponible, `"res"` sur réservation, `"mis"` en mission) |
| Réalisations | tableau `PROJ` |
| Nos moyens | tableau `MOY` |
| Équipe | rechercher `J. Mboumba` |
| Horaires | tableau `HRS` et pied de page |
| RCCM / NIF | rechercher `RCCM et NIF à compléter` |

## Remplacer les illustrations par de vraies photos

Les visuels actuels sont des illustrations SVG générées par la fonction `ill()`. Pour mettre vos photos :

1. Créez un dossier `images/` dans le dépôt et déposez-y vos photos (`.jpg` ou `.webp`, environ 1200 px de large).
2. Dans la fonction qui dessine une carte (par exemple `engCard`), remplacez `${ill(e.k,false,e.cap)}` par :
   ```js
   `<img src="images/${e.photo}" alt="${e.n}" style="width:100%;height:100%;object-fit:cover">`
   ```
   puis ajoutez un champ `photo:"hyster-3t.jpg"` à chaque engin du tableau `ENGINS`.

## Évolutions prévues

L'architecture est prête pour ajouter de nouvelles pages : créez un bloc `<div class="page" id="p-NOM">` et ajoutez la route dans l'objet `ROUTES` du script.

Le suivi de colis et de conteneurs, l'espace client, la connexion entreprise, les factures, les documents de transit, l'historique des opérations, le paiement en ligne, les notifications WhatsApp et le suivi GPS demanderont un serveur et une base de données (par exemple Supabase, Firebase ou une API dédiée). Le champ « Suivre un conteneur » de l'accueil est déjà en place et renvoie pour l'instant vers WhatsApp.