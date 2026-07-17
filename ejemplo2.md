# Ejemplo
Ramón GC
2026-07-16

Hola mundo. Se siguen los pasos descritos en el capítulo 18 de Happy Git
and GitHub, mediante la instrucción `output: github_document`, pero no
se genera el archivo intermedio mencionado por los autores con extensión
`.md`. ¿Será por qué el documento es Quarto y no R Markdown? Se
investiga La IA menciona que la sintaxis es el siguiente:

    format:
      gfm: default

La fuente es el siguiente:
<https://quarto.org/docs/output-formats/gfm.html> De esta manera, se
genera un archivo GitHub Flavored Markdown (GFM) \[Markdown con formato
GitHub\]. Véase <https://github.github.com/gfm/> para más información.
Se cambia formato de salida y se valida. Listo! Sí se genera el archivo
formato `gfm`. Ahora, por último, se genera un bloque de código

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
