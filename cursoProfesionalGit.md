git init = Añadir repositorio

git status = Estado de Git

git add . = Git comienza a seguir los cambios de todos los archivos que están dentro de la carpeta. Para seguir un sólo archivo git add nombrearchivo.html

git commit -m "Mensaje corto descriptivo"

git commit -am "Mensaje descriptivo" (-am hace add y commit en un solo comando)

------------------------------
git log

git log --oneline (Muestra resumido)

git log -p (Muestra los cambios con detalle)

:q (Salir de git log -p)

git log --help (Manual de log - sino pagina devhints.io/git-log )

git log --graph

-----------------------
git config --local user.name (para un proyecto)

git config --global user.name (para todo lo que hagamos en el pc)

git config user.name (muestra la configuración)

Para configurar email reemplazar name por email. 
--------------------------

¿Cuándo hacer un commit? Como regla general, nunca hacer commit a un código que no funciona. Pero cualquier modificación significativa, por pequeña que sea, una vez que está funcionando, se debe commitear. 

---------------------------------
crear un repositorio remoto:

Fuera de la carpeta del proyecto - crear un servidor directorio - y luego hacerlo servidor.

mkdir nombreCarpeta

cd nombreCarpeta

git init -bare

Volver a la carpeta del proyecto copiando la ruta a la carpeta del servidor remoto y:

git remote add nombreservidorinventado pegamoslarutacopiada

Ejemplo: git remote add origin git@github.com:UboldiTIC/ConvertirMonedas.git //lo último es la dirección html o ssh copiada de GitHub.

git remote (vemos todos los servidores remotos a los que tenemos acceso)


SOLUCIÓN CONFLICTOS:
-> fatal: rehusando fusionar historias no relacionadas
git pull origin main --allow-unrelated-histories
---------------------------------

git clone pegamosLaDirecciónQueVamosAClonar

git push nombreservidorinventado rama (enviar la información al servidor)

git push nombreservidorinventado rama (traer la información del servidor)

-----------------------------
git branch (muestra las ramas e indica en cúal estamos actualmente)

git branch nombreDeLaNuevaBranch (Crea una nueva branch)

git checkout nombreDeLaNuevaBranch (Cambiar de rama)

git checkout -b nombreDeLaNuevaBranch (Crea una nueva rama y nos posiciona en ella)
----------------------
git merge nombredelarama (este comando lo hacemos desde main o desde la rama a la cual queremos unir los cambios haciendo una fusión)

git rebase nombredelarama (aplica los commits de otra branch a la branch actual)
-----------------
git restore nombredelarchivo (para desahacer cambios = ctrl z en git)

git restore --staged nombredelarchivo (ctrl z si ya hicimos add y aún no hicimos commit)

git revert hashdelcommitqueborramos (elimina un comit creando un nuevo commit con la situación anterior del archivo)

-----------------------
git stash (guardar temporalmente sin hacer commit)
git stash list
git stash apply Nº (aplica lo guardaddo en stash a nuestro proyecto pero continua en stash)
git stash pop (agrega lo que está en stash y al mismo tiempo lo elimina de stash)
---------------------------
VIAJAR EN EL TIEMPO:
git log --oneline (para ver hash de commits anteriores)

git checkout nºhashanterior (no lleva a un estado del pasado pero en el que no podemos trabajar. Para trabajar deberíamos crear una nueva rama y luego trabajar en ella. Y si la queremos llevar a main hacer merge)

git chechout -b nuevonombre (para crear la nueva rama con archivo del pasado)

git diff hash..hash

-----------------------------
Versiones:

git tag -a v0.1.0 -m "mensaje" (crear una versión)

git tag (muestra las versiones)

git push origin v0.1.0 (envia la versión al remoto)

