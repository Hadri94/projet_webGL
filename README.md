# Projet WEBGL : Gare futuriste

## Attention

Les chemins des imports ne sont plus valide. Il faut suivre les nouveaux chemins du projet. ``jsm\le_fichier.js``

### Ajouter un import

- copier le fichier dans le dossier ``/jsm``
- verifier les imports à l'interieur du fichier
- lors de l'import ajouter le nouveau chemin


## Touche

Des touches qui peuvent être utile lors de la création des scènes

- `Backspace` : permet de bloquer l'axe de rotation. 
- `Enter` : permet d'éxecuter une/des ligne(s) de commande(s).

### Ajouter une ligne de commande

- rechercher cette ligne ``one_time && event.key == 'Enter'``
- à l'interieur de cette condition, ajouter vos lignes de commandes.

Les commandes peuvent être un ``console.log()`` ou ``camera.position.set()``...

### Ajouter une nouvelle touche

- au dessus de la fonction ``animate()``, ajouter une variable ``one_time_`` suivit de votre ``touche``. Initialiser là à ``false``
- dans le ``addEventListener(keydown)``, ajouter votre ``variable = true;``.  
- dans le ``addEventListener(keyup)``, creer une condition ``if(votre_variable && event.key == 'votreTouche'``
- à l'interieur de cette condition créée, ajouter vos lignes de commandes. Après vos lignes, ajouter ``votre_variable = false;``.

### Exemple : ajout d'une nouvelle touche

```js
let one_time_enter = false;
function animate() { 

    requestAnimationFrame( animate ); //de base pour animate() 

    document.addEventListener('keydown', function(event) {
        one_time_enter = true;
    });
    
    document.addEventListener('keyup', function(event) {
        if(one_time_enter && event.key == 'Enter') {
            //Ajouter vos lignes de commmandes
            console.log(camera.position); 
            one_time_enter = false;
        }
    });
}
```

## loading manager

Le loading permet d'afficher le chargement des fichiers dans la console.

### ajouter un _load_

- lors de la création du _load_, ajouter la variable ``manager`` dans la fonction de création.

### Exemple : ajout d'un nouveau _load_

```js
const station_loader = new FBXLoader( manager );
```


### note extra
- la variable `songElement` est un tableau qui a le son des deux haut-parleurs. ```songElement[0].play()```

