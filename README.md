# backon-medias

Hébergement temporaire des visuels publiés sur les réseaux sociaux de
[BackOn Running](https://backonrunning.com).

Les plateformes de publication, Instagram via l'API de Meta comme Metricool,
ne reçoivent pas le fichier : on leur donne une adresse, et leur serveur va
chercher l'image. Elle doit donc être accessible publiquement au moment de la
publication. C'est la seule raison d'être de ce dépôt.

## Ce qu'on y met, et ce qu'on n'y met pas

Uniquement les visuels finaux, ceux qui vont de toute façon paraître
publiquement sur les comptes de BackOn.

Jamais les photos sources sous licence, jamais les gabarits, jamais le corpus
clinique, jamais un contenu non validé. Tout cela vit dans le dépôt privé
`backon-brand`.

## Dépôt au plus juste

Un fichier est déposé **juste avant** sa publication et retiré une fois
celle-ci faite. Un dépôt public qui contiendrait trois mois de visuels à
l'avance rendrait tout le calendrier éditorial lisible par n'importe qui.

Le script qui s'en charge est `publier/medias.mjs`, dans `backon-brand`.

## Adresses

Les fichiers sont servis par GitHub Pages :

```
https://mimicode31.github.io/backon-medias/medias/<nom>.jpg
```

`robots.txt` interdit l'indexation. Ce n'est pas une protection, seulement de
l'hygiène : ces visuels n'ont pas à remonter dans les résultats de recherche à
la place des pages du site.

## Format

JPEG, qualité 92, en 4:4:4. Meta n'accepte que le JPEG pour les images.

À cette qualité, un visuel 1080 x 1350 pèse environ 230 ko pour 46 dB de
PSNR face au PNG d'origine, ce qui est largement au-dessus du seuil visible.
Le 4:4:4 est imposé explicitement plutôt que laissé au défaut : au-dessus de
la qualité 90 l'encodeur le choisit seul, mais dès 80 il retombe en 4:2:0, et
sur du texte cyan posé sur du marine cela bave autour des lettres.
