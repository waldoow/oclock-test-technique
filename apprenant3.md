# Feedback Apprenant 3

 Hello !
 Après avoir testé ton code, j'ai l'impression que tu as été vite bloqué sur une erreur de connexion de base donnée.

```sql
SQLSTATE[HY000] [2002] No such file or directory
```

> je sais que cette erreur n'est pas explicite, mais en gros cela veut juste dire que tu as un soucis dans tes informations
> de connexion :)

```env
; base de données
DB_HOST = '127.0.0.1'
DB_NAME = 'skoule'
DB_USERNAME = 'root'
DB_PASSWORD = 'root'
```
> Si tu rencontres ce genre de soucis, le premier reflex, c'est de changer entre `localhost` et `127.0.0.1`

Si jamais tu trouves le temps de faire la suite, ça serait une bonne idée de le faire, tu pourras voir les notions et
tu avais l'air bien parti :)
