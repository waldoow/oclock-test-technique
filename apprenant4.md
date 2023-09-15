# Feedback Apprenant 1

Hello !

J'ai l'impression que tu as été tu as été bloqué au tout début, dans le message d'erreur que tu as ` require_once(path) ... Failed to open stream: No such file or directory `
comme message.

si on regarde le message, on voit plusieurs points clés

- require_once(path) 
- No such file or directory

de manière generale, tu vas d'abord regarder donc si le fichier existe, et si c'est le cas, verifies bien que tu n'as pas fait
de faute de typo, ça arrive souvent et a tout le monde (moi le premier D:) :)

>  C'est ce qu'il se passe ici, ton dossier `layout` avec les fichiers `header.tpl.php`, `header.tpl.php` qui sont require dans le
> `CoreController.php` n'existent pas. 

Avec de ce petit point débloqué, tu devrais essayer de faire le reste si jamais tu as le temps, tu as la correction pour t'aider  :)
