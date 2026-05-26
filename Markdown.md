# 📝 Guía Completa de Markdown — GitHub Flavored Markdown (GFM)

> Markdown es un lenguaje de marcado ligero que permite dar formato a texto plano de forma sencilla.
> GitHub usa su propia versión extendida llamada **GFM (GitHub Flavored Markdown)**.

---

## 📚 Tabla de Contenidos

- [Encabezados](#-encabezados)
- [Estilos de Texto](#-estilos-de-texto)
- [Listas](#-listas)
- [Links e Imágenes](#-links-e-imágenes)
- [Código](#-código)
- [Tablas](#-tablas)
- [Citas y Alertas](#-citas-y-alertas)
- [Líneas Horizontales](#-líneas-horizontales)
- [Task Lists](#-task-lists)
- [HTML en Markdown](#-html-en-markdown)
- [Menciones y Referencias](#-menciones-y-referencias-github)
- [Emojis](#-emojis)
- [Notas al Pie](#-notas-al-pie)
- [Colapsar Contenido](#-colapsar-contenido)
- [Escapar Caracteres](#-escapar-caracteres)
- [Matemáticas](#-matemáticas)
- [Referencia Rápida](#-referencia-rápida)

---

## 🏷️ Encabezados

# H1 — Encabezado nivel 1
## H2 — Encabezado nivel 2
### H3 — Encabezado nivel 3
#### H4 — Encabezado nivel 4
##### H5 — Encabezado nivel 5
###### H6 — Encabezado nivel 6

Estilo alternativo solo para H1 y H2:

H1 Alternativo
==============

H2 Alternativo
--------------

---

## ✍️ Estilos de Texto

**Negrita con doble asterisco**

__Negrita con doble guion bajo__

*Cursiva con asterisco*

_Cursiva con guion bajo_

***Negrita y cursiva combinadas***

~~Texto tachado~~

<u>Texto subrayado con HTML</u>

Superíndice: X<sup>2</sup> + Y<sup>3</sup>

Subíndice: H<sub>2</sub>O y CO<sub>2</sub>

---

## 📋 Listas

### Desordenada

- Elemento con guion
- Otro elemento
  - Sub-elemento anidado
  - Otro sub-elemento
    - Tercer nivel

* Elemento con asterisco
* Otro elemento

+ Elemento con más
+ Otro elemento

### Ordenada

1. Primer elemento
2. Segundo elemento
   1. Sub-elemento numerado
   2. Otro sub-elemento
3. Tercer elemento

---

## 🔗 Links e Imágenes

[Link básico a GitHub](https://github.com)

[Link con tooltip](https://github.com "Ir a GitHub")

[Link a una sección del documento](#-encabezados)

[Link de referencia a Google][google]

[google]: https://google.com "Motor de búsqueda"

URL automática: https://github.com

![Logo de GitHub](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)

[![Imagen clickeable hacia GitHub](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)](https://github.com)

<img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="60" alt="Logo pequeño">

---

## 💻 Código

Código `inline` dentro de una oración con comillas simples.

``También se puede usar ``doble backtick`` para incluir un `backtick` dentro``

Bloque sin lenguaje:

```
función sin resaltado
print("sin color")
```

```javascript
// JavaScript
const saludo = (nombre) => `Hola, ${nombre}!`;
console.log(saludo("GitHub"));
```

```python
# Python
def saludar(nombre):
    return f"Hola, {nombre}!"

print(saludar("GitHub"))
```

```bash
# Bash / Shell
git clone https://github.com/usuario/repo.git
cd repo
npm install && npm start
```

```typescript
// TypeScript
interface Usuario {
  nombre: string;
  edad: number;
}
const user: Usuario = { nombre: "Ana", edad: 25 };
```

```html
<!-- HTML -->
<!DOCTYPE html>
<html lang="es">
  <head><title>Mi página</title></head>
  <body><h1>Hola mundo</h1></body>
</html>
```

```css
/* CSS */
.container {
  display: flex;
  justify-content: center;
  background-color: #f0f0f0;
}
```

```json
{
  "nombre": "proyecto",
  "version": "1.0.0",
  "dependencias": ["react", "typescript"]
}
```

```yaml
# YAML
nombre: proyecto
version: 1.0.0
configuracion:
  puerto: 3000
  debug: true
```

```sql
-- SQL
SELECT nombre, edad
FROM usuarios
WHERE activo = true
ORDER BY nombre ASC;
```

```java
// Java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("Hola GitHub!");
    }
}
```

```go
// Go
package main
import "fmt"
func main() {
    fmt.Println("Hola GitHub!")
}
```

```rust
// Rust
fn main() {
    println!("Hola GitHub!");
}
```

```php
<?php
// PHP
function saludar($nombre) {
    return "Hola, " . $nombre . "!";
}
echo saludar("GitHub");
?>
```

```swift
// Swift
func saludar(nombre: String) -> String {
    return "Hola, \(nombre)!"
}
print(saludar(nombre: "GitHub"))
```

```kotlin
// Kotlin
fun saludar(nombre: String) = "Hola, $nombre!"
fun main() = println(saludar("GitHub"))
```

```ruby
# Ruby
def saludar(nombre)
  "Hola, #{nombre}!"
end
puts saludar("GitHub")
```

```dockerfile
# Dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

```diff
- línea eliminada en rojo
+ línea añadida en verde
  línea sin cambios
```

---

## 📊 Tablas

| Columna 1 | Columna 2 | Columna 3 |
|-----------|-----------|-----------|
| Celda A   | Celda B   | Celda C   |
| Celda D   | Celda E   | Celda F   |

Con alineación:

| Izquierda | Centro | Derecha |
|:----------|:------:|--------:|
| texto     | texto  |   texto |
| alineado  | centro |     der |

Con formato dentro de celdas:

| Comando | Tipo | Descripción |
|---------|------|-------------|
| `git init` | ✅ Básico | Inicializa un repositorio |
| `git clone` | 📥 Clonar | Clona un repositorio remoto |
| `git commit` | 💾 Guardar | Guarda los cambios |
| `git push` | 🚀 Subir | Sube cambios al remoto |

---

## 💬 Citas y Alertas

> Cita básica de una línea.

> Cita multilínea.
> Segunda línea de la misma cita.
> Tercera línea.

> Primera cita
>
> > Cita anidada dentro
> >
> > > Tercer nivel de anidación

> **Cita con formato.**
> Puede tener *cursiva*, `código` y más.

> [!NOTE]
> Información que el usuario debe tener en cuenta al leer.

> [!TIP]
> Consejo opcional para ayudar al usuario a tener más éxito.

> [!IMPORTANT]
> Información crucial necesaria para que los usuarios tengan éxito.

> [!WARNING]
> Contenido crítico que demanda atención inmediata por riesgos potenciales.

> [!CAUTION]
> Consecuencias negativas potenciales de una acción.

---

## ➖ Líneas Horizontales

Con guiones:

---

Con asteriscos:

***

Con guiones bajos:

___

---

## ✅ Task Lists

- [x] Tarea completada
- [ ] Tarea pendiente
- [x] Otra completada
- [ ] Por hacer
  - [x] Sub-tarea completada
  - [ ] Sub-tarea pendiente

---

## 🌐 HTML en Markdown

Salto de línea forzado:<br>Segunda línea aquí.

<div align="center">

### 🎯 Texto centrado con HTML

Esto está centrado en GitHub.

</div>

<!-- Este comentario es invisible en el resultado renderizado -->

Texto con comentario invisible arriba ↑ (no se ve en GitHub).

<kbd>Ctrl</kbd> + <kbd>C</kbd> — Teclas con estilo de teclado

<pre>
  Texto     preformateado
  con       espacios       exactos
</pre>

---

## 👥 Menciones y Referencias (GitHub)

> ⚠️ Estas funcionalidades son **exclusivas de GitHub** y no se renderizan en otros parsers.

```
@usuario              → Menciona a un usuario (envía notificación)
@org/team-name        → Menciona a un equipo entero

#123                  → Referencia al Issue o PR número 123
usuario/repo#456      → Issue en otro repositorio
GH-789                → Sintaxis alternativa de referencia

a1b2c3d4              → Referencia a un commit por SHA
```

Palabras clave para **cerrar Issues automáticamente** al hacer merge:

```
Closes #123
Fixes #456
Resolves #789
```

---

## 🔢 Notas al Pie

Este texto tiene una nota al pie.[^1]

Aquí hay otra nota más larga.[^nota]

[^1]: Esta es la nota al pie número 1.
[^nota]: Esta nota puede tener contenido más extenso y detallado explicando algo importante.

---

## 🗂️ Colapsar Contenido

<details>
<summary>🔽 Haz clic para ver los pasos de instalación</summary>

### Pasos

1. Clona el repositorio
```bash
git clone https://github.com/usuario/repo.git
```

2. Instala dependencias
```bash
npm install
```

3. Ejecuta el proyecto
```bash
npm start
```

</details>

<details>
<summary>⚙️ Configuración avanzada</summary>

Puedes incluir:
- Listas ✅
- **Negrita** e *cursiva*
- Tablas

| Config | Valor |
|--------|-------|
| Puerto | 3000  |
| Debug  | true  |

</details>

---

## 🛡️ Escapar Caracteres

Usa `\` antes del carácter para mostrarlo literalmente:

\*no es cursiva\*

\**no es negrita\**

\# no es encabezado

\[no es un link\]

\`no es código\`

\> no es una cita

\- no es lista

\| no es tabla

\\ barra invertida literal

Caracteres que se pueden escapar: `\ ` * _ { } [ ] ( ) # + - . ! |`

---

## ➗ Matemáticas

Inline: El valor de $\pi \approx 3.14159$ y la fórmula de Einstein es $E = mc^2$.

Bloque — Fórmula cuadrática:

$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

Sumatoria:

$$
\sum_{i=1}^{n} x_i = x_1 + x_2 + \cdots + x_n
$$

Integral:

$$
\int_{a}^{b} f(x)\,dx = F(b) - F(a)
$$

---

## 📌 Referencia Rápida

| 🏷️ Elemento | ✏️ Sintaxis |
|-------------|------------|
| Encabezado H1 | `# Título` |
| Encabezado H2 | `## Título` |
| Encabezado H3 | `### Título` |
| **Negrita** | `**texto**` |
| *Cursiva* | `*texto*` |
| ***Negrita + Cursiva*** | `***texto***` |
| ~~Tachado~~ | `~~texto~~` |
| `Código inline` | `` `código` `` |
| Bloque de código | ` ```lenguaje ` |
| 🔗 Link | `[texto](url)` |
| 🖼️ Imagen | `![alt](url)` |
| 📊 Tabla | `\| col \| col \|` |
| 💬 Cita | `> texto` |
| ✅ Tarea hecha | `- [x] tarea` |
| ⬜ Tarea pendiente | `- [ ] tarea` |
| ➖ Línea horizontal | `---` |
| 🔢 Nota al pie | `texto[^1]` |
| 😄 Emoji | `:nombre_emoji:` |
| 💬 Comentario | `<!-- comentario -->` |
| ➗ Matemática inline | `$formula$` |
| ➗ Matemática bloque | `$$formula$$` |

---

> 📖 **Recursos oficiales:**
> - [Especificación GFM](https://github.github.com/gfm/)
> - [Docs de GitHub Markdown](https://docs.github.com/en/get-started/writing-on-github)
> - [Emoji Cheat Sheet](https://github.com/ikatyang/emoji-cheat-sheet)
> - [Markdown Guide](https://www.markdownguide.org/)

---

*✨ Creado con GitHub Flavored Markdown — Happy coding! 🚀*