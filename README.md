# Generador de Catalogos

> **Nota**: Por cuestiones de privacidad y futura comercialización, el código se mantendrá privado, sin embargo, se explicará a detalle el proceso.

## Contexto del caso

### *Cómo surge*

Este proyecto surgió de acuerdo a una necesidad planteada; Un negocio cercano quería tener un catálogo de productos, 
los cuáles se generasen de acuerdo al stock de su inventario.

### *Objetivo*

Dicho negocio quería principalmente mostrar la disponibilidad de su inventario a través de un catálogo en formato PDF, para poder mostrarlo con finalidad a sus clientes
el cuál sea estético y que representen los productos que ofrece.

### *Detalles del caso*

- El inventario se encuentra en una hoja de cálculo de Google (Google Sheet).
- El catálogo tiene que ser un PDF.
- Hay que implementar el diseño entregado por el negocio en el catálogo.

### Cómo funciona

Funciona a través de un script de Python ejecutado manualmente. Dicho script arroja el PDF en un lapso menor a 5 minutos. Dicho PDF luego es compartido
con el negocio. Dicho script es independiente del diseño, recibe un diseño seleccionado mediante una variable de entorno, por lo tanto, *modificar el
diseño no afecta la funcionalidad del código* y a partir de dicho diseño crea el PDF, pero puede recibir otros diseños y generar distintos PDFs.
El negocio es en realidad propietaria del diseño, no obstante el código es independiente.

Si bien es cierto que, los negocios no cambian con tanta regularidad su diseño y que los cambios se puede implementar rápidamente dado que solo es 
modificar un template de acuerdo al cliente, a medida que hayan más negocios o incluso más diseños para un mismo negocio, puede ser algo problematico 
al tener que ejecutarse manualmente y además habría que tener un comunicación constante entre cliente y desarrollador.

### *Problemas actuales del código* 

- Necesidad de comunicación constante entre cliente y desarrolador.
- Representa un trabajo manual y repetitivo.

### *Solución de los problemas actuales*

Ambos problemas se solucionan a través de una interfaz la cuál haga uso de una API que conecte a la interfaz con el código, la idea central es que, a través
de la interfaz, el usuario pueda hacer uso por sí mismo de la generación de catálogo, con lo cual, no habría necesidad de haber una comunicación para
la ejecución ni de hacer un trabajo manual. 

> **Nota**: Los cambios en el diseño sería evidentemente solicitados por los clientes y efectuados con cierto tiempo de implementación.

# Modelo de negocio

Para el modelo de negocio se podría implementar: 

1. Un modelo de suscripción, el cual contaría con un lapso y una cantidad limitada de peticiones de cambios en el diseño.
2. Cobrar una pequeña suma por cada catálogo generado y por cada petición de cambio.

Sin embargo la primera funcionalidad sería más práctica, dado de que generar un solo catálogo debería ser suficiente, a menos de que haya un cambio en el diseño.

# Qué exactamente hace el código
...
