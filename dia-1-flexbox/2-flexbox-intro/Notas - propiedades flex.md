# Code Demo: Exploración de Propiedades / Justificación con Flexbox
# Exploración de propiedades

## El primer grupo tiene que ver con el contenedor flex (flex-container), o el tag 'ul': unordered list, en nuestro ejemplo.

```css
ul { display: flex; }
```
1. Esta propiedad convierte todo en una sola línea. La dirección predeterminada es en fila y en orden estándar (según la fuente).

```css
ul { display: flex; flex-direction: **** }
```
2. *** puede ser row, row-reverse, column, column-reverse
Esta propiedad toma los elementos y los posiciona en una sola fila o columna. El orden puede ser según la fuente, o el inverso de la fuente. Flex-direction define nuestro eje principal.

```css
ul { display: flex; flex-direction: as before; flex-wrap: ***; }
```
3. *** puede ser wrap, wrap-reverse, or nowrap
flex-direction ordena los componentes individuales.
flex-wrap ordena las filas/columnas creadas.

```css
ul { display: flex; flex-flow: ***; }
```
4. flex-flow es un atajo para flex-direction y flex-wrap
Toma dos argumentos, justo como las propiedades individuales:
Ejemplo: row wrap, row-reverse wrap

```css
ul { display: flex; flex-flow: row wrap; justify-content: *** }
```
5. *** puede ser flex-start, flex-end, center, space-between, space-around and space-evenly.
Justify-content determina la distribución de los elementos flex (flex-items) dentro del contenedor flex (flex-container) en el eje principal - en otras palabras, ¿cómo el espacio relativo al ancho de cada item debe ser colocado?

```css
ul { display: flex; flex-flow: row wrap; justify-content: center; height: 400px; }
```
6. Asignar artificialmente altura a la fila. En el siguiente paso, intentaremos alinear ejes cruzados. 

```css
ul { display: flex; flex-flow: row wrap; justify-content: center; height: 400px; align-items: *** }
```
7. *** puede ser flex-start, flex-end, center, baseline, stretch
Esta propiedad alinea los elementos en el eje cruzado. Como estamos trabajando en una columna, el eje cruzado es el eje vertical

## El siguiente set de propiedades tienen que ver con elementos flex específicamente, o los tags 'li' en nuestro ejemplo.

Estas propiedades dictarán cómo ordenar los elementos y qué tan anchos son, así como también la manera en que cambiarán de tamaño dependiendo de las dimensiones.

```css
.flex2 { border: 2px dotted blue; order: *** }
```
8. *** puede ser cualquier entero.
1 moverá las cajas .flex2 al final the la lista, mientras que -1 las moverá al inicio de la misma. 0 es neutral. El estilo de borde nos ayuda a diferenciar entre los 'li' con la clase .flex2 y aquellos que no la tienen.

```css
.flex2 { border: 2px dotted blue; flex-basis: *** }
```
9. flex-basis es análogo al ancho, pero no es lo mismo. El ancho es una medida absoluta - un elemento será así de ancho todo el tiempo. Es posible medir el ancho en unidades relativas (digamos 25% en lugar de 250px), pero al final, la medida en sí nunca va a cambiar. Con flex-basis, intentamos obtener un ancho dado con el espacio que se tiene disponible. Podría ser más pequeño que este ancho, o puede ser mayor, dependiendo del espacio extra y cómo éste está supuestamente distribuido. La distribución del espacio extra esta controlado por las propiedades flex-grow y flex-shrink como se muestra en el siguiente punto.
Do not use width property on the flex items, you should use flex-basis

```css
.flex2 { border: 2px dotted blue; flex-grow: *** }
```
10. *** puede ser  0 o un entero positivo. (Nada dejará de funcionar si el número es negativo, pero no hará nada tampoco).
flex-grow, como flex-shrink (siguiente punto), distribuye el espacio extra una vez que el elemento es mostrado en la página. En este ejemplo, nuestros items flex están alineados al centro (justify-content: center en el elemento 'ul'). Asignando un valor a flex-grow, cualquier espacio extra será asignado en mayor proporción a este elemento, haciéndolo más largo en relación de los demás. Es importante notar que no existe unidad de medida - es simplemente proporción.

```css
.flex2 { border: 2px dotted blue; flex-shrink: *** }
```
11. *** puede ser  0 o un entero positivo. (Nada dejará de funcionar si el número es negativo, pero no hará nada tampoco).
flex-shrink controla lo que pasa con el espacio extra conforme el elemento se hace más pequeño. Asignando un valor a flex-shrink, conforme el elemento se hace más pequeño en la página, este elemento se hará mas pequeño que los otros elementos. No existe unidad de medida - es simplemente proporción.

```css
.flex2 { border: 2px dotted blue; flex: G S B }
```
12. Este es el método abreviado para combinar flex-grow, flex-shrink y flex-basis.
G = flex-grow
S = flex-shrink
B = flex-basis