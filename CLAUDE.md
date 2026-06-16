# BTP Générale — Site web (contexte projet)

Site d'acquisition de leads pour **BTP Générale**, entreprise générale du bâtiment
basée à Irigny (sud de Lyon). Objectif : générer des **appels** et **demandes de devis**
via le SEO local et un site orienté conversion.

## Infos entreprise (NAP — à garder strictement identiques partout, y compris fiche Google)
- Nom : **BTP Générale**
- Adresse : 24 rue de la Mouche, 69540 Irigny
- Téléphone : 06 59 98 51 98  (format lien : `tel:+33659985198`)
- Email : btpgenerale69@gmail.com
- SIREN : 914 329 487
- Zone : Irigny + sud de la Métropole de Lyon (Pierre-Bénite, Saint-Genis-Laval,
  Oullins, Vernaison, Charly, Feyzin, Brignais, Vénissieux, La Mulatière,
  Sainte-Foy-lès-Lyon, Lyon)

## Positionnement (règles non négociables)
- **Pas de dépannage / urgence** : on vise la rénovation et les projets, pas le SOS plomberie.
- L'entreprise affiche la **garantie décennale**. Elle **n'est PAS RGE** :
  → ne JAMAIS écrire qu'on gère les aides MaPrimeRénov' / qu'on est installateur RGE.
  On peut mentionner que des aides existent pour la rénovation d'ampleur, sans rien promettre.
- Têtes d'affiche : **Façade/ITE · Carrelage · Climatisation/PAC**.
  Produit phare transversal : **rénovation complète tous corps d'état**.

## Le principe central : accueil full-service + pages métier SEO
- **L'accueil (`index.html`)** vend l'entreprise générale : « une seule entreprise pour
  tous vos travaux, de l'idée à la remise des clés ». Le client doit sentir « ils font tout ».
- **Les pages métier** capturent le SEO sur des intentions précises (« façade Irigny »,
  « carreleur Lyon »…). Chacune doit RAPPELER qu'on ne fait pas que ça et renvoyer vers
  l'offre complète (`index.html#services`). Ne jamais diluer le sentiment full-service.

## Stack & contraintes techniques
- **HTML/CSS statique, aucun framework, aucun build.** Priorité : vitesse, mobile-first,
  simplicité de maintenance et de duplication.
- Une seule feuille de style partagée : **`styles.css`** (ne pas la dupliquer par page).
- Polices : Bricolage Grotesque (titres) + Inter (corps), via Google Fonts.
- Accessibilité : focus visible, `prefers-reduced-motion` respecté, alt sur les images.

## Design system (déjà défini dans styles.css)
- Couleurs (variables CSS) : `--petrol #0E5A63` (marque), `--encre #072A2F` (fonds sombres),
  `--brume #E8F4F3` (lavis aqua), `--ambre #F2A526` (boutons d'action), `--craie #FBFAF6` (fond).
- Signature visuelle : petit pictogramme « toiture » repris du logo (voir `.brand .mark`).
- Composants prêts : `.btn`/`.btn--call`/`.btn--solid`/`.btn--ghost`, `.card`, `.chip`,
  `.eyebrow`, `.section`/`.section--tint`/`.section--dark`, `.faq` (details/summary),
  `.photo-ph` (emplacement photo), `.callbar` (barre d'appel mobile), `.form-card`.

## Conversion (présent sur chaque page)
- Téléphone visible dans le header + barre d'appel collante en bas sur mobile (`.callbar`).
- Promesse « devis gratuit sous 24h » répétée.
- Formulaire de devis court + numéro en repli immédiat.

## SEO — checklist par page
Pour chaque nouvelle page, personnaliser :
1. `<title>` = métier (ou commune) + lieu, ex. « Carreleur à Irigny & sud de Lyon ».
2. `<meta name="description">` unique, avec le téléphone.
3. `<link rel="canonical">` propre à la page.
4. `<h1>` unique, aligné sur le mot-clé cible.
5. Bloc JSON-LD `Service` : adapter `serviceType` et `description`.
6. Maillage interne : liens vers l'accueil, les autres pages métier et les pages communes pertinentes.

## Emplacements photos
Remplacer chaque `<div class="photo-ph" data-label="…">…</div>` par
`<div class="photo-ph has-img"><img src="photos/xxx.jpg" alt="description précise"></div>`.
Mettre les images dans un dossier `photos/`. Priorité : vraies photos avant/après de chantiers.

## Formulaire
Brancher l'envoi : soit héberger sur Netlify et ajouter l'attribut `netlify` à `<form>`,
soit remplacer `action="https://formspree.io/f/VOTRE_ID"` par un vrai ID Formspree.

## Roadmap (à construire)
1. ✅ Pages métier sur le gabarit de `facade.html` : `carrelage.html`, `climatisation.html`,
   `renovation.html` (rénovation complète) — faites. Reste à faire : `plomberie.html`, `peinture.html`.
2. Pages par commune (forte priorité leads) : `travaux-pierre-benite.html`,
   `travaux-saint-genis-laval.html`, `travaux-oullins.html`, etc. Contenu réellement
   différencié par commune (pas de copier-coller), sinon Google pénalise.
3. `sitemap.xml` + `robots.txt`.
4. Page mentions légales (SIREN, assurance décennale, hébergeur).
5. Optimisation des images (formats compressés, `loading="lazy"`, dimensions explicites).

## Ton rédactionnel
Français naturel et concret, orienté problème → solution. Phrases courtes. Pas de jargon,
pas de superlatifs creux. Toujours dire ce qui est vrai (cf. règle RGE ci-dessus).
