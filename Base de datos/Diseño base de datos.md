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

Documentación:
En una primera instancia realizamos la identifiación de las tres entidades (Usuarios, Accion y Empresa). Posterior a ello, en una segunda instancia, realizamos la descripción de los atributos correspondientes a cada entidad, quedando resultante:

ENTIDAD: Usario
Atributos:
1) DNI (PK): Utilizamos el DNI como identificador único.
2) Email.
3) Contraseña.
4) Nombre.
5) Saldo: Para hacer referencia al saldo de las acciones.
6) Acciones: Que posee en su poder.

ENTIDAD: Accion
Atributos:
1) id_accion (PK): Utilizado para identificar de manera única a la acción.
2) Valor.
3) id_empresa (FK): Utilizada para representar a la empresa que emite la acción.
4) DNI (FK): Utilizado para representar al usuario que compra / vende la acción.

ENTIDAD: Empresa
Atributos:
1) id_empresa (PK): Para representar de manera única a la empresa.
2) Nombre.
3) Acciones: Que emite.

Como tercera instancia, realizamos la determinación de las relaciones y su respectiva cardinalidad, resultando que un "Usuario" Compra/Vende 1 o varias "Acciones" que son emitidas por 1 "Empresa".  Posterior a ello, realizamos la normalización, aplicando la 3FN, en cual establecimos que los atributos de una entidad solamente dependan de la PK. En donde para cada entidad resultó:
 
 Entidad: Usuario
 Atributos:
 1) DNI (PK): Para representar al usuario (D.N.I) de la persona.
 2) Email: Correo electrónico de la persona.
 3) Contraseña: Del correo.
 4) Nombre: De la persona.
 5) Saldo: Corresponde al saldo de las acciones que posee al usuario.
 6) Acciones: Que posee el usuario.

 Entidad: Accion
 Atributos:
 1) id_accion (PK): Para representar a la accion.
 2) Valor: De la acción.
 3) id_empresa (FK): Para representar a la acción que fue emitida por una determinada empresa.
 4) DNI (FK): Para representar a la acción que fue comprada o vendida por dicho usuario.

 Entidad: Empresa
 Atributos:
 1) id_empresa (PK): Para representar a la empresa.
 2) Nombre: De dicha empresa.
 3) Acciones: Que emite dicha empresa.
