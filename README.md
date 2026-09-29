Ejercicio 2.E.2 06 - Comic

Lógica del programa
Para este ejercicio, me enfoqué en preservar la integridad de los datos de la clase (garantizar invariantes) restringiendo cómo se modifica su estado interno. Diseñé la clase `Comic` con los atributos privados `titulo`, `precio` y `stock`.

En el constructor, agregué validaciones defensivas mediante estructuras condicionales (`if/else`) para evitar que el objeto nazca con un estado inválido (como un precio o un stock negativo). Además, generé los *getters* para consultar la información, pero solo permití el uso de un *setter* para el atributo `precio`. Omití deliberadamente el *setter* de `stock` para evitar modificaciones arbitrarias desde el exterior.

Para alterar la cantidad de cómics, diseñé dos métodos de negocio específicos:
1. `reponerStock(int cantidad)`: Verifica que la cantidad a ingresar sea mayor a cero antes de sumarla al stock actual.
2. `venderUnidad()`: Evalúa si hay ejemplares disponibles (`stock > 0`) antes de restar una unidad. Si no hay stock, bloquea la operación y avisa por consola.

Dentro de la clase `Main`, implementé la siguiente prueba:
1. Instancié un objeto `Comic` (Spiderman) con un stock inicial de apenas 1 unidad.
2. Evoqué el método `venderUnidad()` para consumir ese único ejemplar.
3. Volví a llamar a `venderUnidad()` inmediatamente después para forzar un escenario sin stock. Al hacerlo, pude comprobar por consola que mi clase protegió el estado interno, bloqueó la venta y evitó que el inventario quedara en números negativos.

Ejecución en consola
<img width="1366" height="720" alt="{ADE3B5BB-0858-4FF0-A85A-F6F34DA417B9}" src="https://github.com/user-attachments/assets/3932e704-c701-45f0-bde8-ab1089506d85" />
