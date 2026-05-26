# 📘 Guía Completa de Git y GitHub

> Documentación orientada a los comandos, flujos de trabajo y herramientas más utilizadas en proyectos personales y colaborativos.

---

# 📑 Índice

1. 🚀 Introducción a Git y GitHub
2. ⚙️ Configuración inicial de Git
3. 🔐 Conectar GitHub con Git local (SSH)
4. 📂 Crear un proyecto y subirlo a GitHub
5. 📥 Clonar un repositorio y trabajar en él
6. 🌿 Crear y trabajar con ramas
7. 🔀 Combinar ramas con `merge`
8. ⚠️ Merge conflicts y soluciones
9. 🏷️ Convención de nombres para ramas
10. 📝 GitHub Issues
11. 📋 GitHub Projects
12. 👀 Code Review y Pull Requests
13. 🌍 GitHub Pages
14. 🌐 Custom Domain
15. 🚫 .gitignore
16. 🧠 Comandos útiles y recomendaciones
17. ✅ Buenas prácticas
18. 🎯 Flujo recomendado
19. 🚀 Fin de la documentación

---

# 🚀 1. Introducción a Git y GitHub

## 📌 ¿Qué es Git?

Git es un sistema de control de versiones que permite:

- guardar cambios
- volver a versiones anteriores
- trabajar con ramas
- colaborar con otros desarrolladores

---

## 🌐 ¿Qué es GitHub?

GitHub es una plataforma basada en Git que permite:

- almacenar repositorios online
- colaborar en equipo
- realizar code reviews
- usar issues y proyectos
- desplegar aplicaciones

---

# ⚙️ 2. Configuración inicial de Git

## 👤 Configurar nombre de usuario

```bash
git config --global user.name "Tu Nombre"
```

---

## 📧 Configurar correo electrónico

```bash
git config --global user.email "correo@gmail.com"
```

---

## 🔍 Ver configuración actual

```bash
git config --list
```

---

# 🔐 3. Conectar GitHub con Git local (SSH)

> Método recomendado actualmente para conectar GitHub con Git local sin usar contraseña.

---

## 🔑 Generar clave SSH

```bash
ssh-keygen -t ed25519 -C "correo@gmail.com"
```

---

## 📂 Ver clave pública

### Windows (PowerShell)

```bash
cat ~/.ssh/id_ed25519.pub
```

---

## 🌐 Agregar clave SSH a GitHub

Ruta:

```text
GitHub → Settings → SSH and GPG Keys
```

---

## ➕ Agregar nueva clave

1. Presionar:
   ```text
   New SSH Key
   ```

2. Copiar la clave generada

3. Pegarla en GitHub

---

## 🧪 Verificar conexión

```bash
ssh -T git@github.com
```

---

## ✅ Resultado esperado

```text
Hi usuario! You've successfully authenticated...
```

---

# 📂 4. Crear un proyecto y subirlo a GitHub

## 📁 Crear carpeta del proyecto

```bash
mkdir mi_proyecto
```

---

## 📂 Entrar a la carpeta

```bash
cd mi_proyecto
```

---

## 📂 Inicializar Git

```bash
git init
```

🔹 Crea un repositorio Git local.

---

## 🔍 Ver estado del proyecto

```bash
git status
```

---

## ➕ Agregar archivos

```bash
git add .
```

---

## 💾 Crear commit

```bash
git commit -m "primer commit"
```

---

## 🌐 Conectar repositorio remoto

```bash
git remote add origin git@github.com:usuario/repositorio.git
```

---

## 🔍 Ver repositorios conectados

```bash
git remote -v
```

---

## ☁️ Subir proyecto a GitHub

```bash
git push -u origin main
```

---

## 📌 Diferencia entre comandos

### Forma corta

```bash
git push
```

🔹 Funciona cuando la rama ya está conectada al remoto.

---

### Forma explícita

```bash
git push origin main
```

🔹 `origin` → repositorio remoto  
🔹 `main` → rama principal

---

## 📥 Descargar cambios

```bash
git pull
```

---

# 📥 5. Clonar un repositorio y trabajar en él

## 📦 Clonar repositorio

```bash
git clone URL_DEL_REPOSITORIO
```

---

## ✅ Ejemplo

```bash
git clone https://github.com/usuario/proyecto.git
```

---

## 📂 Entrar al proyecto

```bash
cd proyecto
```

---

## ✏️ Modificar archivos

```bash
git status
```

---

## ➕ Agregar cambios

```bash
git add .
```

---

## 💾 Crear commit

```bash
git commit -m "actualizacion del proyecto"
```

---

## ☁️ Subir cambios

```bash
git push
```

---

# 🌿 6. Crear y trabajar con ramas

