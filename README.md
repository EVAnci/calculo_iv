# Cálculo IV

Este documento está basado en el programa de la asignatura Cálculo IV, dictada en la [Universidad de Mendoza](um.edu.ar).

## Contenidos

Este documento contiene:
- Funciones de variable compleja
- Ecuaciones de Cauchy-Riemann (analiticidad de funciones)
- Serie de Taylor y Serie de Laurent
- Teorema de los residuos para resolver integrales reales o complejas
- Transformada de Fourier
- Transformada de Laplace
- Antitransformada de Laplace

## Para nerds

### ¿Cómo se puede contribuir?

Si deseas contribuir o realizar aportes al documento solo debes realizar un PR (Pull-Request) en GitHub. Por otro lado, si encuentras errores o piensas que algo debe ser modificado o agregado para mejorar la calidad del contenido solo debes crear un Issue de GitHub.

Al momento de realizar la descripción del Issue, coloca de la forma más detallada posible aquello que piensas que debe ser mejorado o agregado y donde gustarías que sea agregado. Puedes usar de referencia los números de sección de cada capítulo y/o número de página.

> [!IMPORTANT]
> Si se agregan imágenes al documento, es importante que se haga con `git lfs` para no llenar el repositorio con binarios. Ver documentación sobre [Git LFS](https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage).
> Un PR que no respete esta regla será rechazado.

### ¿Cómo puedo compilar el documento?

Si ya tienes experiencia usando $\LaTeX$ entonces es muy sencillo:
1. Debes clonar el repositorio usando
    ```sh
    git clone https://github.com/EVAnci/calculo_iv.git
    ```
    o simplemente realizar un fork del repositorio para usar el tuyo mismo.
2. Este documento ha sido realizado respetando (o al menos intentando respetar) las mejores prácticas para que la composición sea lo más profesional posible. Debido a ello no se hace uso de `pdflatex` sino `lualatex` (más adelante se explica el por qué de esto en detalle).
3. Por `2.` entonces, nos situamos en la raíz del proyecto y usamos el siguiente comando
    ```sh
    lualatex main.tex
    ```
    obviamente, este comando debe ejecutarse unas 3 veces para obtener las referencias cruzadas e indices correctos.
4. Listo, era todo jajaja. Con esto ya esta listo para comenzar a trabajar modificando o agregando lo que desee.

### Justificación de `lualatex`

Bueno, lo más probable es que la mayoría de los que leen este README no estén interesados en esta explicación. Sin embargo, me resulta importante dejarla a modo documentativo. En [este documento](https://br.mirrors.cicku.me/ctan/info/lshort/english/lshort.pdf) introductorio a $\LaTeX$ (recomiendo leerlo) dan varios consejos y sugerencias para mejorar la experiencia al usar $\LaTeX$. Una de las sugerencias es utilizar nuevos compiladores y sus nuevas características, ya que proporcionan ventajas y comodidad.

Evidentemente, el español no es un idioma libre de acentos, tildes y símbolos que no se encuentran en la lista de caracteres ASCII. Usualmente para lograr una buena composición en $\LaTeX$ se usa `\usepackage[spanish]{babel}` acompañado de codificación UTF-8 y algunas configuraciones extra para obtener un buen resultado. Sin embargo, hay cosas que no se integraran del todo como el silabeado (o hyphenation), el soporte para ligaduras y fuentes OpenType (Unicode). Para este propósito surge `\usepackage{polyglossia}`, que no solo permite soporte para múltiples idiomas en el mismo documento, sino también caracteres unicode usados directamente en el texto. Esto hace más cómoda la escritura y mejora el resultado final. 

No estoy intentando venderte `polyglossia` ya que es gratuito. Tampoco soy fanático de `polyglossia` y tampoco me interesa que lo uses en tus proyectos. Si te gusta `babel` es totalmente válido usarlo. De hecho, este ha sido mi primer proyecto $\LaTeX$ usando `lualatex` y `polyglossia`.

Usar `polyglossia` requiere necesariamente de `xelatex` o `lualatex`. Yo siempre he usado `pdflatex` por ser más rápido al compilar en computadores de bajo rendimiento. Sin embargo, `pdflatex` no soporta `polyglossia`, y debido a ello uso `lualatex`. 

Tal vez te preguntes ¿y por qué no `xelatex`? Y bueno, realmente no hay un motivo justificable. Mi respuesta es, porque se algo de *Lua* y pensé que tal vez podría utilizarlo si lo requiero. Más allá de eso, no hay otra razón.

Según mis lecturas, hay algunos comandos que deben ser aplicados de forma distinta en `xelatex`. Como en este proyecto yo he utilizado los que se necesitan para `lualatex`, entonces, no puedo asegurar que el documento compile y se vea bien usando `xelatex`. Si puedes usar `lualatex`, entonces es totalmente recomendable.

## Licencia

Como el código incluido en este proyecto y el documento en $\LaTeX$ no son considerados piezas de software, sino documentos de texto, el documento en formato pdf (y el código $\LaTeX$) está sujeto a **CC BY-SA**. Ver [LICENSE](LICENSE)

Puedes usar, modificar, distribuir e incluso comercializar los contenidos de este documento, siempre y cuando hagas mención del creador y no cambies el tipo de licencia.
