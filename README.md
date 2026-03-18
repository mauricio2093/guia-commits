# Guía de Commits

Esta guía define una convención simple para escribir mensajes de commit claros, consistentes y útiles para el equipo. El objetivo es que el historial de Git permita entender qué cambió, por qué cambió y dónde conviene revisar.

## Formato recomendado

Usa la siguiente estructura:

```text
tipo(scope): descripcion breve en imperativo
```

Ejemplos:

```text
feat(reservas): agregar calendario de disponibilidad
fix(contacto): corregir validacion del formulario
style(header): ajustar espaciado en mobile
```

El `scope` es opcional. Conviene usarlo cuando el proyecto tiene varias áreas funcionales o cuando quieres ubicar el cambio con mayor precisión.

## Principios de redacción

- Escribe en minúsculas.
- Usa verbos en imperativo: `agregar`, `corregir`, `ajustar`, `eliminar`.
- Mantén el resumen breve y específico.
- Evita mensajes genéricos como `cambios varios` o `update`.
- Un commit debe agrupar un cambio coherente, no una mezcla de temas sin relación.

## Tipos de commit

| Tipo | Uso recomendado | Ejemplo |
|------|------------------|---------|
| `feat` | Nueva funcionalidad o comportamiento | `feat: agregar filtro por categoria` |
| `fix` | Corrección de errores o regresiones | `fix: corregir envio duplicado del formulario` |
| `perf` | Mejora de rendimiento sin cambiar la funcionalidad | `perf: optimizar carga de imagenes del hero` |
| `style` | Ajustes visuales, CSS, espaciado o tipografía | `style: ajustar padding del footer` |
| `refactor` | Reorganización interna sin cambio funcional | `refactor: separar validaciones del controlador` |
| `docs` | Documentación técnica o de uso | `docs: actualizar guia de instalacion` |
| `config` | Archivos de configuración o entorno | `config: ajustar variables de produccion` |
| `build` | Compilación, minificación o empaquetado | `build: regenerar assets minificados` |
| `ci` | Workflows, pipelines o automatización | `ci: agregar validacion de tests en pull requests` |
| `deps` | Instalación o actualización de dependencias | `deps: actualizar phpmailer` |
| `security` | Cambios relacionados con seguridad | `security: reforzar validacion csrf` |
| `seo` | Meta tags, sitemap, schema u optimización SEO | `seo: actualizar metadatos de servicios` |
| `content` | Textos visibles o contenido editorial | `content: actualizar textos de la pagina principal` |
| `assets` | Recursos estáticos como imágenes, iconos o fuentes | `assets: reemplazar logo institucional` |
| `chore` | Mantenimiento general sin impacto funcional directo | `chore: limpiar archivos temporales del proyecto` |

## Cuándo usar cada tipo

### `feat`

Úsalo cuando introduces una capacidad nueva para el usuario o una nueva pieza funcional del sistema.

```text
feat: agregar formulario de reservas
feat(blog): incorporar paginacion en listados
```

### `fix`

Úsalo para corregir comportamientos incorrectos, errores reportados o regresiones.

```text
fix: corregir redireccion despues del login
fix(home): solucionar desborde del banner en mobile
```

### `style`

Úsalo para cambios visuales que no alteran la lógica del sistema.

```text
style: ajustar contraste de botones secundarios
style(header): corregir alineacion del menu
```

### `refactor`

Úsalo cuando mejoras la estructura interna del código sin modificar el resultado funcional.

```text
refactor: extraer logica de validacion a una clase dedicada
refactor(menu): simplificar renderizado de enlaces
```

### `docs`

Úsalo para README, guías, instrucciones operativas o documentación técnica.

```text
docs: documentar despliegue local
docs(api): actualizar ejemplos de uso
```

### `config`, `build`, `ci`

Estos tipos separan con claridad los cambios operativos de los cambios de producto.

```text
config: ajustar reglas de apache para rutas limpias
build: regenerar css compilado
ci: agregar workflow de revision automatica
```

## Set mínimo recomendado

Si quieres una convención más simple para el día a día, estos ocho tipos suelen ser suficientes:

```text
feat
fix
style
refactor
docs
config
seo
chore
```

Con ese conjunto ya puedes mantener un historial legible en la mayoría de proyectos web.

## Reglas prácticas

- No mezcles correcciones, rediseño visual y cambios de contenido en un mismo commit si se pueden separar.
- Si un cambio incluye código y configuración, usa el tipo que mejor represente el impacto principal.
- Si el commit toca varias áreas, el `scope` debe reflejar la más relevante.
- Si el cambio fue generado por una tarea de mantenimiento, evita describir la herramienta y describe el resultado.

## Ejemplos correctos

```text
feat(reservas): agregar seleccion de horario
fix(forms): corregir validacion de telefono internacional
style(cards): ajustar sombras y espaciado
refactor(auth): unificar manejo de sesiones
docs: agregar procedimiento de backup
config: actualizar variables para entorno staging
seo(servicios): mejorar title y description
```

## Ejemplos a evitar

```text
update
arreglos
commit final
cambios varios
fix: varias cosas
```

Estos mensajes no permiten entender el cambio ni facilitan la revisión posterior.

## Flujo sugerido

```bash
git status
git diff
git add <archivos_relacionados>
git commit -m "tipo(scope): descripcion breve"
git push origin main
```

## Recomendación final

Prioriza precisión sobre creatividad. Un buen mensaje de commit no intenta impresionar; permite revisar el historial con rapidez, identificar cambios relevantes y reducir ambigüedades cuando haya que depurar, auditar o revertir trabajo.
