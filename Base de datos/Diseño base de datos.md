Base de Datos: Diseño

1. Identificación de Entidades Principales
Usuario
Empresa
Accion


2. Definir Atributos para cada Entidad

Usuario:

DNI (PK)
email
contraseña
nombre
saldo
acciones

Empresa:

id_empresa (PK)
nombre
acciones

Accion:

id_accion (PK)
valor
id_empresa (FK)
DNI (FK)

3. Relaciones entre Entidades

Una Empresa emite Acciones.
Un Usuario compra Acciones.
Un Usuario vende Acciones.

4. Normalización y Modelo Relacional
Aplicamos el proceso de normalización hasta alcanzar la Tercera Forma Normal (3FN):

Usuario (DNI (PK), nombre, email, saldo, acciones)
Empresa (id_empresa (PK), nombre, acciones)
Accion (id_accion (PK), valor, id_empresa (FK), DNI (FK))

Documentación del Diseño
Título: Modelo Relacional de la Base de Datos ARGBroker Demo

Descripción: Este modelo relacional representa las entidades y sus relaciones necesarias para la aplicación ARGBroker Demo. La base de datos almacenará información sobre los usuarios, empresas, acciones, permitiendo realizar las operaciones de compra y venta de acciones.

Notas:

Cada entidad tiene una clave primaria (PK) para identificar de forma única cada registro.
Se utilizan claves foráneas (FK) para establecer relaciones entre las tablas, garantizando la integridad referencial.