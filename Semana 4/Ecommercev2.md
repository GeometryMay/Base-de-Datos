**Diseño de un Modelo ER para un Escenario Comercial:** Los estudiantes diseñarán un modelo ER para una empresa de comercio electrónico, identificando entidades, atributos y relaciones.

Productos de computo

ecommerce privado

vendedor - unico administra
compradores - unicos - no pueden vender

ecommerce SAAS - publico

administrador - superusuarios
venderdor - productos
comprador - pueden ser vendedores

<font color="#ffc000">ecommerce exclusivo</font>

administrador
vendedores - exclusivos (muchos) - provedores
comprador - unicos - no pueden vender

Alcanse del proyecto DBA

- Tabla administrador

id_administrador int primary key
nombre_administrador varchar(50)
app_administrador varchar(50)
apm_administrador varchar(50)
correo_electronico varchar(100)
contrasena varchar(50)
fecha_creacion timestamp | time o date o datetime

Tabla vendedor

id_vendedor int primary key
nombre_vendedor varchar(50)
app_vendedor varchar(50)
apm_vendedor varchar(50)
correo_electronico varchar(100)
contraseña varchar(50)
telefono varchar(10)
fecha_creacion  timestamp
id_estatus int - foranea

Tabla producto

id_producto int primary key
nombre_producto varchar(50)
id_marca int - foranea
modelo varchar(50)
stock int
precio_provedor float
precio_publico float
descripcion text
id_vendedor int - foranea
fecha_creacion timestamp
id_estatus int - foranea

Tabla estatus

id_estatus int primary key
nombre_estatus varchar(50)

Tabla marca

id_marca int primary key
nombre_marca varchar(50)
fecha_creacion timestamp

Tabla cliente

id_cliente int primary key
nombre_cliente varchar(50)
app_cliente varchar(50)
apm_cliente varchar(50)
correo_electronico varchar(100)
contraseña varchar(50)
telefono varchar(10)
fecha_creacion timestamp
id_estatus - foranea

Tabla ubicacion

id_ubicacion int primary key
nombre_contacto varchar(50)
numero_contacto varchar(50)
region - supermanzana varchar(250)
manzana varchar(50)
numero interior varchar(50)
numero exterior (lote) varchar(50)
codigo_postal varchar(5)
calles varchar(50)
referencia varchar(500)
<font color="#ffc000">id_cliente</font>  int - foranea


Tabla ventas

id_venta int primary key
id_vendedor int - foranea
id_cliente int - foranea
id_producto int - foranea
cantidad_producto int
fecha_venta timestamp

```sql
Table cliente {

id_cliente integer [primary key]

nombre_cliente varchar

email varchar [unique]

password varchar

}

  

Table administrador {

id_administrador integer [primary key]

nombre_administrador varchar

email varchar [unique]

password varchar

id_area integer

}

  

Table area {

id_area integer [primary key]

nombre_area varchar

}

  

Table nivel {

id_nivel integer [primary key]

nombre_nivel varchar

}

  

Table estatus {

id_estatus integer [primary key]

nombre_estatus varchar

}

  

Table ticket {

id_ticket integer [primary key]

id_cliente integer

id_administrador integer

id_area integer

incidencia text

id_nivel integer

id_estatus integer

fecha_creacion datetime

fecha_cerrado datetime

}

  

Table comentario {

id_comentario integer [primary key]

id_ticket integer

comentario text

fecha_creacion datetime

}

  

Ref: ticket.id_cliente > cliente.id_cliente

Ref: ticket.id_administrador > administrador.id_administrador

Ref: ticket.id_area > area.id_area

Ref: ticket.id_nivel > nivel.id_nivel

Ref: ticket.id_estatus > estatus.id_estatus

Ref: comentario.id_ticket > ticket.id_ticket

Ref: administrador.id_area > area.id_area
```