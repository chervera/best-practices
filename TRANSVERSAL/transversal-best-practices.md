# Buenas prácticas de programación transversales.

Este es un conjunto de buenas practicas aplicables a cualquier tipo de programación y de lenguage. Seguirlas hará que nuestro codigo sea mantenible, escalable y de calidad. De paso crecerá nuestro **orgullo de programador**.

1.  :point_up: - **Single Responsibility Principle (SRP)**. Este principio habla de que cada elemento en programación sirva únicamente para una objetivo especifico.  
    Por lo tanto un método save(), solo va a guardar los datos. Si también se tiene que enviar un mail informando del cambio, se creará un método a parte.

1.  :kiss: - **KISS - Keep it simple, stupid**. Como dice la misma frase, hay que hacerlo sencillo. Todo. Como mas sencillo, mas mantenible, mas escalable, mas testeable. En el futuro te lo agradecerás.

1.  :cyclone: - **DRY**

1.  :pencil2: - **Escribe código que no necesite ser documentado**

1.  :capital_abcd: - **Nomenclaturas** - Como dice "Uncle Bob" en el libro "Clean Code", nos pasamos el 80% del tiempo leyendo código y solo un 20% escribiendolo. Por eso primaremos que el código se entienda sobre que sea fácil de escribir.

        person.crtDoc();                   -> incorrecto
        person.createDocumentation()       -> correcto

1.  :revolving_hearts: - **Convenciones** -

1.  :rainbow: - **Separación de capas**

1.  :deciduous_tree: - **Deja el bosque mas limpio de lo que lo encontraste**
