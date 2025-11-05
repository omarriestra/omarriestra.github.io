# Workflow de Publicación con Claude Code

Este documento describe cómo utilizar Claude Code para gestionar y publicar contenido en el sitio web personal.

## 🎯 Filosofía del Workflow

Este sitio utiliza un **enfoque híbrido**:
- **Automatización inteligente** para tareas repetitivas
- **Curación humana** para calidad y relevancia
- **Claude Code como asistente** en todo el proceso

## 📝 Creación de Contenido

### Posts de Blog

#### Paso 1: Brainstorming con Claude
```
Prompt sugerido:
"Basándome en mi writing profile, sugiere 3-5 ideas de posts sobre [tema].
Incluye: título tentativo, ángulo único, y puntos clave a cubrir."
```

#### Paso 2: Generar Borrador
```
Prompt sugerido:
"Crea un borrador de post sobre [tema específico] siguiendo el writing profile.
Longitud: 1000-1500 palabras
Incluye: intro atractiva, secciones claras, ejemplos prácticos, conclusión accionable"
```

#### Paso 3: Crear Archivo
```bash
# Con Claude Code:
hugo new content posts/[nombre-del-post].md

# Estructura de frontmatter:
+++
title = 'Título del Post'
date = 2025-11-05T14:00:00+01:00
draft = false
description = 'Descripción breve para SEO'
tags = ['Tag1', 'Tag2', 'Tag3']
categories = ['Category1', 'Category2']
+++
```

#### Paso 4: Revisión y Edición
- Revisar con Claude: "Revisa este post para claridad, precisión técnica y tono"
- Ajustar manualmente según necesario
- Verificar links y referencias
- Añadir ejemplos o contexto adicional

### Proyectos

#### Estructura Recomendada
```markdown
# Título del Proyecto

## 🎯 Concepto/Visión
Qué problema resuelve

## 🔍 El Problema/Desafío
Contexto y motivación

## 💡 La Solución
Cómo se abordó

## 🛠️ Stack Tecnológico
Herramientas utilizadas

## 📊 Resultados
Métricas e impacto

## 💭 Aprendizajes
Lecciones clave

## 🔮 Próximos Pasos
Roadmap futuro
```

### AI Briefings

#### Workflow de Curación
1. **Recopilación**: Agregar fuentes relevantes
2. **Filtrado**: Claude ayuda a identificar lo importante
3. **Análisis**: Extraer insights clave
4. **Síntesis**: Crear briefing estructurado
5. **Revisión**: Verificar precisión y relevancia

#### Prompt para Síntesis
```
"Analiza estos [N] artículos sobre IA y crea un briefing ejecutivo con:
- Resumen de 2-3 párrafos
- 5-7 puntos clave
- Implicaciones de negocio
- Recomendaciones accionables"
```

## 🔄 Proceso de Publicación

### Preview Local
```bash
# Iniciar servidor de desarrollo
hugo server --buildDrafts

# Abrir en navegador
# http://localhost:1313

# Claude Code puede ayudar a verificar:
# - Links rotos
# - Formato de markdown
# - Frontmatter correcto
```

### Preparar para Producción

#### 1. Verificación Pre-Commit
```
Checklist con Claude:
"Revisa estos archivos antes de commit:
- ¿Frontmatter completo y correcto?
- ¿Tags y categorías apropiados?
- ¿Links funcionando?
- ¿Imágenes optimizadas?
- ¿Ortografía y gramática?
- ¿Tono consistente con writing profile?"
```

#### 2. Build Local (Opcional)
```bash
hugo --gc --minify
# Verifica output en /public/
```

#### 3. Commit
```bash
git add content/posts/nuevo-post.md
git commit -m "Add: [título corto del post]"
```

### Deploy Automático

Una vez pushes a la rama principal:
1. GitHub Actions detecta el cambio
2. Ejecuta workflow de Hugo
3. Construye el sitio
4. Despliega a GitHub Pages
5. Sitio actualizado en ~2 minutos

## 🤖 Prompts Útiles para Claude

### Para Investigación
```
"Investiga las últimas tendencias en [tema] y proporciona:
- 3-5 desarrollos clave
- Fuentes confiables
- Posibles ángulos para un post"
```

