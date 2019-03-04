# Buenas prácticas para la definición de servicios REST

1. :baby_symbol: - **Llegar al menos al nivel 2 de madurez de las api REST.** 
(Richardson Maturity Model Fowler - https://martinfowler.com/articles/richardsonMaturityModel.html)

1. :gem: - **Diseñar en base a Dominio y no a Modelo.** 
No hacer un recurso por tabla, si no por necesidad de negocio, desnormalizar si es necesario (patrón agregado).

1. :bird:	- **Usar la anidación.** 
La URL /coches/get-by-id-persona/3 sería incorrecta, ya que coches es una colección dentro de personas. la URL correcta sería /personas/3/coches.
Esto puede crear un poco de confusión en los controladores que utilizan **prefijos de rutas**.

    http://test.com/api/v1/coches/findbypersona/305150 -> Incorrecta  
    http://test.com/api/v1/personas/305150/coches/ --> Correcta

1. :restroom: - **Usar plurales.** 
-> /personas o /personas/2

1. :black_nib: - **Usar spinal-case.** 
-> /personas-adultas o /personas-adultas/2

1. :anger: - **Los métodos GET, nunca van a modificar nada ni a generar ninguna acción.**
Siempre serán de solo lectura. Tampoco los parámetros query ( /personas?filter=dani). Que un servició no devuelva ningún resultado, tampoco significa que tenga que ser de tipo GET.

1. :muscle: - **POST vs PUT, la idempotencia.** 
POST va a ser no idempotente, eso significa que dos ejecuciones iguales no tienen porque dar el mismo resultado, en cambio PUT será idempotente, siempre dará el mismo resultado. Después de una ejecución con éxito de un POST debemos tener una URL para acceder al recurso que acabamos de crear.

1. :eyes: - **Para las busquedas usar los parametros query.** -> /personas?pelo=rojo&anyos=33

1. :last_quarter_moon: - **Usar el parametro query sort para ordenar.** 
Permitir la ordenación por varios parámetros, separados por comas y mediante signos de negativo (para descendiente) o positivo (ascendiente) para definir el sentido (/personas?sort=-anyos, +localidad)

1. :page_facing_up: - **Usar la paginación como parametros de query.** 
Usar los parametros offset para informar el primer resultado a devolver y limit para informar de cuantos resultados devolver /personas?offset=10&limit=5. Para devolver el numero total de recursos usar el header **X-Total-Count** de la respuesta.

1. :closed_book: - **Tanto la petición como la respuesta se tienen que entender sin documentación.** 
Independientemente del modelo que tengamos o de la base de datos, los nombres de las propiedades y de las URL deben estan en lenguage prosa y entendible. En caso de duda, hay que pensar que no existe equipo de front.

1. :books:	- **Evitar las sublistas por defecto.** Aunque el modelo personas tenga una colección de coches, no devolverlo para no devolver información de mas (esto puede ser imcompatible con la norma 11) a no ser que sea necesario.

1. :boom: - **Un Error 500 es un error no controlado.** 
Por definición, error 500 significa que **la petición(request) es correcta** pero que no se puede satisfacer por alguna otra razón. Eso significa que no se puede resolver con error 500 porque no esta bien cierto campo o directamente porque falta.

1. :bug: - **Definir un payload de errores genérico**
```Javascript
    {
        "code":null, // Código interno del mensaje, por si no hay suficiente con el codigo de respuesta HTTP
        "message":null, // Mensaje para mostrar al usuario ( una key, si hay i18n )
        "messageDetail":null, // Mensaje para das mas detalles al programador, no se va a mostrar
        "propertyErrors":[
            {
                "property": null, // Que propiedad provoca el error de validación
                "message": null,  // Mensaje con la explicación del error para la propiedad en concreto
                "values": [{"peso": 0}, {"alto": 3}] // valores que se van a interpolar dentro del mensaje ( por ejemplo "el valor de peso debe ser superior a 0 Kg")
            }
        ]
    }
```
(Los campos *code*, *message* y *messageDetail* sólo se debe informar si el codigo HTTP no es suficiente).  
(El array *propertyErrors* solo se debe informar si hay errores de validación en alguna propiedad).