# Curso-Git2019

ls -al: Listar todos los archivos y los ocultos
git show nombreArchivos: ver los cambios que han tenido

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

---

Fusión de ramas con Git merge
El comando git merge nos permite crear un nuevo commit con la combinación de dos ramas (la rama donde nos encontramos cuando ejecutamos el comando y la rama que indiquemos después del comando).

# Crear un nuevo commit en la rama master combinando

# los cambios de la rama cabecera:

git checkout master
git merge cabecera

# Crear un nuevo commit en la rama cabecera combinando

# los cambios de cualquier otra rama:

git checkout cabecera
git merge cualquier-otra-rama
Asombroso, ¿verdad? Es como si Git tuviera super poderes para saber qué cambios queremos conservar de una rama y qué otros de la otra. El problema es que no siempre puede adivinar, sobretodo en algunos casos donde dos ramas tienen actualizaciones diferentes en ciertas líneas en los archivos. Esto lo conocemos como un conflicto y aprenderemos a solucionarlos en la siguiente clase.

Recuerda que al ejecutar el comando git checkout para cambiar de rama o commit puedes perder el trabajo que no hayas guardado. Guarda tus cambios antes de hacer git checkout.

---

#Agregar repositorio a Github

Guardar la url del repositorio de github con el nombre origin

1. git remote add origin https://github.com/caal2096/Fundamentos-Js-Platzi.git

2. Verifica que la url se haya guardado
   git remote -v
   git remote

3. Tercero Traer la version del repositorio remoto y hacer merge para crear un commit con los archivos de ambas partes. Podemos usar git fetch y git mer o solo el git pull con el flag --allow-unrelated-history

git pull origin master --allow-unrelated-histories

4. Por ultimo, ahora si podemos hacer git push para guardar los cambios de nuestro repositorio local en github

git push origin master

Grafico:

git log --graph --decorate --pretty=oneline --abbrev-commit --all

---

git commit --amend: Permite si ya realizaste el commmit de los archivos y se te paso uno permite agregarlo sin crear un nuevo commit

git tag (numeroversion) -m '(mensaje)': Creacion de tag para la versiones

git tag (numeroversion) (NumeroCommit)

Para borrar tag: git tag -d

Para renombrar tag: git tag -f -a (numeroversionNew) -m '(mensaje)', luego realizar git tag -d (numeroversionborrar)

---

git log : ver toda los commit
git log --oneline : bb3c926 ( master, tag: 0.5) Agregado Index
git log --oneline --graph : graficaciones de ramas

git log -(cantCommit) : Ver cantidad de commit

---

Diferenciacion entre commit

git diff (commitDeComparacionConElActual)
git diff (commitDeComparacionConElActual) (compraracionotro)

---

#git Reset

git reset --soft --mixed --hard

Reescribir

git reset --soft (commitdondequiere que se quede igual) : Quitar el commit pero mantener los archivos en el state

git reset --mixed (quita del estato en el commit y states )

git reset --hard (numerocommit): quita el archivo completo del working directory

---

git branch nombrenuevo
git branch -m nombrenuevo : nueva y moverse
git branch -m nombreviejo nombrenuevo: cambiar nombre

git branch (-d / -D ) nombrebranch : eliminar branch

---

git checkout -b nuevarama: creacion de nueva rama

---

git stash: Permite guardar sin hacer ningun commit, a la hora de cambiar de ramas es util ya que no mueve los cambios hacia otra rama, este tiene que estar en el state

git stash apply: Realiza el primer cambio
git stash apply stash{nuevo}: Realiza el primer cambio

git stash list: muestra la lista de los stash

git stash drop stash@{0}:Elimina el stash

---

git cherry-pick numeroCommit: permite selecionar el commit y moverlo a la rama donde estas

---

#Llaves SSH

(llave ssh - generacion de la llave - -t algoritmo especial que se quiere generar - algoritmo rsa - complejida -b - tipo de algoritmo matematico - -C correo electronico - correo@mail.com)

1. Creacion la llave:
   ssh-keygen -t rsa -b 4096 -C "caal2096@gmail.com"

2. Verificacion si esta corriendo dentro del equivo
   eval \$(ssh-agent -s)

3)Agregar la llave al sistema
ssh-add ~/.ssh/id_rsa

# Realizar commit a travez de ssh

Cambiar la direccion remota
git remote set-url origin git@github.com:caal2096/Curso-Git2019.git
