# Boîte à outils du quotidien

Petits outils utiles réunis sur une seule page, rapides et sans compte : **pourboire**, **conversions d'unités**, **budget** et **devises**.

Un seul fichier (`index.html`), sans dépendance, sans étape de build. Interface en français et en anglais, claire ou sombre selon l'appareil, adaptée au mobile.

## Les outils

| Outil | Ce qu'il fait |
|---|---|
| Pourboire | Addition, pourcentage et nombre de personnes : part de chacun, avec arrondi optionnel |
| Conversions | Longueurs, poids, volumes et températures |
| Budget | Revenus et dépenses par catégorie : solde restant et part dépensée |
| Devises | 30 monnaies, taux de la Banque centrale européenne (via [Frankfurter](https://frankfurter.dev)), taux intégrés en secours hors ligne |

## Vie privée

- Aucun compte, aucun suivi, aucune publicité.
- Seuls les réglages (langue, devise, unités, pourcentage de pourboire) sont gardés dans le navigateur (`localStorage`). Les montants ne sont jamais enregistrés.
- Seul l'outil Devises fait une requête externe (GET vers l'API Frankfurter, sans aucun montant).

## Mise en ligne (GitHub + Vercel)

1. Créer un dépôt GitHub et y mettre `index.html` (et ce `README.md`) à la racine.
2. Sur Vercel : **Add New → Project**, importer le dépôt.
3. Laisser les réglages par défaut (Framework : *Other*, pas de commande de build, dossier de sortie vide), puis **Deploy**.

## Ajouter un outil

Tout est dans `index.html` :

1. Écrire une fonction `monOutil(el)` qui remplit le conteneur `el`.
2. Ajouter ses textes `x_t` (titre) et `x_d` (description) dans chaque langue de `I18N`.
3. Ajouter une entrée dans la liste `TOOLS` : `{id, k, color, icon, render}`.

La carte d'accueil, l'adresse (`#/id`) et le titre de la page sont générés automatiquement.

## Ajouter une langue

Copier un bloc de `I18N`, traduire les valeurs, puis ajouter une `<option>` dans le sélecteur `#lang`.

## Description courte (GitHub « About » / projet Vercel)

> Boîte à outils du quotidien : pourboire, conversions, budget et devises. Web app statique en un seul fichier HTML, sans dépendance, FR/EN.

Sujets suggérés : `web-app` `calculator` `unit-converter` `currency-converter` `budget` `vanilla-js` `single-file` `vercel`
