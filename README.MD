# NUEVO

COMANDOS UTILIZADOS

git init
git status
git add .
git commit -m "nuevo comit"
git push
// diferencias
git push origin main
git pull
git clone

-- crear una rama 

git branch
git switch -c develop
git add .
git commit -m "nueva rama"
git push origin develop

-- combinar la rama secundaria con la rama principal(main)

git switch main
git merge develop

-- Actualizar la rama secundaria con las modificaciones de la rama principal
(Esto tambien es posible realizar desde github.com con un pull request y un merge pull request)
(Opcion 3 activar opcion desde las configuraciones de github.com y activar "always suggest updating pull request branches" dar mas detalles)

git pull origin main
git switch develop
git merge main