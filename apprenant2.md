# Feedback Apprenant 2

> Certaines notions sont présents ce qui est très bien, j'aperçois quand même quelques lacunes que l'on va essayer
> de détailler ensemble. Au début, c'est toujours un peu compliqué, mais si je peux te donner un conseil, c'est d'essayer de faire
> une partie complête sans s'éparpiller. Par exemple, dans cet exercice, la logique pour les formateurs et les étudiants est la même,
> je m'explique, on peut ajouter des nouveaux étudiants et formateurs, les modifiers, les lister et les supprimer, du coup la logique reste la même
> une fois que tu l'as fait pour un, on ne réinvente pas la roue, on fait pareil :)

> Il faut persevere, tu vas avoir le déclick. 

## Partie Teacher

> Tu as réussi à lister les formateurs ce qui est très bien.

> Pour la liste des formateurs le bouton jaune sert à éditer un formateur, pour cela on doit générer une route, qui contient l'id du formateur
> avec la fonction `generate`, la route `/teachers/[id]` le `[id]` signifie qu'il n'est pas fixe pour rendre les routes réutilisable.
> <br />
> il faut donc géréner la route avec tout ses parametre ce qui va correspondre à un controller et une action donnée.
> 
```php
// ici la fonction generate a deux parameters, le premier qui est la route en question et le second qui est optionnel et qui permet d'ajouter 
// l'id à la route
$router->generate('/teachers/', ['id' => $teacher->getId()])
```

> Ce qui va nous rediriger vers l'action du controller qui est la fonction `update($teacherId)` qui avec l'id va nous retrouver un teacher
> et nous retourner le formulaire avec les informations du teacher à éditer.

> Quand on voudra sauvegarder cela sera le même fonctionnement, mais on vérifiera quand meme que les informations soient valide, toujours avec l'id
> du teacher.

> Enfin, ton bouton pour éditer sur les listes correspond à celui pour créer un Teacher. Il faut le sortir du tableau et le mettre au-dessus de manière generale
> pour des soucis de hiérarchie visuelle 


> En Conclusion, ce type de fonctionnement pour les Actions, Delete et Edit du projet, Teachers comme Students :).

<hr />

## Partie Student

> Sur la Partie Students ce qui te cause cette erreur, même si celle-ci n'est pas très claire, c'est qu'il te manque un attribut `$teacher_id`
> qui permet de lier un Student à un Teacher.

> Pour le reste, comme expliqué plus haut pour les teachers, s'applique ici aussi car la seule différence, c'est l'objet que tu utilises, sinon la 
> logique et les mécanismes sont les mêmes.
 

  
