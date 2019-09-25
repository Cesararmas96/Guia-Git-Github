#Guia Basica de Git y Github

##Tags (Etiquetas)

###Creacion de Tags.

Creación de tag para la versiones.

```
$ git tag numeroversion -m 'mensaje'
```

##Tags (Etiquetas)

###Creacion de Tags.

Creacion de tag para la versiones

```$ git tag numeroversion -m 'mensaje'

```

Creacion del tag y asignarlo a un commit

```
$ git tag numeroversion NumeroCommit
```

###Borrar tag

```
$ git NumeroTag -d
```

###Renombrar un tag.

1.  Crear un nuevo tag.

````
$ git tag -f -a numeroversionNew -m 'mensaje'```

2. Luego borrar el tag seleccionado.
````

\$ git tag -d NumeroVersionBorrar

```

##LLaves SSH

###Creación de la llave SSH.

> ssh-generacion de la llave - algoritmo especial que se quiere generar - algoritmo rsa - complejida - tipo de algoritmo matematico - correo electronico - correo@mail.com.

1. ssh-keygen -t rsa -b 4096 -C 'tucorreo@correo.com'

2. Verificación si esta corriendo dentro del computador.
```

$ eval $(ssh-agent -s)

```

3. Agregar la llave al sistema.
```

\$ ssh-add ~/.ssh/id_rsa

```

###Cambiar direccion del repositorio remoto.
> Si posee una dirreccion HTTPS  y no una SSH es necesario es necesario realizar este paso.

```

\$ git remote set-url origin git@github.com:nombre/nombre-repositorio.git

````

##Repositorio local a Github

Pasos para agregar un repositorio creado a **Github**:

1. Crear un nuevo repositorio en [Github](https://github.com) en donde se va a guardar el repositorio creado.

2. Copiar la URL o llave SSH del repositorio creado.

3. Guardar la URL o llave SSH del repositorio de [Github](https://github.com).

4. Agregar la URL o llave SSH al repositorio local.
```
git remote add origin https://github.com/usuario/repositorio.git
```
```
git remote add origin git@github.com:usuario/repositorio.git
```

5. Verificar si la URL O llave SSH se ha guardado correctamente.
```git remote
```
```git remote -v
```

##Guardar cambios del repositorio local a [Github](https://github.com)


1. Traer la version del repositorio del repositorio remoto para poder sincronizar los commits entre las 2 versiones .
```$ git pull origin master --allow-unrelated-histories
```
2. Guardar los cambios en el repositorio local en **Github**
```$ git push origin master
```



## Branch (rama)

Creacion de branch.

``` $ git branch nombre
```

Creacion de una branch y moverse a ella.

```$ git branch -m nombre
```

```$ git checkout -b nuevarama
```

Renombrar branch.

```$ git branch -m vieja nueva
```

Eliminar branch.

```
$ git branch -d nombre
```

##Fuccion de branch.

> Merge permite combinar 2 ramas , la rama donde nos encontramos y la rama que indiquemos en el comando.

1. Posicionarse en la rama que se va a manejar.
```
$ git checkout master
```

2. Obtener los datos de otra rama que quiere fuccionar.
```
$ git merge otrarama
```

##Reset

* Quita el commit pero este se mantiene el states y no se borra en el working directory.
```
$ git reset --soft CommitDondeQuiereQuedarse
```

* Quita el commit del state y no se borra en el working directory.
```
$ git reset --mixed CommitDondeQuiereQuedarse
```

* Quita el archivo completo en el working directory.
```
$ git reset --hard CommitEliminar
```

##Diferenciacion de Commit

* Ver diferenciacion del commit con el ultimo.

```
$ git diff commit
```

* Diferenciacion entre commit.
```
$ git diff CommitActual CommitOtro
```


##Graficar los branchs y los commits.



* Ver todos los commit.
```
$ git log
```

* Ver los commit de manera resumida.
```
$ git log --oneline
```
* Ver cantidades de commit
```
$ git log -cantCommit
```

* Ver las graficaciones de las ramas-
```
$ git log --oneline --graph
```

* Graficacion de de ramas y commits
```
$ git log --graph --decorate --pretty=oneline --abbrev-commit --all
```








Tercero Traer la version del repositorio remoto y hacer merge para crear un commit con los archivos de ambas partes. Podemos usar git fetch y git mer o solo el git pull con el flag --allow-unrelated-history







fetch: recibir
push: enviar

---

git fetch : hacer la copia a mi directorio de trabajo desde el repositorio remoto

pero se usa el pull

git push: Luego de hacer git add y git commit debemos ejecutar este comando para mandar los cambios al servidor remoto.

git fetch: Lo usamos para traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local (en caso de que hayan, por supuesto).

git merge: También usamos el comando git fetch con servidores remotos. Lo necesitamos para combinar los últimos cambios del servidor remoto y nuestro directorio de trabajo.

git pull: Básicamente, git fetch y git merge al mismo tiempo.

---

git commit -am 'Archivo modificados' : commit para los archivos modificados.






git commit --amend: Permite si ya realizaste el commmit de los archivos y se te paso uno permite agregarlo sin crear un nuevo commit





git stash: Permite guardar sin hacer ningun commit, a la hora de cambiar de ramas es util ya que no mueve los cambios hacia otra rama, este tiene que estar en el state

git stash apply: Realiza el primer cambio
git stash apply stash{nuevo}: Realiza el primer cambio

git stash list: muestra la lista de los stash

git stash drop stash@{0}:Elimina el stash

---

git cherry-pick numeroCommit: permite selecionar el commit y moverlo a la rama donde estas

---
````
