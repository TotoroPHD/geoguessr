# GeoGuessr Maison

Bienvenue sur cette page github qui vous apprendra à utiliser mon code pour faire jouer vos viewers à une version maison de GeoGuessr ! 

## Comment ça se présente ? 

D'abord, vos viewers verront une view tirée de Google Streetview, que vous aurez vous-même choisi.
Les viewers pourront alors proposer un pays dans lequel ils ou elles pensent se trouver. 

Quand vous le souhaitez, vous pouvez arrêter la manche en cours et afficher les résultats, et les distances (de la plus petite à la plus grande) des viewers par rapport à la bonne réponse.

Ensuite, vous pouvez passer au prochain round ! 
Vous pouvez préparer autant de rounds que vous voulez, vous pouvez afficher les scores de la manche, les scores totaux, ou les distances ! Vous pouvez aussi annuler un round qui vient de se finir et le supprimer du total si vous le souhaitez.

Quand un round est fini vous pouvez intéragir avec la source et cliquer sur chaque pseudo pour recentrer la carte sur la proposition de chaque pseudo sur lequel vous cliquez. 

Quelques exemples : 

![vlcsnap-2022-11-15-15h42m10s562](https://user-images.githubusercontent.com/64203596/201948135-13dbf264-4814-4567-b9a6-d7be39346b6d.png)
![vlcsnap-2022-11-15-15h42m23s383](https://user-images.githubusercontent.com/64203596/201948143-64da4018-191e-4737-a086-8074f18cff75.png)
![vlcsnap-2022-11-15-15h43m03s278](https://user-images.githubusercontent.com/64203596/201948144-d3cceb41-2852-4884-b8c0-cbc7fc48d872.png)
![vlcsnap-2022-11-15-15h43m19s632](https://user-images.githubusercontent.com/64203596/201948146-a196e7d9-7565-40b7-b940-02be49dcff65.png)



## Comment intégrer ça dans mon live ?

Tout en haut de cette page, vous cliquez sur le bouton "CODE" en vert, puis sur [Download ZIP](https://github.com/TotoroPHD/geoguessr/archive/refs/heads/main.zip)
![image](https://user-images.githubusercontent.com/64203596/201950773-aee0cc78-042c-4031-b3c0-bccd365e547a.png)

Vous dézippez le dossier que vous venez de télécharger et vous mettez son contenu où vous voulez sur votre disque.
Mais surtout, laissez tous les fichiers dans le même dossier ! 

Il y a 4 fichiers dans le zip : 

* Le fichier [README](README.md) (qui est juste ce que vous êtes en train de lire)
* Le fichier [osm.html](osm.html) (qui est le fichier que vous allez intégrer à OBS en tant que Browser Source)
* Le fichier [coordinates.js](coordinates.js) (qui est le fichier qui contient la liste entière des pays du monde, leurs noms en français, en anglais, et les coordonnées)
* Le fichier [config.js](coordinates.js) (qui est le seul que vous allez utiliser !)


### Etape 1
Tout d'abord, éditez le fichier [config.js](config.js) avec l'éditeur texte de votre choix (bloc notes, notepad++, Visual Studio Code...)
Et changez la variable "nomChaineTwitch" pour mettre le nom de votre chaine.

```Javascript
var nomChaineTwitch = 'TotoroPHD'  // METTEZ ICI LE NOM DE VOTRE CHAINE TWITCH
```

![image](https://user-images.githubusercontent.com/64203596/201952252-241e5562-aa42-4e22-a0f2-4680408d102e.png)

Enregistrez le fichier.

### Etape 2
Ajoutez le fichier [osm.html](osm.html) à OBS en tant que Browser Source, avec 1920 * 1080 comme taille. 

![image](https://user-images.githubusercontent.com/64203596/201953104-75b03cbe-117c-43d2-a3dd-b1974c6da476.png)

Et si tout va bien, vous devriez avoir ceci : 

![image](https://user-images.githubusercontent.com/64203596/201952937-56a98b5a-10d2-4dd4-908c-e7ace121b941.png)

Si c'est OK, vous pouvez taper !start 1, et le premier round commencera !

## Les Commandes

* Pour lancer le round de votre choix, tapez **!start X**, X étant le numéro du round que vous voulez lancer. 
* Pour arrêter le round en cours, tapez **!stop**
* Pour afficher les scores de la manche, tapez **!score**
* Pour afficher à nouveau les distances, tapez **!distance**
* Pour afficher le score total (cumul de tous les rounds), tapez **!total**
* Pour annuler le round en cours (supprimer le score de la manche du score total) tapez **!cancel**

Exemple live : https://www.youtube.com/watch?v=N7WLeK7wLJI

## Comment customiser votre partie ?

Dans le fichier [config.js](config.js) vous avez 2 variables que vous allez pouvoir modifier pour customiser la partie comme vous le souhaitez. 

La première variable, c'est **var googleMaps**

```Javascript
var googleMaps =
    [
        // Round 1 : 
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668032969416!6m8!1m7!1sRSVzAppaX_ITbwFHP8XNBw!2m2!1d39.24420790963297!2d16.54800527578782!3f60.97941790749783!4f0.2563914996873393!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
        // Round 2 : 
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668033034633!6m8!1m7!1szVSOSB34oPGDV2VLxpOPZg!2m2!1d5.023999218177508!2d-74.0050350130003!3f295.78355463927466!4f7.508964159255584!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
        // Round 3 : 
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668033112535!6m8!1m7!1srQFB6-P_-MKJaFaWrUYNzw!2m2!1d23.69315317205257!2d90.43383888749545!3f141.3947!4f0!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
        // Round 4 :
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668033159542!6m8!1m7!1sXAmSMiEw36zSsOQO9nxddQ!2m2!1d-0.444755820265375!2d36.97583812800001!3f186.51127351449344!4f0.8941221602334224!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
        // Round 5 : 
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668033245111!6m8!1m7!1sXaSmQBZlEd86fk1iYByXCQ!2m2!1d56.95756131891078!2d24.18953365922986!3f73.86868520074125!4f0.09349177793050956!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>'
    ]
```

Dans cette variable, vous allez mettre le lien des maps StreetView, un par un, entre symbole apostrophe **'**comme ça**'**, et avec une virgule à la fin.


### Comment récupérer les liens StreetView ?


### Etape 1 : 
Allez sur StreetView, mettez vous où vous le souhaitez, puis cliquez sur les 3 petits points en haut à gauche, puis *Partager ou intégrer l'image*
![image](https://user-images.githubusercontent.com/64203596/201956778-87e755e4-3c78-477b-81eb-d0da77e20824.png)

### Etape 2 : 
Cliquez sur *Intégrer une carte*, puis cliquez sur *Moyenne* pour mettre à la place *Taille Personnalisée*
![image](https://user-images.githubusercontent.com/64203596/201957711-98fb39c7-8c90-4067-bbf7-e3f61cdd9c6b.png)

### Etape 3 ⚠Cette étape est très importante ! ⚠

En taille personnalisée, mettez 1720x1080

![image](https://user-images.githubusercontent.com/64203596/201961060-b30f41bc-faa1-4658-b4b6-93953e05813c.png)
Puis cliquez sur **Copier le contenu HTML**

### Etape 4 
Copier le contenu de votre presse papier entre deux apostrophe à la suite de la variable googleMaps, puis mettez une virgule à la fin. Vous pouvez rajouter un commentaire comme 
```//Round 6```
pour ne pas vous y perdre dans les numéros de round. 
Dans l'exemple en cours, ça donnerait ça : 

```Javascript
var googleMaps =
    [
        // Round 1 : 
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668032969416!6m8!1m7!1sRSVzAppaX_ITbwFHP8XNBw!2m2!1d39.24420790963297!2d16.54800527578782!3f60.97941790749783!4f0.2563914996873393!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
        // Round 2 : 
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668033034633!6m8!1m7!1szVSOSB34oPGDV2VLxpOPZg!2m2!1d5.023999218177508!2d-74.0050350130003!3f295.78355463927466!4f7.508964159255584!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
        // Round 3 : 
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668033112535!6m8!1m7!1srQFB6-P_-MKJaFaWrUYNzw!2m2!1d23.69315317205257!2d90.43383888749545!3f141.3947!4f0!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
        // Round 4 :
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668033159542!6m8!1m7!1sXAmSMiEw36zSsOQO9nxddQ!2m2!1d-0.444755820265375!2d36.97583812800001!3f186.51127351449344!4f0.8941221602334224!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
        // Round 5 : 
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668033245111!6m8!1m7!1sXaSmQBZlEd86fk1iYByXCQ!2m2!1d56.95756131891078!2d24.18953365922986!3f73.86868520074125!4f0.09349177793050956!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
        // Round 6 :
        '<iframe src="https://www.google.com/maps/embed?pb=!4v1668525753652!6m8!1m7!1sRMYaFOhIoMyaqLuZA-t2Fw!2m2!1d47.07261491015031!2d-0.04192361938676371!3f159.73596527628285!4f-11.537726288581965!5f0.7820865974627469" width="1720" height="1080" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
    ]
```



Si vous essayez de relancer la partie maintenant en rafraichissant le navigateur, vous devriez avoir un message d'erreur en haut à droite : 

![image](https://user-images.githubusercontent.com/64203596/201962394-1ded698a-3bf3-49f9-a640-ac5c6a965ffd.png)

En  effet, il y a un problème : La liste des réponses est plus courte que la liste des liens Google Maps.

### Etape 4

Rajoutez simplement le nom du pays qui correspond à la bonne réponse à la suite de la variable **listePays**

#### Avant : 

```Javascript
var listePays =
    [
        'Italie',
        'Colombie',
        'Bangladesh',
        'Kenya',
        'Lettonie',
    ]
```

#### Après : 

```Javascript
var listePays =
    [
        'Italie',
        'Colombie',
        'Bangladesh',
        'Kenya',
        'Lettonie',
        'France',
    ]
```

Et voilà ! Vous avez rajouté un round vous même ! 
vous pouvez supprimer ceux que vous voulez, en rajouter à votre guise, tant que les variables **googleMaps** et **listePays** font la même taille !


### Questions ?
Normalement, vous avez de quoi créer une partie vous même. 
Si jamais vous avez une question ou que vous souhaitez un coup de main pour la mise en place, n'hésitez pas à m'envoyer un MP sur Twitter : @TotoroPHD


### Améliorations à venir
Je compte ajouter la possibilité de remplacer les liens Google StreetView par n'importe quel lien vers une image (URL ou image locale) pour diversifier un peu la possibilité de jeux (exemple : De quel pays est originaire cette chanteuse ?)

Il est aussi envisageable de pouvoir faire un bot qui répond aux viewers (par exemple pour valider que la proposition est bien prise en compte, ou pour donner les scores individuellement) mais cela demanderait de récupérer un OAuth de votre côté, et ça sortait un peu du scope de l'outil livrable tout en main. Si ça vous intéresse, c'est pas compliqué on peut en discuter !

### Limitations
Deux points importants à noter : 
* Les coordonnées des pays sont calculées en fonction du barycentre du pays. Donc le point géographiquement le plus central. Pour des pays avec des formes un peu excentrique, le point central peut être placé un peu bizarrement. Et ça peut être un peu déroutant pour les viewers que des pays tout petits soit plus proches que certains grands pays limitrophes. Mais ça peut aussi être une Meta !

* Il faut que l'orthographe du pays soit exacte. Ca peut être avec ou sans majuscule, avec ou sans tirets, mais il faut que l'orthographe soit exacte, sinon je ne pourrais pas faire la différence entre Irlande et Islande par exemple. Vous pouvez aiguiller vos viewers à l'aide de la liste des pays à laquelle vous avez accès.




