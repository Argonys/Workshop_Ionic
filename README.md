# Workshop sur Ionic

Nous allons réaliser ensemble une petite application nous permettant de prendre des photos (que ce soit sur ordinateur ou téléphone).

## Installations nécessaires

Nous allons d'abord installer le CLI d'Ionic ainsi que native-run et cordova-res. 
Cordova-res nous servira à générer les îcones des applications natives, ainsi que les affichages. Tandis que Native-run nous permettra d'exécuter notre application sur des appareils et des simulateurs/émulateurs.

> npm install -g @ionic/cli native-run cordova-res

Ensuite, nous pouvons déjà créer notre app Ionic (en utilisant Angular) :

> ionic start photo-gallery tabs --type=angular --capacitor

Là, on dit à Ionic de créer une nouvelle application Ionic en la nommant "photo-gallery", en utilisant le template "tabs" (3 pages seront créées avec un système de navigation), en choisissant Angular comme framework et en utilisant Capacitor ; celui-ci nous permet de construire des apps iOS, Android et des PWA en utilisant des technologies web et le tout dans une seule base de code.

On va ensuite se déplacer dans notre dossier photo-gallery

> cd photo-gallery

On va avoir besoin d'utiliser la caméra (de notre ordi, téléphone) et pour cela, les plugins de Capacitor auront besoin de la PWA Elements Library d'Ionic. Pour cela, on va donc installer cette dépendance séparémment.

> npm install @ionic/pwa-elements

Il faudra ensuite aller importer cette dépendance (@ionic/pwa-elements) en éditant le fichier src/main.ts.

```
import { defineCustomElements } from '@ionic/pwa-elements/loader';

// Call the element loader after the platform has been bootstrapped
defineCustomElements(window);
```


Enfin, pour lancer notre application, il suffira d'entrer cette commande dans notre terminal :

> ionic serve

L'application est lancée, vous pouvez désormais naviguer entre les différentes pages qui ont été créées pour nous.

Naviguez jusqu'à 
> /src/app/tab2/tab2.page.html

Et changez les deux <ion-title> en 
  
`
<ion-title>Photo Gallery</ion-title>
`

Ajoutons également un floating action button (souvent abrégé en FAB) à la fin de cette page :

`
<ion-fab vertical="bottom" horizontal="center" slot="fixed">
    <ion-fab-button>
        <ion-icon name="camera"></ion-icon>
    </ion-fab-button>
</ion-fab>
`

Ensuite, allons jusqu'à 
> src/app/tabs/tabs.page.html

Et modifions légèrement le bouton de la tab2 :

`
<ion-tab-button tab="tab2">
  <ion-icon name="images"></ion-icon>
  <ion-label>Photos</ion-label>
</ion-tab-button>
`


