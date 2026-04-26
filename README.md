# Plantilla LaTeX ERS (Especificación de Requisitos Software)

Una plantilla profesional de LaTeX para crear documentos de Especificación de Requisitos Software (ERS) / Software Requirements Specification (SRS) con un diseño limpio, moderno y estructurado. [Ejemplo](https://drive.google.com/file/d/1PO1tZquEMscTidKGU0e-lc6_KohoJjbK/view?usp=sharing)

## Características

- **Diseño Profesional**: Portada automática, tipografía limpia y estructuración clara.
- **Entornos Personalizados**: Cajas visualmente atractivas (`tcolorbox`) para Requisitos, Casos de Uso e Iteraciones de Inteligencia Artificial.
- **Numeración Automática**: Los requisitos y casos de uso se numeran de forma automática para facilitar su referenciación.
- **Fácil de extender**: Basado en el estándar `report` de LaTeX, permite utilizar cualquier paquete adicional.

## Estructura del Proyecto

```text
├── srsdocument.cls    # Clase principal de la plantilla (¡No modificar a menos que sepas lo que haces!)
├── EJEMPLO.pdf        # Documento pdf de ERS de ejemplo de la plantilla
├── main.tex           # Documento principal donde se importa todo
├── Makefile           # Utilidad para compilar rápidamente (opcional)
├── chapters/          # Directorio para los capítulos del documento
├── prelims/           # Páginas preliminares (historial de revisiones, etc.)
└── assets/            # Imágenes y otros recursos estáticos
```

## Uso Rápido

1. Clona este repositorio.
2. Modifica la información del proyecto en `main.tex` (`\title`, `\author`, `\version`).
3. Compila el documento utilizando tu editor de LaTeX favorito (Overleaf, TeXStudio, VSCode + LaTeX Workshop) o usa el `Makefile` incluido si estás en un entorno Unix:
   ```bash
   make
   ```

## Extensiones (HyperSnips / VSCode)

Para maximizar tu productividad escribiendo la documentación, te recomendamos usar la extensión **HyperSnips** en VSCode. A continuación, tienes los snippets (fragmentos de código) listos para copiar y pegar en tu archivo `latex.hsnips`, lo que te permitirá autocompletar rápidamente los entornos personalizados:

### Snippets para `latex.hsnips`

```snippets
snippet req "Entorno de Requisito" b
\begin{requirement}{${1:Nombre del Requisito}}
    \reqbody
        {${2:Descripción detallada del requisito}}
        {${3:Entradas esperadas}}
        {${4:Procesamiento a realizar}}
        {${5:Salidas generadas}}
        {${6:Excepciones y manejo de errores}}
\end{requirement}
$0
endsnippet

snippet usecase "Entorno de Caso de Uso" b
\begin{usecase}{${1:Nombre del Caso de Uso}}
    \cubody{
        nombre=${1:Nombre del Caso de Uso},
        id=CU-${2:01},
        actores=${3:Actores involucrados},
        objetivo=${4:Objetivo principal},
        descripcion=${5:Descripción detallada},
        tipo=${6:Primario/Secundario},
        precondiciones=${7:Precondiciones},
        dependencias=${8:Dependencias},
        normal=${9:Secuencia normal de eventos},
        alternativas=${10:Secuencias alternativas},
        postcondiciones=${11:Postcondiciones},
        importancia=${12:Alta/Media/Baja},
        comentarios=${13:Comentarios adicionales}
    }
\end{usecase}
$0
endsnippet

snippet ai "Entorno de Iteración IA" b
\begin{aiiteration}
    \aiprompt{${1:Prompt empleado}}
    \aicontext{${2:Contexto proporcionado a la IA}}
    \aiartifacts{${3:Artefactos o resultados generados}}
    \aianalysis{${4:0}}{${5:0}}{${6:0}} % Correctas, Parciales, Fallidas
    \aicorrections{${7:Correcciones aplicadas manualmente}}
\end{aiiteration}
$0
endsnippet
```

**¿Cómo usarlos?**
Escribe `req`, `usecase` o `ai` al inicio de una línea y presiona `Tab`. Podrás saltar de un campo a otro fácilmente presionando `Tab`.

## Entornos Disponibles

### Requisitos (`requirement`)
Utilizado para detallar los requisitos funcionales y no funcionales del sistema.

### Casos de Uso (`usecase`)
Tabla detallada con toda la información pertinente a las interacciones de los actores con el sistema.

### Iteraciones IA (`aiiteration`)
Perfecto para proyectos modernos donde se utiliza Inteligencia Artificial Generativa. Permite documentar prompts, contextos, y análisis de resultados de forma estructurada.

## Licencia

Este proyecto es de código abierto y está disponible de forma pública para cualquier uso académico o profesional.
