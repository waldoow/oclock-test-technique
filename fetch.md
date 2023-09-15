# Fetch

## Definition

La methode `fetch` permet d'envoyer des requetes HTTP en javascript et d'avoir une réponse et le tout sans recharger la page.

Cela nous permet d'afficher des données présentent en base ou des données qui sont coté serveur et sans rechargement de la page.


### Signature de la fonction
```javascript
    let promise = fetch(url, [options]);
```

Ici, on peut voir plusieurs choses:
- `promise`
- `url`
- `[options]`

### Qu'est-ce qu'une promise ?
une `Promise` est un objet qui nous permet de faire un traitement asynchrone, ce qui ne bloque pas l'execution du code.

### URL
Ici l'`url` est une `string` qui va être appelée.

### OPTIONS
`[options]` correspond un objet javascript est <span style="color: yellow;"> optionnel </span>, ce qui veut dire qu'il n'est pas obligatoire.
 Il y a plusieurs `[options]` dont les plus courantes sont:
- method (string)
- headers (objet javascript)
- body (json)

Quand on regarde les options, on voit une option `method`, il faut savoir que si l'on ne met pas d'options, `fetch`
fait une requete HTTP en `GET`

Si l'on veut faire un `POST`, en reprenant le projet précédent, l'écriture se fait comme ceci:
```javascript
    let response = fetch('http://localhost:8000/signin', {
        method: 'POST',
        ...
    })
```

La methode `POST` dans notre exemple pour authentifier un user doit contenir un e-mail et un password, pour ce faire on ajoute un `body`a la requete:
```javascript
    let body = {
        email: 'lucie@skoule.fr',
        password: 'cameleons'
    };

    let response = fetch('http://localhost:8000/signin', {
        method: 'POST',
        // Comme on a dit plus haut que le body devait etre au format JSON, ici on le converti
        body: JSON.stringify(body)
    });
```

## Enfin on attend la reponse
Comme nous l'avons vu plus haut, la methode `fetch` est asynchrone, nous devons utiliser un mot clé pour dire que nous `attendons` la reponse:

Ce mot clé est `await`

```javascript
    let body = {
        email: 'lucie@skoule.fr',
        password: 'cameleons'
    };

    let response = fetch('http://localhost:8000/signin', {
        method: 'POST',
        body: JSON.stringify(body)
    });
   
    // qui nous permet de lire le corp de la réponse 
    let result = await response.json();
```

## Écriture différente
On a vu plus haut une manière d'écrire un `fetch` mais la plus connue est celle-ci, comme ça si jamais tu la vois tu ne seras pas perdu :)
```javascript
    let body = {
        email: 'lucie@skoule.fr',
        password: 'cameleons'
    };

    let result = fetch('http://localhost:8000/signin', {
        method: 'POST',
        body: JSON.stringify(body)
    })
    .then(response => response.json());
```

Avec une écriture de cette manière, tu peux aussi attraper les erreurs possibles avec la methode `catch`:
```javascript
    let body = {
        email: 'lucie@skoule.fr',
        password: 'cameleons'
    };

    let result = fetch('http://localhost:8000/signin', {
        method: 'POST',
        body: JSON.stringify(body)
    })
    .then(response => {
        // ici on regarde si on a bien 200 (donc nous somme bien connecté) 
        if (response.ok) {
            console.log('je suis connecté !');
        }
    })
    .catch(error => {
        // ici je vais avoir les erreurs s'il y en ya, exactement comme dans tes controllers pour geres les champs
        // de formulaires ne sont pas valide :)
        console.log("j'ai eu un soucis sur le fetch: " + error.message)
    });
```

Voilaaaa dans les grandes lignes comment le `fetch` fonctionne ;)

Faut juste jouer avec et Have fun ;) 