## 📄 Ver ramas existentes

```bash
git branch
```

---

## 🌱 Crear rama y cambiar automáticamente

```bash
git switch -c develop
```

---

## ✏️ Trabajar en la nueva rama

```bash
git add .
git commit -m "nueva funcionalidad"
```

---

## ☁️ Subir rama a GitHub

```bash
git push origin develop
```

---

## 🔄 Cambiar entre ramas

```bash
git switch main
```

o

```bash
git switch develop
```

---

# 🔀 7. Combinar ramas con merge

## 🔄 Cambiar a la rama principal

```bash
git switch main
```

---

## 🔗 Combinar rama secundaria

```bash
git merge develop
```

---

## ☁️ Subir cambios

```bash
git push origin main
```

---

# ⚠️ 8. Merge conflicts y soluciones

# 📌 Escenario

## Rama `main`

```text
commit A
commit B
commit C
```

---

## Rama `develop`

```text
commit X
commit Y
```

---

## ❌ Problema

La rama `develop` está desactualizada respecto a `main`.

---

## ⚠️ Error típico

```bash
CONFLICT (content): Merge conflict in archivo.txt
Automatic merge failed
```

---

## 🔍 ¿Por qué ocurre?

Git detecta modificaciones en las mismas líneas.

Ejemplo:

```text
main
 ├── modifica linea 10

develop
 ├── modifica linea 10
```

Git no sabe cuál conservar.

---

# ✅ Solución correcta

## 1️⃣ Descargar cambios principales

```bash
git pull origin main
```

---

## 2️⃣ Cambiar a develop

```bash
git switch develop
```
🔹 Crea la rama `develop` y cambia automáticamente a ella.

---

## 3️⃣ Combinar cambios

```bash
git merge main
```

---

# 🛠️ Resolver conflictos manualmente

Git mostrará:

```txt
<<<<<<< HEAD
Codigo develop
=======
Codigo main
>>>>>>> main
```

---

## ✅ Después de resolver

```bash
git add .
git commit -m "conflicto resuelto"
```

---

## ☁️ Subir cambios

```bash
git push origin develop
```

---

# 🌐 Alternativa usando Pull Request

GitHub puede mostrar:

```text
Update branch
```

Esto actualiza automáticamente la rama secundaria.

---

# ⚙️ Configuración recomendada

## ✅ Activar:

```text
Always suggest updating pull request branches
```

Ruta:

```text
Repositorio → Settings → Pull Requests
```

---

# 🏷️ 9. Convención de nombres para ramas

## 📌 Formato recomendado

```text
tipo/nombre-del-cambio
```

---

## 📂 Tipos comunes

| Tipo | Uso |
|---|---|
| `feature/` | Nueva funcionalidad |
| `fix/` | Corrección de errores |
| `hotfix/` | Corrección urgente |
| `release/` | Preparar versión |
| `docs/` | Documentación |
| `refactor/` | Reestructuración |

---

## ✅ Ejemplos reales

```bash
feature/login-system
feature/dashboard-admin

fix/navbar-mobile
fix/error-login

hotfix/payment-error

release/v1.0.0

docs/update-readme

refactor/user-module
```

---

## 📌 Ejemplos en español

```bash
feature/sistema-login
fix/error-navbar
hotfix/error-pagos
docs/documentacion-git
```

---

# 📝 10. GitHub Issues

## 📌 ¿Qué son?

Sistema para:

- reportar errores
- crear tareas
- proponer mejoras
- organizar trabajo

---

## ✅ Ejemplo de Issue

```text
Título:
Error al iniciar sesión

Descripción:
La aplicación muestra pantalla blanca al ingresar credenciales incorrectas.
```

---

## 🔗 Relación con ramas

Ejemplo:

```bash
feature/15-login-page
```

Donde:

```text
15 → número del Issue
```

---

# 📋 11. GitHub Projects

## 📌 ¿Qué es?

Sistema de organización estilo Kanban.

---

## 📂 Columnas comunes

```text
Backlog
Todo
In Progress
Testing
Done
```

---

## 🧠 ¿Para qué sirve?

- organizar tareas
- trabajo en equipo
- seguimiento del proyecto
- metodologías ágiles

---

## 🔗 Relación con Issues

Los Issues pueden moverse automáticamente entre columnas.

---

# 👀 12. Code Review y Pull Requests

## 📌 ¿Qué es un Pull Request?

Solicitud para fusionar cambios entre ramas.

---

## 🔄 Flujo profesional

```text
1. Crear rama
2. Realizar cambios
3. Hacer commit
4. Hacer push
5. Crear Pull Request
6. Code Review
7. Merge
```

---

## 👀 ¿Qué se revisa?

