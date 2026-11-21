# JOLCAKES – Site de réservation

Site statique (un seul fichier `index.html`) : choix de la formule, date, groupe jusqu'à 35 personnes, paiement d'un acompte ou du total, ou demande de devis.

## 1. Mettre le site en ligne sur GitHub

1. Créez un dépôt sur github.com (par exemple `jolcakes-reservation`), public.
2. Envoyez-y `index.html` (Add file > Upload files).
3. Dépôt > Settings > Pages > Source : *Deploy from a branch*, branche `main`, dossier `/ (root)`.
4. Après une minute, le site est disponible sur `https://VOTRE-COMPTE.github.io/jolcakes-reservation/`.

## 2. Régler le site

Tout se règle dans le bloc `CONFIG` au début du script de `index.html` : e-mail, téléphone, adresse, pourcentage d'acompte, délai minimum, formules et tarifs.

## 3. Recevoir les demandes

- **Simple** : laissez `formspree` vide. La demande s'ouvre dans l'application mail du client, adressée à votre e-mail.
- **Recommandé** : créez un formulaire gratuit sur formspree.io et collez son URL dans `formspree`. Vous recevez chaque demande par e-mail, sans que le client ait besoin d'une application mail.

## 4. Activer le paiement en ligne

GitHub Pages ne peut pas encaisser seul : le paiement passe par un prestataire.

1. Créez un compte Stripe, puis des **liens de paiement** (Payment Links) : un pour l'acompte et un pour le total de chaque formule.
2. Collez-les dans `links: { acompte: "...", total: "..." }` de la formule.
3. Si vous renseignez un tarif (`price`), le site calcule et affiche le montant. Pensez à créer des liens de paiement au même montant.

Tant qu'un lien n'est pas renseigné, le client envoie sa demande et vous lui renvoyez le lien de paiement après confirmation du créneau.

Les formules « tarif : nous consulter » restent sans prix affiché jusqu'à ce que vous renseignez `price`.
