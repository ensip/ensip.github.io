# CREAR CAMPOS NUEVOS PARA AGENCIA DE VIAJES - COCHES 

Debido a un nuevo contrato con una agencia de coches los comerciales tienen que añadir nuevos campos que nos van a cobrar la agencia al final de cada mes.   
Cada venta debe tener unos campos nuevos a rellenar por el comercial.

## Campos:
  1. Seguro  
      * Rango: 21-24 años: seguro (30€/$) + 50% (15€/$) = 45€/$
	   * Rango: 25-75 años: seguro (30€/$)
	   * Rango: 76-80 años: seguro (30€/$) + 50% (15€/$) = 45€/$
  2. Combustible
      * Económicos: 54€/$
      * Medios: 60€/$
  3. Recogida aeropuerto:  20€/$
  4. Chofer adicional: 3€/$ x cada día renta
  
### 1. Seguro
Dependiendo del rango de edad tiene un incremento porcentual (%) al precio del seguro.
### 2. Combustible
Según que tipo de coche es tiene un precio u otro el combustible.

## Requisitos
Cuando el coche sea del proveedor ***RIESGO AVC*** - será obligatorio.  
En caso de los precios en **EUROS** se deberá cobrar un 5% más debido al tipo de cambio actual.

#### Dudas
* **(Campo 1)**: ¿Habrá un campo para el precio del seguro, ahora mismo 30, y otro para el suplemento? ahora mismo 15.
Si es así, ¿Donde se tiene que ver reflejado la suma, 45?
* **(Campo 2)**: Las categorías que tenemos son : 
    1. ECONOMICO MECANICO CON SEGURO
    2. ECONOMICO AUTOMATICO CON SEGURO
    3. MEDIO MECANICO CON SEGURO
    4. MEDIO AUTOMATICO CON SEGURO
    5. REX
    6. ECONOMICO MECANICO SIN SEGURO  
    Supongo que las categorías 1,2 y 6 serían económicos: 45€ y 3 y 4, medios: 60.
Se confirmar esta suposición?  
La 5, Rex que sería?
* **(Campo 4)**: ¿Que quiere decir que son 3€ por cada día de renta? se tiene que hacer algún cálculo en este campo? por ejemplo multiplicar 3 por el campo que ya existe ***Cantidad de días*** ?


## Recursos
* Crear tabla nueva de ***datos_coches*** para poner los campos nuevos.
* Crear tabla de ***rangos***, con precio y suma de incremento, para poderlo cambiar siempre que quiera.
* Crear tabla de ***precio*** si euros o dólares por si hay que hacer incremento.
* Modificar tabla de ***cats_coches*** para añadir el precio de cada tipo
* Crear tabla de ***configuración*** de datos de coche para tener los campos recogida aeropuerto y chofer adicional.

## Lógica
Como hay campos con valores fijos y otros que dependen de campos previamente rellenados, iría rellenando los campos según se rellenen los campos previos.  
* **Chofer** es por cantidad de días, cuando seleccionen la cantidad de días, calcularía el precio por el valor que tenga. Mientras no escojan nada será x 1.
* El **combustible** se pondría en cuanto seleccionasen la categoría de coche.  
* Para el precio del **seguro** el comercial tendrá que seleccionar entre 3 rangos, al seleccionarlo se calcularán los precios.
* La **recogida** al aeropuerto se puede poner automáticamente al entrar en el producto coche.
### Duda
Como sabré la divisa? hasta ahora fijo la divisa de la venta en función de los comprobantes, o sea, que hasta que no se inserta un comprobante no sé que divisa tiene una venta.
¿Re calculo el precio cuando hayan ingresado la venta?

---