### Para Mejora de Contenido
```
"Este post trata sobre [tema]. ¿Cómo puedo:
- Hacer la intro más atractiva
- Añadir ejemplos más concretos
- Mejorar la conclusión
- Optimizar para SEO"
```

### Para Revisión Técnica
```
"Revisa la precisión técnica de este contenido sobre [tema].
Identifica:
- Imprecisiones o errores
- Conceptos que necesitan más explicación
- Suposiciones no fundamentadas"
```

### Para SEO
```
"Optimiza este post para SEO:
- Sugiere meta description (150-160 caracteres)
- Recomienda tags relevantes
- Identifica keywords principales
- Sugiere mejoras de estructura"
```

## 📊 Mantenimiento Continuo

### Revisión Mensual
Con ayuda de Claude:
- Revisar posts antiguos para actualizaciones
- Identificar contenido que necesita refrescarse
- Verificar links rotos
- Analizar temas populares para más contenido

### Optimización
```
"Analiza estos 5 posts y sugiere:
- Temas relacionados para nuevos posts
- Oportunidades de interlinking
- Mejoras de estructura o formato
- Temas que resuenan con la audiencia"
```

## 🎨 Personalización del Writing Profile

El archivo `data/writing-profile.toml` guía todo el contenido.

### Actualizar con Claude
```
"Basándome en estos últimos posts que he escrito,
sugiere ajustes a mi writing profile para reflejar mejor
mi estilo actual"
```

## 🛠️ Comandos Útiles

### Crear Contenido
```bash
# Nuevo post
hugo new content posts/titulo.md

# Nuevo proyecto
hugo new content projects/nombre-proyecto.md

# Nuevo briefing
hugo new content ai-briefings/fecha.md
```

### Gestión
```bash
# Ver estructura del sitio
tree content/

# Buscar contenido
grep -r "palabra clave" content/

# Listar posts recientes
ls -lt content/posts/
```

### Git
```bash
# Status
git status

# Ver cambios
git diff

# Commit con mensaje descriptivo
git commit -m "Add: título del contenido"

# Push a rama de trabajo
git push origin [nombre-rama]
```

## 🔍 Troubleshooting

### Build Falla
```
Claude puede ayudar:
"El build de Hugo falló con este error: [error]
¿Qué puede estar mal y cómo lo soluciono?"
```

### Contenido No Aparece
- Verificar `draft = false` en frontmatter
- Verificar fecha no está en el futuro
- Verificar estructura de carpetas correcta

### Formato Roto
- Verificar markdown válido
- Verificar shortcodes de Hugo
- Verificar frontmatter TOML correcto

## 📚 Recursos

### Hugo
- [Hugo Documentation](https://gohugo.io/documentation/)
- [Hugo Shortcodes](https://gohugo.io/content-management/shortcodes/)
- [Congo Theme Docs](https://jpanther.github.io/congo/)

### Git/GitHub
- [Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
- [GitHub Pages](https://docs.github.com/en/pages)

### Writing
- [Writing Profile](data/writing-profile.toml)
- [Markdown Guide](https://www.markdownguide.org/)

## 💡 Best Practices

1. **Consistencia**: Mantén estructura similar entre posts
2. **Calidad sobre Cantidad**: Mejor un post excelente mensual que posts mediocres semanales
3. **Documentación**: Usa Claude para documentar decisiones y aprendizajes
4. **Iteración**: Mejora contenido basado en feedback
5. **Backup**: Git es tu backup, commit frecuentemente

## 🎯 Workflow Ideal

```
[Idea]
  ↓
[Research con Claude]
  ↓
[Outline/Estructura]
  ↓
[Borrador con Claude]
  ↓
[Revisión Humana]
  ↓
[Ediciones/Refinamiento]
  ↓
[Preview Local]
  ↓
[Commit]
  ↓
[Push]
  ↓
[Auto-Deploy]
  ↓
[Publicado ✅]
```

---

**Este workflow está diseñado para maximizar la eficiencia manteniendo alta calidad.** Claude Code es tu copiloto, pero tú sigues siendo el piloto.

*Última actualización: Noviembre 2025*
