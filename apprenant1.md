# Feedback Apprenant 1

## Partie Teacher


### Update d'un teacher:

#### Le formulaire:
```php
public function teacherUpdatePost($teacherid)
```
- voici la definition de ta fonction php pour faire une modification sur un teacher en base de donnée.

```php
<form action="<?= $router->generate('teacher_update_post') ?>" method="POST" class="mt-5">
```
- et voici ta balise d'ouverture du formulaire pour faire la mise a jour.
> comme tu peux le voir ici, y a un petit soucis, dans ta function, tu lui dis que tu as besoin de l'Id ton teacher dans la signature de ta fonction mais quand tu génères la route avec le `$router` tu le lui passes l'id en paramètres.
> Donc quand tu fais ton `POST`  le router génère une route avec la method `POST` `/teacher/` qui n'existe pas et te retourne une 404

<hr>

#### La verification des données:
```php
...
$teacherFromDb = Teacher::find($teacherid);  
  
if(isset($_POST) && !empty($_POST)) {
	$teacherFromDb->setFirstname($firstname);  
	$teacherFromDb->setLastname($lastname);  
	$teacherFromDb->setJob($job);  
	$teacherFromDb->setStatus($status);  
	  
	// Gestion de erreurs  
	if(empty($firstname)) {  
	  $errorList[] = "Le prénom est vide ou invalide !";  
	}  
	if(empty($lastname)) {  
	  $errorList[] = "Le nom est vide ou invalide !";  
	}  
	if(empty($job)) {  
	  $errorList[] = "Le titre est vide ou invalide !";  
	}  
	if(empty($status)) {  
	  $errorList[] = "Le status est vide ou invalide !";  
	}
...
```
> dans cette partie du code, il faut structurer ta logique, dans un premier temps on verfie les données, et ensuite s'il n'y a pas d'erreurs, on peut apporter les modifications.
> Ce que tu fais ici est un melange des deux. Cela fonctionne car tu verifies que ton tableau d'erreurs est vide mais dans l'ideal  on veut de faire des actions si le formulaire n'est pas valide:
```php
$teacherFromDb = Teacher::find($teacherid);

$teacherFromDb->setFirstname($firstname);  
$teacherFromDb->setLastname($lastname);  
$teacherFromDb->setJob($job);  
$teacherFromDb->setStatus($status);
```
> tout ce block est utile que s'il n'y a pas d'erreurs et pas conséquent que mon form est valide.

<hr>

### Verfication du champ Status:

```php
if(empty($status)) {  
  $errorList[] = "Le status est vide ou invalide !";  
}
```
> Dans l'idée ton message d'erreur est bon, mais tu ne vérifies que si le champs est vide, pense à vérifier s'il est valide, tu as que deux choix que tu acceptes car je suis capable d'ajouter le champs dans le DOM via le navigateur en inspectant et le rajoutant a la main.

> il faut que ton status soit plus grand que 1 ET plus petit ou egale que 2.

<hr >

## Partie Student:

> Les commentaires fait sur la partie teacher d'applique ici :)


