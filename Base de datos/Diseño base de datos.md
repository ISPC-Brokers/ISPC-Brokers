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

![image](https://github.com/ISPC-Brokers/ISPC-Brokers/assets/171303582/6cbe5487-0ad1-4976-abce-96f934fa6195)

link: https://lucid.app/lucidchart/7285d314-7dc6-4544-a9c2-38e3f9c9d732/edit?viewport_loc=655%2C-48%2C2219%2C1052%2C0_0&invitationId=inv_9697bae4-30b4-43fc-a0a9-8a94daa29d81

Notas:

Cada entidad tiene una clave primaria (PK) para identificar de forma única cada registro.
Se utilizan claves foráneas (FK) para establecer relaciones entre las tablas, garantizando la integridad referencial.
