# ARGBroker Demo

## Descripción del Contexto, Objetivo y Alcance del Diagrama

El diagrama de clases del sistema ARGBroker Demo ha sido diseñado para capturar las principales entidades y relaciones necesarias para cumplir con los requerimientos funcionales especificados. El objetivo del diagrama es proporcionar una visión clara de la estructura de clases, atributos y métodos, así como de las interacciones entre las diferentes entidades dentro del sistema.

## Nomenclatura Elegida

- **Clases**: Nombres en singular y con la primera letra en mayúscula (e.g., `Usuario`, `Inversor`, `Portafolio`).
- **Atributos**: Nombres en minúscula y separados por guiones bajos (e.g., `nombre`, `email`).
- **Métodos**: Nombres en minúscula y en forma de verbo (e.g., `registrar`, `login`).

## Diagrama de Clases

![Diagrama de Clases](./Diagrama%20de%20Clases.drawio%20(1).png)

## Descripción de Clases

### Usuario

Representa un usuario del sistema.

- **Atributos**:
  - `nombre: str`: El nombre del usuario.
  - `email: str`: El correo electrónico del usuario.
  - `saldo: float`: El saldo disponible del usuario.
  - `password: str`: La contraseña del usuario.
- **Métodos**:
  - `registrar()`: Método para registrar un nuevo usuario.
  - `login()`: Método para iniciar sesión en el sistema.

### Inversor

Representa un inversor en el sistema. Hereda de `Usuario`.

- **Atributos**:
  - `perfil_inversor: str`: El perfil del inversor (conservador, medio, agresivo).
- **Métodos**:
  - `consultar_portafolio()`: Método para consultar el portafolio del inversor.
  - `comprar_accion()`: Método para comprar una acción.
  - `vender_accion()`: Método para vender una acción.

### Portafolio

Representa el portafolio de un inversor.

- **Atributos**:
  - `acciones: Dict[str, int]`: Diccionario de acciones y sus cantidades.
  - `total_invertido: float`: Total invertido en el portafolio.
  - `ganancia_perdida: float`: Ganancia o pérdida total del portafolio.
- **Métodos**:
  - `actualizar_portafolio()`: Método para actualizar el portafolio.
  - `calcular_ganancia_perdida()`: Método para calcular la ganancia o pérdida del portafolio.

### Empresa

Representa una empresa cuyas acciones están disponibles en el mercado.

- **Atributos**:
  - `nombre: str`: El nombre de la empresa.
  - `simbolo: str`: El símbolo de la acción de la empresa.
  - `acciones: List[Accion]`: Lista de acciones de la empresa.
- **Métodos**:
  - `obtener_cotizacion()`: Método para obtener la cotización de las acciones.

### Accion

Representa una acción en el mercado.

- **Atributos**:
  - `simbolo: str`: El símbolo de la acción.
  - `nombre_empresa: str`: El nombre de la empresa.
  - `ultimo_operado: float`: Último precio operado.
  - `cantidad_compra_diaria: int`: Cantidad de compras diarias.
  - `precio_compra_actual: float`: Precio de compra actual.
  - `precio_venta_actual: float`: Precio de venta actual.
  - `cantidad_venta_diaria: int`: Cantidad de ventas diarias.
  - `apertura: float`: Precio de apertura diario.
  - `minimo_diario: float`: Precio mínimo diario.
  - `maximo_diario: float`: Precio máximo diario.
  - `ultimo_cierre: float`: Precio de cierre del día anterior.
- **Métodos**:
  - `actualizar_cotizacion()`: Método para actualizar la cotización de la acción.

### Transaccion

Representa una transacción en el sistema.

- **Atributos**:
  - `tipo: str`: Tipo de transacción (compra o venta).
  - `fecha: datetime`: Fecha y hora de la transacción.
  - `accion: Accion`: La acción involucrada en la transacción.
  - `cantidad: int`: Cantidad de acciones transaccionadas.
  - `precio_unitario: float`: Precio unitario de la acción en la transacción.
  - `comision: float`: Comisión aplicada a la transacción.
- **Métodos**:
  - `calcular_comision()`: Método para calcular la comisión de la transacción.

### Broker

Representa el broker que ejecuta las transacciones.

- **Atributos**:
  - `nombre: str`: El nombre del broker.
  - `comision: float`: La comisión del broker.
- **Métodos**:
  - `ejecutar_transaccion()`: Método para ejecutar una transacción.

## Comentarios y Notas

- Las comisiones del broker se calculan automáticamente en las transacciones para reflejar el costo real de cada operación.