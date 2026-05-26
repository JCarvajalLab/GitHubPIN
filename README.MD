# 📘 Guía Básica de Git y GitHub

> Documentación orientada a los comandos y flujos más utilizados en proyectos personales y colaborativos.

---

# 📑 Índice

1. 🚀 Crear un proyecto y subirlo a GitHub
2. 📥 Clonar un repositorio y trabajar en él
3. 🌿 Crear y trabajar con ramas
4. 🔀 Combinar ramas con `merge`
5. ⚠️ Sincronizar ramas y resolver conflictos
6. 🧠 Comandos útiles y recomendaciones

---

# 🚀 1. Crear un proyecto y subirlo a GitHub

## 📂 Inicializar Git en un proyecto

```bash
git init
```

🔹 Crea un repositorio Git en la carpeta actual.

---

## 🔍 Ver el estado del proyecto

```bash
git status
```

🔹 Muestra archivos modificados, nuevos o pendientes de commit.

---

## ➕ Agregar archivos al commit

```bash
git add .
```

🔹 Agrega todos los archivos modificados al área de preparación (*staging area*).

---

## 💾 Crear un commit

```bash
git commit -m "primer commit"
```

🔹 Guarda una versión del proyecto con un mensaje descriptivo.

---

## ☁️ Subir el proyecto a GitHub

```bash
git push
```

🔹 Envía los cambios al repositorio remoto.

---

## 📌 Diferencia importante

### Forma corta

```bash
git push
```

🔹 Funciona cuando la rama remota ya está configurada.

---

### Forma explícita

```bash
git push origin main
```

🔹 `origin` → nombre del repositorio remoto  
🔹 `main` → rama principal

Esta forma es más clara y recomendable para aprender.

---

## 📥 Descargar cambios del repositorio

```bash
git pull
```

🔹 Descarga y combina cambios del repositorio remoto.

---

---

# 📥 2. Clonar un repositorio y trabajar en él

## 📦 Clonar un proyecto existente

```bash
git clone URL_DEL_REPOSITORIO
```

Ejemplo:

```bash
git clone https://github.com/usuario/proyecto.git
```

🔹 Descarga el proyecto completo desde GitHub.

---

## 📂 Entrar a la carpeta del proyecto

```bash
cd proyecto
```

---

## ✏️ Modificar archivos

Después de editar archivos:

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

🔹 Como el repositorio ya está conectado a GitHub y es propio, normalmente no pedirá permisos nuevamente.

---

# 🌿 3. Crear y trabajar con ramas

## 📄 Ver ramas existentes

```bash
git branch
```

---

## 🌱 Crear y cambiar a una nueva rama

```bash
git switch -c develop
```

🔹 Crea la rama `develop` y cambia automáticamente a ella.

---

## ✏️ Trabajar en la nueva rama

```bash
git add .
git commit -m "nueva funcionalidad"
```

---

## ☁️ Subir la rama a GitHub

```bash
git push origin develop
```

🔹 Publica la nueva rama en GitHub.

---

# 🔀 4. Combinar una rama secundaria con la principal

## 🔄 Cambiar a la rama principal

```bash
git switch main
```

---

## 🔗 Combinar ramas

```bash
git merge develop
```

🔹 Une todos los cambios de `develop` dentro de `main`.

---

## ☁️ Subir los cambios finales

```bash
git push origin main
```

---

# ⚠️ 5. Sincronizar ramas y resolver conflictos

## 📌 Escenario

Imaginemos esta situación:

### Rama `main`

Tiene 3 commits nuevos:

```text
commit A
commit B
commit C
```

---

### Rama `develop`

Tiene 2 commits diferentes:

```text
commit X
commit Y
```

---

## ❌ Problema

La rama `develop` está desactualizada respecto a `main`.

Si intentamos hacer merge directamente, pueden aparecer conflictos.

---

# ✅ Solución correcta

## 1️⃣ Descargar cambios de la rama principal

```bash
git pull origin main
```

🔹 Descarga la última versión de `main`.

---

## 2️⃣ Cambiar a la rama secundaria

```bash
git switch develop
```

---

## 3️⃣ Combinar cambios de `main` en `develop`

```bash
git merge main
```

🔹 Ahora `develop` obtiene los cambios nuevos de `main`.

---

# ⚠️ Posibles conflictos

Git puede mostrar conflictos como:

```text
CONFLICT (content): Merge conflict in archivo.txt
```

---

## 🛠️ Resolver conflictos

Git marcará las diferencias así:

```txt
<<<<<<< HEAD
Codigo de develop
=======
Codigo de main
>>>>>>> main
```

Debes:

- Elegir qué código conservar
- O combinar ambos manualmente

---

## ✅ Después de resolver conflictos

```bash
git add .
git commit -m "conflicto resuelto"
```

---

## ☁️ Subir cambios actualizados

```bash
git push origin develop
```

---

# 🌐 Alternativa usando GitHub Pull Request

También es posible sincronizar ramas desde GitHub.com mediante un:

## 🔃 Pull Request

GitHub puede mostrar un botón como:

```text
Update branch
```

Esto actualiza automáticamente la rama secundaria.

---

# ⚙️ Configuración recomendada en GitHub

## ✅ Activar:

### "Always suggest updating pull request branches"

📍 Ruta aproximada:

```text
Repositorio → Settings → Pull Requests
```

🔹 GitHub sugerirá automáticamente actualizar ramas desactualizadas antes de hacer merge.

---

# 🧠 6. Comandos útiles y recomendaciones

| Comando | Descripción |
|---|---|
| `git status` | Ver estado del proyecto |
| `git add .` | Agregar todos los archivos |
| `git commit -m ""` | Crear commit |
| `git pull` | Descargar cambios |
| `git push` | Subir cambios |
| `git branch` | Ver ramas |
| `git switch rama` | Cambiar de rama |
| `git switch -c rama` | Crear rama |
| `git merge rama` | Combinar ramas |
| `git clone URL` | Clonar repositorio |

---

# ✅ Buenas prácticas

## 📌 Usa mensajes de commit claros

✅ Correcto:

```bash
git commit -m "agrega sistema de login"
```

❌ Incorrecto:

```bash
git commit -m "cambios"
```

---

## 📌 Haz `pull` antes de trabajar

Evita conflictos innecesarios.

---

## 📌 Trabaja con ramas

Nunca desarrolles funcionalidades grandes directamente en `main`.

---

# 🎯 Resumen del flujo recomendado

```text
main
 └── develop
      ├── nueva-funcion
      ├── fix-login
      └── mejora-ui
```

🔹 `main` → versión estable  
🔹 `develop` → integración  
🔹 ramas secundarias → nuevas funcionalidades

---

# 🚀 Fin de la documentación

> Esta guía cubre el flujo básico y más utilizado en Git y GitHub para proyectos personales y colaborativos.


# MODIFICABLE

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