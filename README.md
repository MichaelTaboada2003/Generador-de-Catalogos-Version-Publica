# Generador de Catalogos

> **Nota**: Por cuestiones de privacidad y futura comercialización, el código se mantendrá privado, sin embargo, se explicará a detalle el proceso.

## Contexto del caso

### *Cómo surge*

Este proyecto surgió de acuerdo a una necesidad planteada; Un negocio cercano quería tener un catálogo de productos, 
los cuáles se generasen de acuerdo al stock de su inventario.

### *Objetivo*

Mostrar la disponibilidad del inventario de un negocio a sus respectivos clientes a través de un catálogo en formato PDF, el cuál sea estético y que represente los productos que ofrece.

### *Detalles del caso*

- El inventario se encuentra en una hoja de cálculo de Google (Google Sheet).
- El catálogo tiene que ser un PDF.
- Hay que implementar el diseño entregado por el negocio en el catálogo.

### *Cómo funciona*

Funciona a través de un script de Python ejecutado manualmente. El script se tarda en promedio 10 segundos por cada página creada para el PDF. Dicho PDF luego es compartido con el negocio. El script recibe un diseño seleccionado mediante una variable de entorno, además de que es diseño es independiente del código, por lo tanto, *modificar el diseño no afecta la funcionalidad del código* y a partir de dicho diseño se crea el PDF, pero puede recibir otros diseños y generar distintos PDFs. Por lo que, el negocio es en realidad propietaria del diseño, no obstante el código no.

Por otro lado, si bien es cierto que, los negocios no cambian regularidad su diseño y que los cambios se puede implementar rápidamente dado que solo es modificar un template de acuerdo al cliente, a medida que hayan más negocios o incluso más diseños para un mismo negocio, puede ser algo problemático al tener que ejecutarse manualmente y además habría que tener un comunicación constante entre cliente y desarrollador.

### *Problemas actuales del código* 

- Necesidad de comunicación constante entre cliente y desarrollador.
- Representa un trabajo manual y repetitivo.

### *Solución de los problemas actuales*

Ambos problemas se solucionan a través de una interfaz la cuál haga uso de una API que conecte a la interfaz con el código, la idea central es que a través de la interfaz, el usuario pueda hacer uso por sí mismo de la generación de catálogo, con lo cual, no habría necesidad de haber una comunicación para la ejecución ni de hacer un trabajo manual. 

> **Nota**: Los cambios en el diseño sería evidentemente solicitados por los clientes y efectuados con cierto tiempo de implementación.

# Modelo de negocio

Para el modelo de negocio se podría implementar: 

1. Un modelo de suscripción, el cual contaría con un lapso y una cantidad limitada de peticiones de cambios en el diseño.
2. Cobrar una pequeña suma por cada catálogo generado y por cada petición de cambio.

Sin embargo la primera funcionalidad sería más práctica, dado de que generar un solo catálogo debería ser suficiente, a menos de que haya un cambio en el diseño.

# Qué exactamente hace el código

- Recibe los datos.
- Descarga las imágenes y le quita el fondo.
- Crea individualmente PDFs y une dichos PDFs.

*Los diseños son pasados como un parámetro para la función que crea individualmente los pdf.*

### Las librerías más importantes fueron

| Librería | Descripción     |
| :-------- | :------- | 
| `weasyprint`      | `Convierte el archivo HTML y CSS en PDF ` |
| `pandas`      | `Manipulación de datos` |
| `pillow`       | `Eliminar fondo` |
| `PyPDF2`       | `Manipulación de PDFs` | 

#### Instalación

```
  pip install weasyprint
```

```
  pip install pandas
```

```
  pip install pillow
```

```
  pip install PyPDF2
```
> **Nota**: En el caso de weasyprint hay que aplicar algunos pasos extras
#### Documentación de weasyprint

[Weasyprint](https://doc.courtbouillon.org/weasyprint/stable/)


