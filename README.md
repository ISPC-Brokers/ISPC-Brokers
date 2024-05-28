# ISPC-Brokers
# ARGBroker Demo

## Propósito

El propósito de ARGBroker Demo es desarrollar una aplicación de simulación de compra y venta de acciones para la empresa tecnológica ISPC Cba, que se ha registrado como broker de bolsa. Esta aplicación servirá como intermediario entre los inversores y la Bolsa de Valores de Buenos Aires (MERVAL), permitiendo a los usuarios realizar transacciones de compra y venta de acciones en un entorno simulado.

## Contexto

El proyecto surge de la necesidad de ISPC Cba de brindar una herramienta educativa y de simulación para futuros inversores en el Mercado de Valores de Buenos Aires. ARGBroker Demo ofrece una plataforma donde los usuarios pueden experimentar el proceso de inversión, gestionar su portafolio y entender el comportamiento del mercado de acciones sin riesgo financiero real.

## Objetivo

El objetivo principal es desarrollar una aplicación que permita a los usuarios:
- Crear una cuenta con un saldo inicial simulado de $1.000.000.
- Consultar cotizaciones de acciones de empresas argentinas en tiempo real.
- Realizar transacciones de compra y venta de acciones a precios de mercado.
- Gestionar su portafolio de inversiones, visualizando el total invertido, saldo de la cuenta, y las ganancias o pérdidas.
- Calcular la comisión del broker (1.5% por operación).

## Alcance

El proyecto incluye el diseño del sistema en términos de clases y relaciones, así como el diseño de la base de datos necesaria para soportar la aplicación. En esta etapa, no se requiere la implementación del código ni la conexión con bases de datos reales. El foco está en el diseño y la estructuración de la aplicación.

## Nomenclatura

Para el desarrollo del proyecto, se ha acordado la siguiente nomenclatura:
- Clases: Nombres en CamelCase (por ejemplo, `Usuario`, `Accion`, `Transaccion`).
- Atributos: Nombres en snake_case (por ejemplo, `saldo_inicial`, `precio_compra`).
- Métodos: Nombres en snake_case (por ejemplo, `crear_usuario`, `consultar_cotizaciones`).

## Diseño del Sistema

### Clases Identificadas

- **Usuario**: Maneja la información del usuario/inversor.
- **Accion**: Representa una acción específica del mercado.
- **Transaccion**: Registra las operaciones de compra y venta de acciones.
- **Portafolio**: Gestiona las inversiones del usuario y su saldo.

### Relaciones entre Clases

- Un **Usuario** puede tener múltiples **Transacciones**.
- Una **Transaccion** está asociada a una **Accion** específica.
- Un **Usuario** tiene un **Portafolio** que contiene varias **Acciones**.

## Documentación del Diseño

El diseño del sistema y de la base de datos se ha documentado detalladamente, incluyendo diagramas de clases y modelos relacionales, que se adjuntan en este repositorio. Las suposiciones y decisiones de diseño están claramente explicadas en la documentación para asegurar la comprensión y continuidad del proyecto.

## Autores

Este proyecto ha sido desarrollado por los estudiantes del módulo de Programador en ISPC Cba, trabajando de manera colaborativa y asignando tareas específicas a cada miembro del equipo.

- Cristian Vellio
- Fernando Rey
- Mauricio Nahuel Pucheta
- Paula Denise Sarmiento
- Santiago Rosso


