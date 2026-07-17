# Ejemplo
Ramón GC
2026-07-16

Hola mundo.

Se siguen los pasos descritos en el capítulo 18 de Happy Git and GitHub,
mediante la instrucción `output: github_document`, pero no se genera el
archivo intermedio mencionado por los autores con extensión `.md`. ¿Será
por qué el documento es Quarto y no R Markdown? Se investiga

La IA menciona que la sintaxis es el siguiente:

    format:
      gfm: default

La fuente es el siguiente:
<https://quarto.org/docs/output-formats/gfm.html>

Dicha página menciona que la sintaxis es:

    ---
    title: "My Project"
    format: gfm
    ---

De esta manera, se genera un archivo GitHub Flavored Markdown (GFM)
\[Markdown con formato GitHub\]. Véase <https://github.github.com/gfm/>
para más información.

Se cambia formato de salida y se valida.

Listo! Sí se genera el archivo formato `gfm`.

Ahora, por último, se genera un bloque de código

``` r
library(tidyverse)
```

    Warning: package 'tidyverse' was built under R version 4.5.3

    Warning: package 'ggplot2' was built under R version 4.5.3

    Warning: package 'tibble' was built under R version 4.5.3

    Warning: package 'tidyr' was built under R version 4.5.3

    Warning: package 'readr' was built under R version 4.5.3

    Warning: package 'purrr' was built under R version 4.5.3

    Warning: package 'dplyr' was built under R version 4.5.3

    Warning: package 'stringr' was built under R version 4.5.3

    Warning: package 'forcats' was built under R version 4.5.3

    Warning: package 'lubridate' was built under R version 4.5.3

    ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ✔ dplyr     1.2.1     ✔ readr     2.2.0
    ✔ forcats   1.0.1     ✔ stringr   1.6.0
    ✔ ggplot2   4.0.3     ✔ tibble    3.3.1
    ✔ lubridate 1.9.5     ✔ tidyr     1.3.2
    ✔ purrr     1.2.2     
    ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ✖ dplyr::filter() masks stats::filter()
    ✖ dplyr::lag()    masks stats::lag()
    ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
datasets::cars |> 
  count()
```

       n
    1 50

Por otro lado, el capítulo 19 explica cómo generar un documento
presentable a partir de un archivo `.R` de la siguiente manera:

1.  Transformar un archivo R Markdown a tipo R:

- Todo aquello que no sea código añadir al inicio `#'`, comentario
  estilo `roxygen` **PENDIENTE**
- Cambiar sintaxis de las propiedades de los bloques de código mediante
  `#+`

2.  Generar (renderizar) el archivo Markdown y HTML

En mi caso, lo hice a partir de este documento tipo Quarto, pero
solamente genera el archivo HTML no el archivo intermedio legible para
GitHub ¿por qué?

En el libro existen distintas maneras de renderizar (generar) el archivo
R, para el caso de la consola se puede utilizar

```` markdown
```{r}
rmarkdown::render("foo.R")
```
````

Sin embargo, el documento está generado en Quarto. Existe la función
`quarto_render`
<https://quarto-dev.github.io/quarto-r/reference/quarto_render.html> del
paquete `quarto` <https://quarto-dev.github.io/quarto-r/index.html>
donde menciona que para su instalación se requiere instalar la terminal
de Quarto:

“Antes de utilizar el paquete Quarto R, debe instalar la interfaz de
línea de comandos de Quarto desde
<https://quarto.org/docs/get-started/>”

Que digamos es similar al Git Bash pero para poder ejecutar
instrucciones de Quarto no en la terminal sino en R. No está instalado.
