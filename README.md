# WORK IN PROGRESS
# ViewPayConsentBar
Documentation d'intégration de la ViewPay Consent Bar

Ce guide a pour objectif de vous guider dans la mise en place du widget JS Consent Bar de ViewPay dans votre site web.

Pour rappel, Viewpay est une solution de micro-paiement par l'attention publicitaire, qui permet à l'utilisateur de débloquer un contenu premium en regardant une publicité. La Consent Bar de ViewPay a été fait pour répondre aux besoins d'éditeurs souhaitant encourager leurs utilisateurs réfractaires au consentement à les soutenir.

Voici un exemple de déblocage d'article avec Viewpay : 

![sample](https://github.com/TechViewpay/ViewPay-iOS/blob/master/DocImages/parcours_vp_mobile3.png?raw=true)

## Chargement du Javascript
```html
<script type="text/javascript" src="https://cdn.jokerly.com/scripts/VPConsentBar.js?[yourViewPaySiteID]"></script>
```
Le fichier VPConsentBar.js est le seul fichier nécessaire à appeler, celui-ci fera ensuite le travail afin d'appeler les éléments nécessaires pour un moment donné.
Ce fichier est installé sur notre CDN afin de vous garantir d'avoir toujours la dernière version.
NB: Il faut placer le script le plus haut possible dans la page afin d’optimiser son temps de chargement.

## Paramètres du fichier JS

yourViewPaySiteID : est le site ID que votre contact ViewPay vous aura transmis, ou que vous aurez récupéré dans votre compte le cas échéant.


## Besoin de rajouter la possibilité d'insérer un bouton pour rouvrir la CMP