- errores
- rendimiento
- seguridad
- buenas prácticas
- legibilidad

---

## ✅ Aprobar cambios

Opciones comunes:

```text
Approve
Request changes
Comment
```

---

# 🌍 13. GitHub Pages

> Permite publicar sitios web estáticos directamente desde GitHub.

---

# 📄 Proyecto HTML, CSS y JS

## ✅ Activar GitHub Pages

Ruta:

```text
Repositorio → Settings → Pages
```

---

## 🌿 Seleccionar rama

```text
main
/root
```

---

## 🌐 Resultado

```text
https://usuario.github.io/repositorio/
```

---

# ⚛️ Proyecto Vue 3

## 📦 Compilar proyecto

```bash
npm run build
```

Esto genera:

```text
dist/
```

---

## 📦 Instalar gh-pages

```bash
npm install gh-pages --save-dev
```

---

## ⚙️ package.json

```json
"scripts": {
  "deploy": "gh-pages -d dist"
}
```

---

## 🚀 Deploy

```bash
npm run deploy
```

---

# ⚛️ Proyecto React

## 📦 Compilar proyecto

```bash
npm run build
```

Genera:

```text
build/
```

---

## 📦 Instalar gh-pages

```bash
npm install gh-pages --save-dev
```

---

## ⚙️ package.json

```json
"homepage": "https://usuario.github.io/repositorio"
```

---

## 🚀 Deploy

```bash
npm run deploy
```

---

# 🐍 Proyecto Django con Python

## ⚠️ Importante

GitHub Pages NO soporta Django completo.

---

## ❌ ¿Por qué?

Porque Django necesita:

- Python ejecutándose
- backend activo
- servidor

---

## ✅ GitHub Pages solo soporta

- HTML
- CSS
- JS
- imágenes

---

## 🌐 Plataformas compatibles con Django

| Plataforma | Compatible |
|---|---|
| Render | ✅ |
| Railway | ✅ |
| VPS | ✅ |
| PythonAnywhere | ✅ |

---

# 🌐 14. Custom Domain

## 📌 ¿Qué es?

Permite usar:

```text
midominio.com
```

En lugar de:

```text
usuario.github.io
```

---

## ⚙️ Configuración DNS

| Tipo | Valor |
|---|---|
| A | IP GitHub |
| CNAME | usuario.github.io |

---

## 📄 Archivo CNAME

```text
midominio.com
```

---

# 🚫 15. .gitignore

## 📌 ¿Qué es?

Archivo utilizado para ignorar archivos innecesarios o sensibles.

---

## ❌ Archivos comunes ignorados

```text
venv/
node_modules/
.env
dist/
build/
__pycache__/
```

---

## 📄 Crear archivo

```bash
touch .gitignore
```

---

# 🐍 Ejemplo Python/Django

```gitignore
venv/
__pycache__/
*.pyc
.env
db.sqlite3
```

---

# ⚛️ Ejemplo Node/Vue/React

```gitignore
node_modules/
dist/
.env
```

---

# 🧠 16. Comandos útiles y recomendaciones

| Comando | Descripción |
|---|---|
| `git init` | Inicializar repositorio |
| `git status` | Ver estado |
| `git add .` | Agregar archivos |
| `git commit -m ""` | Crear commit |
| `git push` | Subir cambios |
| `git pull` | Descargar cambios |
| `git clone URL` | Clonar proyecto |
| `git branch` | Ver ramas |
| `git switch rama` | Cambiar rama |
| `git switch -c rama` | Crear rama |
| `git merge rama` | Combinar ramas |
| `git remote -v` | Ver remotos |

---

# ✅ 17. Buenas prácticas

## 📌 Usar mensajes claros

✅ Correcto:

```bash
git commit -m "agrega sistema de login"
```

❌ Incorrecto:

```bash
git commit -m "cambios"
```

---

## 📌 Hacer pull antes de trabajar

Evita conflictos.

---

## 📌 Trabajar con ramas

Nunca desarrollar directamente en `main`.

---

## 📌 Hacer commits pequeños

Facilita debugging y revisión.

---

# 🎯 18. Flujo recomendado

```text
main
 └── develop
      ├── feature/login
      ├── feature/dashboard
      ├── fix/navbar
      └── hotfix/payment-error
```

---

## 📌 Significado

| Rama | Uso |
|---|---|
| `main` | Producción |
| `develop` | Integración |
| `feature/*` | Nuevas funcionalidades |
| `fix/*` | Correcciones |
| `hotfix/*` | Correcciones urgentes |

---

# 🚀 19. Fin de la documentación

> Esta guía cubre el flujo básico y profesional más utilizado en Git y GitHub para proyectos personales y colaborativos.