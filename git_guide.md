## Create a new repository on github

1.- Login to your github account and add a new repository
2.- Generate the local repository from the command line
```
git init <name project>
```
 3.- Add all the files to the **Staging Area**
 ```
git add .
```
4.- Perform the commit, which takes the files to the repository for change control
```
git commit -m "a comment related to what is going up"
```
5.- Then you have to do the **push** from your local repository to remote with the commands that appear on the Github page that is right after you have created the repository.
```
git remote add origin git@github.com:"user name"/"name repository".git
git push -u origin master
```

## Delete last commit con reset and revert

1.- Solution if we have NOT uploaded the commit to our remote repository (we have not done push):
```
git reset --hard HEAD~1
```
* Spanish:
> --head: Con esta opción estamos indicando que retrocedemos a el comit HEAD~1 y perdemos todas las confirmaciones posteriores. HEAD~1 es un atajo para apuntar al commit anterior al que nos encontramos. CUIDADO, con la opcion –head, ya que como he dicho se borran todos los commits posteriores al commit al que indicamos.

* English:
> --head: With this option we are indicating that we go back to the HEAD ~ 1 committee and lose all subsequent confirmations. HEAD ~ 1 is a shortcut to point to the previous commit to which we are. BEWARE, with the option -head, since as I said, all the commits after the commit that we indicated are deleted.

2.- Use the flag soft:
```
git reset --soft HEAD~1
```

* Spanish:
> --soft: con esta opción estamos indicando que retrocedemos a el commit HEAD~1 y no perdemos los cambios de los commits posteriores. Todos los cambios aparecerán como pendientes para realizar un commit.

* English:
--soft: with this option we are indicating that we go back to the commit HEAD ~ 1 and we do not lose the changes of the subsequent commits. All changes will appear as pending to commit.

3.- Solution if we have uploaded the commit to our remote repository (we have done push):

* Spanish
>En caso de que queramos borrar un commit que ya hemos subido al servidor remoto, la mejor opcion es realizar un nuevo commit que borre el commit que queremos eliminar utilizando el comando revert. De esta forma cualquier usuario que se tenga actualizado el contenido del repositorio remoto puede obtener el cambio simplemente haciendo pull.

* English

> In case we want to delete a commit that we have already uploaded to the remote server, the best option is to make a new commit that deletes the commit that we want to eliminate using the revert command. In this way any user who has updated the contents of the remote repository can obtain the change simply by doing pull. Therefore, to erase the last commit taking into account that the commit is uploaded in a remote repository, we must use:
```
git revert HEAD
```
