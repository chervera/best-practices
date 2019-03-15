# Buenas prácticas de programación transversales.

Este es un conjunto de buenas practicas aplicables a cualquier tipo de programación y de lenguage. Seguirlas hará que nuestro codigo sea mantenible, escalable y de calidad. De paso crecerá nuestro **orgullo de programador**.

1.  :point_up: - **Single Responsibility Principle (SRP)**. Este principio habla de que cada elemento en programación sirva únicamente para una objetivo especifico.  
    Por lo tanto un método save(), solo va a guardar los datos. Si también se tiene que enviar un mail informando del cambio, se creará un método a parte.

1.  :kiss: - **KISS - Keep it simple, stupid**. Como dice la misma frase, hay que hacerlo sencillo. Todo. Como mas sencillo, mas mantenible, mas escalable, mas testeable. En el futuro te lo agradecerás.

1.  :cyclone: - **DRY - Don't repeat yourself**. No te repitas. De esta forma el código que hagas, será mucho más mantenible, ya que solo estará una vez. Mas mantenible, ya que solo estará una vez. Mas testeable, ya que solo estará una vez. ya que solo estará una vez. ya que solo estará una vez.

1.  :capital_abcd: - **Nomenclaturas - Escribir en modo prosa** - Como dice "Uncle Bob" en el libro "Clean Code", nos pasamos el 80% del tiempo leyendo código y solo un 20% escribiendolo. Por eso primaremos que el código se entienda sobre que sea fácil de escribir.  
    Es una buena practica poner en el nombre de las funciones todo lo que hacen, si vemos que nos queda demasiado largo, hay que plantearnos si nos estamos saltando la norma **SRP**.

           person.crtDoc();                   -> incorrecto
           person.createDocumentation()       -> correcto

1.  :revolving_hearts: - **Convenciones** - Todos los lenguages suelen tener unas convenciones que dictan la forma de escribirlo, [JAVA](https://www.oracle.com/technetwork/java/codeconventions-150003.pdf), [JavaScript - (no tiene unas directamente, pero se puede usar las de google)](https://google.github.io/styleguide/jsguide.html#naming) [C#](https://docs.microsoft.com/es-es/dotnet/csharp/programming-guide/inside-a-program/coding-conventions). Es conveniente seguirlas, de esta forma el código de todo el equipo sera homogéneo.

1.  :rainbow: - **Separación de capas**. Las aplicaciones de software, suelen estar divididas por capas lógicas (Controladores, Servicios, Persistencia...). El no respetarlas, no siempre significa que el código no "funcione".  
    Podemos hacer una consulta en un controlador, pero aunque parezca más rápido, hará que incumplamos muchas de las buenas practicas descritas y por tanto a la larga (o no tan larga) será una gran perdida de tiempo y un incremento de dolores de cabeza.

1.  :deciduous_tree: - **Deja el bosque (código) mas limpio de lo que lo encontraste**. Cuando nos ponemos a resolver un problema en un código o a hacer un evolutivo, muchas veces nos encontramos con que lo que ya está echo, no sigue los princípios de buenas prácticas.  
    Suele ser más cómodo seguir tal i como está, pero lo que hay que hacer es hacer nuestra tarea y arreglar lo que esté mal. De esta forma, se equilibra el estropeo al que tiende el software de forma natural.

1.  :pencil2: - **Escribe código que NO necesite ser documentado**. Si seguimos todas las buenas prácticas aquí escritas, nuestro código no debería necesitar de documentación, ya que se debería entender por si solo. El principio no dice que no se documente, si no que cuando se necesite documentar una función/objeto/código nos tiene que saltar la alarma, ya que igual estamos saltandonos alguna de las buenas prácticas anteriores.
