# Buenas prácticas para la maquetación en HTML + CSS

1. :bento: - **Se dará estilos ortientados a componentes.** No se estilará en torno a páginas, si no a componentes, de esta forma será mas reutilizable y documentable. Por lo que:
    .personas .title -> incorrecto
    .block .title       -> correcto

1. :nail_care: - **No se darán estilos a etiquetas de HTML directamente.** No hay que crear acople entre funcionalidad y diseño. Se pondrá clases a los elementos, de esta forma si el tipo de elemento cambia no cambiará el diseño.
    h1 {} -> incorrecto
    .h1 {} -> correcto

1. :black_nib: - **Usar spinal-case.** 

1. :closed_book: -  **Se utilizará notación BEM.** La metodología BEM (http://getbem.com/) sirve para nomenclar las clases orientadas a componentes. Se utilizará de la siguiente forma:

        .nombre-del-componente                   ->.grid
        .nombre-del-componente__sub-bloque       ->.grid__title
        .nombre-del-componente--variante         ->.grid--dark o .grid__title--odd

1. :no_entry_sign: - **Esta prohibido usar !important.** Los !importan en css hacen que se rompan las especificidades de los selectores, por lo tanto no se deben usar. El querer usarlos lo podemos usar como alerta de que algo no se esta haciendo bien.

1. :newspaper: -  **Se debe usar las etiquetas html de forma semántica.** Esto significa que un span es para mostrar texto, un div para un contenedor y un label tiene que ir como acompañamiento a un input, por ejemplo. 

1. :iphone: - **Se desarrolla primero la parte Mobile**. Todo lo que no esté en media queries será para mobile (o para la resolución más pequeña), y las media queries lo arreglarán para pantallas más grandes. Esto se hace porque en las versiones mínimas, hay todo lo necesario para trabajar, a partir de ahí se van añadiendo cosas, por lo tanto solo se añade CSS cuando se necesita añadir cosas no para quitar.

1. :construction_worker: - **No modificar nunca estilos de terceros**. Si utilizamos librerias de terceros, como Bootstrap, Angular, React o cualquiera, nunca las vamos a modificar. Podemos sobreescribir sus estilos utilizando correctamente la cascada o especificidad de CSS.
