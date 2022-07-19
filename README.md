# WORK IN PROGRESS
# ViewPayConsentBar
Documentation d'intégration de la ViewPay Consent Bar

Ce guide a pour objectif de vous guider dans la mise en place du widget JS Consent Bar de ViewPay dans votre site web.

Pour rappel, Viewpay est une solution de micro-paiement par l'attention publicitaire, qui permet à l'utilisateur de débloquer un contenu premium en regardant une publicité. Le Paywall de ViewPay a été fait pour répondre aux besoins d'éditeurs n'ayant pas de Paywall existant mais souhaitant intégrer ViewPay.

Voici un exemple de déblocage d'article avec Viewpay : 

![sample](https://github.com/TechViewpay/ViewPay-iOS/blob/master/DocImages/parcours_vp_mobile3.png?raw=true)

## Chargement du Javascript
```html
<script type="text/javascript" src="https://cdn.jokerly.com/scripts/VPConsentBar.js?[yourViewPaySiteID]"></script>
```
Le fichier VPConsentBar.js est le seul fichier nécessaire à appeler, celui-ci fera ensuite le travail afin d'appeler les éléments nécessaires pour un moment donné.
Ces fichiers sont installés sur notre CDN afin de vous garantir d'avoir toujours la dernière version.
NB: Il faut placer le script le plus haut possible dans la page afin d’optimiser son temps de chargement.

## Paramètres du fichier JS

yourViewPaySiteID : est le site ID que votre contact ViewPay vous aura transmis, ou que vous aurez récupéré dans votre compte le cas échéant.


## Partie à revoir - Va être simplifié
## Design de ViewPay
Le design CSS est généré automatiquement lors de l’initialisation de Viewpay, ainsi vous n’êtes pas obligés de rajouter du CSS. Cependant, si vous devez changer le design, votre CSS sera pris en priorité. Pour ceci, donnez à ce div les dimensions que vous souhaitez attribuer à Viewpay, en veillant à conserver un ratio largeur/hauteur de 1,44.
Nous imposons 650x450 pour du desktop et de le centrer horizontalement et verticalement.
Voici donc le CSS qui chargeons nous-même :

```css
#cadreJokerlyADS{
	margin: auto;
	top: 0;
	right: 0;
	left: 0;
	position: fixed;
	bottom: 0;
	width: 650px !important;
	height: 450px !important;
	z-index:9999999 !important;
}

//Le z-index est nécessaire à la visibilité de la publicité. 
//Il est impératif de le monter si nécessaire si une frame/bannière/autre est au dessus du nôtre.
//Ceci est obligatoire afin de garantir de CPM élevé.

```
Si vous souhaitez modifier l'une de ces données, n'hésitez pas à contacter votre contact ViewPay

La même chose se passe pour les sites Mobiles/Tablettes. 

Pour votre site mobile, on utilise tout l’espace vertical disponible en ouvrant l’iframe en 100% width et height, sauf si vous spécifiez la taille maximale que vous souhaitez nous offrir.

Les balises média sont les suivantes suivantes afin de permettre aux personnes sur mobile de profiter pleinement de l’interface ViewPay:

```css
@media screen and (max-width: 600px){
	#cadreJokerlyADS{
	width:100% !important;
	height:100% !important;
	margin-top:0;
	}
}
@media screen and ((min-width: 601px) and (max-width: 1024px)){
	#cadreJokerlyADS{
	width:100% !important;
	height:100% !important;
	margin-top:0;
	margin-left:0;
	}
}
```

