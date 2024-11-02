
## Introducción
En este archivo se localizaran los scrips que se deberan de ejecutar dentro de Neo4j, para crear el escenario de datos.

## Contenido

- [Introducción](#introducción)
- [Contenido](#contenido)
- [Nodos](#nodos)
  - [Empresa](#empresa)
  - [Proveedores](#proveedores)
  - [Productos](#productos)
  - [Clientes](#clientes)
- [Enlaces](#enlaces)
  - [Inventario](#inventario)
  - [Pedidos de Compra](#pedidos-de-compra)
  - [Pedidos de Venta](#pedidos-de-venta)
  - [Devoluciones](#devoluciones)
- [Querys](#querys)
  - [Q00.](#q00)
  - [Q01.](#q01)
  - [Q02.](#q02)
  - [Q03.](#q03)
  - [Q04.](#q04)
  - [Q05.](#q05)
  - [Q06.](#q06)
  - [Q07.](#q07)
  - [Q08.](#q08)
  - [Q09.](#q09)
  - [Q10.](#q10)
  - [Q11.](#q11)
  - [Q12.](#q12)
  - [Q13.](#q13)
  - [Q14.](#q14)
  - [Q15.](#q15)

## Nodos

### Empresa

Este es un nodo que funciona como enlace, entre los demas nodos cuando se hagan los demas enlaces
pertinentes

```bash
CREATE (e:Empresa {nombre:"Handtech"})
return e;
```

### Proveedores

```bash
CREATE
(p1:Proveedores {ID: 1, nombre: "ElectroTech Solutions", Pais_de_origen: "México", Telefono: "+52 55 1234 5678", correo: "contacto@electrotech.com"}),
(p2:Proveedores {ID: 2, nombre: "Digital World Corp", Pais_de_origen: "Estados Unidos", Telefono: "+1 415 987 6543", correo: "ventas@digitalworld.com"}),
(p3:Proveedores {ID: 3, nombre: "Premium Gadgets SA", Pais_de_origen: "España", Telefono: "+34 91 456 7890", correo: "info@premiumgadgets.com"}),
(p4:Proveedores {ID: 4, nombre: "Innovación Global", Pais_de_origen: "México", Telefono: "+52 81 2345 6789", correo: "innovacion@global.com"}),
(p5:Proveedores {ID: 5, nombre: "TecnoHogar Ltd.", Pais_de_origen: "Canadá", Telefono: "+1 613 456 7890", correo: "soporte@tecnohogar.ca"}),
(p6:Proveedores {ID: 6, nombre: "Future Vision Electronics", Pais_de_origen: "Alemania", Telefono: "+49 30 1234 5678", correo: "sales@futurevision.de"}),
(p7:Proveedores {ID: 7, nombre: "SmartHome Global", Pais_de_origen: "México", Telefono: "+52 33 9876 5432", correo: "atencion@smarthome.mx"}),
(p8:Proveedores {ID: 8, nombre: "Innovatek Inc.", Pais_de_origen: "Japón", Telefono: "+81 3 1234 5678", correo: "contacto@innovatek.jp"}),
(p9:Proveedores {ID: 9, nombre: "Bright Screens Ltd.", Pais_de_origen: "Reino Unido", Telefono: "+44 20 1234 5678", correo: "ventas@brightscreens.co.uk"}),
(p10:Proveedores {ID: 10, nombre: "Digital Luxury Goods", Pais_de_origen: "Francia", Telefono: "+33 1 2345 6789", correo: "info@digitalluxury.fr"});
```

### Productos

```bash
CREATE
(prod1:Productos {codigo: 401, nombre: "Laptop Premium Ultra", descripcion: "Laptop de alto rendimiento con procesador Intel i9, 32GB RAM, 1TB SSD", precio: 45000, stock: 15, categoria: "Laptops", id_proveedor: 1}),
(prod2:Productos {codigo: 402, nombre: "Televisor OLED 4K 65", descripcion: "Televisor OLED con resolución 4K, 65 pulgadas y HDR10+", precio: 35000, stock: 10, categoria: "Televisores", id_proveedor: 2}),
(prod3:Productos {codigo: 403, nombre: "Laptop Creativa Pro", descripcion: "Laptop para diseño y creación de contenido con tarjeta gráfica dedicada, 16GB RAM, pantalla 4K", precio: 30000, stock: 20, categoria: "Laptops", id_proveedor: 3}),
(prod4:Productos {codigo: 404, nombre: "Smart TV QLED 75", descripcion: "Televisor QLED de 75 pulgadas con resolución 8K y sonido envolvente", precio: 50000, stock: 8, categoria: "Televisores", id_proveedor: 4}),
(prod5:Productos {codigo: 405, nombre: "Ultrabook Empresarial", descripcion: "Ultrabook de uso empresarial con pantalla táctil, 16GB RAM, 512GB SSD", precio: 22000, stock: 30, categoria: "Laptops", id_proveedor: 5}),
(prod6:Productos {codigo: 406, nombre: "Pantalla Curva UltraWide 49", descripcion: "Monitor ultra ancho de 49 pulgadas para experiencia inmersiva, ideal para gamers", precio: 21000, stock: 25, categoria: "Monitores", id_proveedor: 6}),
(prod7:Productos {codigo: 407, nombre: "Laptop Gamer Nitro", descripcion: "Laptop gamer con RTX 3080, 32GB RAM, 1TB SSD", precio: 42000, stock: 12, categoria: "Laptops", id_proveedor: 7}),
(prod8:Productos {codigo: 408, nombre: "TV 4K UHD 70", descripcion: "Televisor 4K de 70 pulgadas con tecnología de inteligencia artificial", precio: 27000, stock: 18, categoria: "Televisores", id_proveedor: 8}),
(prod9:Productos {codigo: 409, nombre: "All-in-One 27 4K", descripcion: "PC todo-en-uno con pantalla táctil de 27 pulgadas y resolución 4K", precio: 15000, stock: 30, categoria: "Computadoras", id_proveedor: 9}),
(prod10:Productos {codigo: 410, nombre: "Televisor Smart UHD 8K 85", descripcion: "Televisor UHD 8K de 85 pulgadas, ideal para grandes espacios", precio: 60000, stock: 5, categoria: "Televisores", id_proveedor: 10}), 
(prod11:Productos {codigo: 411, nombre: "SSD 1TB NVMe", descripcion: "Disco duro sólido NVMe de 1TB, velocidad de lectura 3500 MB/s", precio: 3000, stock: 50, categoria: "Almacenamiento", id_proveedor: 1}),
(prod12:Productos {codigo: 412, nombre: "Mouse Gaming RGB", descripcion: "Mouse gaming con retroiluminación RGB y 16000 DPI", precio: 900, stock: 100, categoria: "Periféricos", id_proveedor: 2}),
(prod13:Productos {codigo: 413, nombre: "Teclado Mecánico", descripcion: "Teclado mecánico con retroiluminación y switches mecánicos", precio: 1500, stock: 60, categoria: "Periféricos", id_proveedor: 3}),
(prod14:Productos {codigo: 414, nombre: "Mousepad Gaming XXL", descripcion: "Mousepad grande para gamers con superficie textil", precio: 500, stock: 80, categoria: "Periféricos", id_proveedor: 4}),
(prod15:Productos {codigo: 415, nombre: "Auriculares Inalámbricos", descripcion: "Auriculares Bluetooth con cancelación de ruido", precio: 2500, stock: 40, categoria: "Audio", id_proveedor: 5}),
(prod16:Productos {codigo: 416, nombre: "Monitor 24 Full HD", descripcion: "Monitor LED de 24 pulgadas con resolución Full HD", precio: 4000, stock: 30, categoria: "Monitores", id_proveedor: 6}),
(prod17:Productos {codigo: 417, nombre: "Adaptador USB-C a HDMI", descripcion: "Adaptador para conectar dispositivos USB-C a HDMI", precio: 700, stock: 70, categoria: "Accesorios", id_proveedor: 7}),
(prod18:Productos {codigo: 418, nombre: "Cámara Web HD", descripcion: "Cámara web con resolución HD 1080p y micrófono incorporado", precio: 1200, stock: 50, categoria: "Periféricos", id_proveedor: 8}),
(prod19:Productos {codigo: 419, nombre: "Hub USB 3.0", descripcion: "Hub USB de 4 puertos, permite conectar múltiples dispositivos", precio: 600, stock: 90, categoria: "Accesorios", id_proveedor: 9}),
(prod20:Productos {codigo: 420, nombre: "Altavoces Bluetooth", descripcion: "Altavoces portátiles Bluetooth con sonido estéreo", precio: 2000, stock: 35, categoria: "Audio", id_proveedor: 10}),
(prod21:Productos {codigo: 421, nombre: "Laptop Premium Ultra", descripcion: "Laptop de alto rendimiento con procesador Intel i9, 32GB RAM, 1TB SSD", precio: 45000, stock: 0, categoria: "Laptops", id_proveedor: 1}),
(prod22:Productos {codigo: 422, nombre: "Smart TV OLED 55", descripcion: "Televisor OLED de 55 pulgadas con resolución 4K y HDR", precio: 32000, stock: 0, categoria: "Televisores", id_proveedor: 2}),
(prod23:Productos {codigo: 423, nombre: "Smartphone Pro Max", descripcion: "Smartphone de última generación con cámara de 108 MP y 256GB de almacenamiento", precio: 28000, stock: 0, categoria: "Smartphones", id_proveedor: 3}),
(prod24:Productos {codigo: 424, nombre: "Tableta Avanzada X", descripcion: "Tableta con pantalla de 12 pulgadas, 128GB de almacenamiento y procesador de alto rendimiento", precio: 18000, stock: 0, categoria: "Tabletas", id_proveedor: 4}),
(prod25:Productos {codigo: 425, nombre: "Monitor Curvo 34", descripcion: "Monitor curvo de 34 pulgadas con resolución UltraWide y frecuencia de actualización de 144Hz", precio: 22000, stock: 0, categoria: "Monitores", id_proveedor: 5});
```

### Clientes

```bash
CREATE
(c1:Cliente {ID: 1, nombre: "Juan Pérez", direccion: "Calle Falsa 123", ciudad: "México D.F.", teléfono: "+52 55 1234 5678", correo_electronico: "juan.perez@email.com"}),
(c2:Cliente {ID: 2, nombre: "María López", direccion: "Av. Reforma 456", ciudad: "Guadalajara", teléfono: "+52 33 9876 5432", correo_electronico: "maria.lopez@email.com"}),
(c3:Cliente {ID: 3, nombre: "Compañía XYZ", direccion: "Paseo de la Reforma 789", ciudad: "Monterrey", teléfono: "+52 81 2345 6789", correo_electronico: "contacto@companiaxyz.com"}),
(c4:Cliente {ID: 4, nombre: "Carlos Martínez", direccion: "Calle 123", ciudad: "Puebla", teléfono: "+52 22 3456 7890", correo_electronico: "carlos.martinez@email.com"}),
(c5:Cliente {ID: 5, nombre: "Sofía Ramírez", direccion: "Calle 456", ciudad: "Tijuana", teléfono: "+52 66 1234 5678", correo_electronico: "sofia.ramirez@email.com"}),
(c6:Cliente {ID: 6, nombre: "Grupo Tech Solutions", direccion: "Blvd. Adolfo López Mateos 321", ciudad: "Querétaro", teléfono: "+52 44 5678 1234", correo_electronico: "info@grupotech.com"}),
(c7:Cliente {ID: 7, nombre: "Andrés González", direccion: "Calle 789", ciudad: "Cancún", teléfono: "+52 98 7654 3210", correo_electronico: "andres.gonzalez@email.com"}),
(c8:Cliente {ID: 8, nombre: "Innovaciones 360", direccion: "Calle Innovación 101", ciudad: "Ciudad de México", teléfono: "+52 55 6789 1234", correo_electronico: "ventas@innovaciones360.com"}),
(c9:Cliente {ID: 9, nombre: "Laura Fernández", direccion: "Calle 222", ciudad: "León", teléfono: "+52 477 1234 5678", correo_electronico: "laura.fernandez@email.com"}),
(c10:Cliente {ID: 10, nombre: "Servicios Integrales SA", direccion: "Calle Empresarial 333", ciudad: "Toluca", teléfono: "+52 72 1234 5678", correo_electronico: "contacto@serviciosintegrales.com"}),
(c11:Cliente {ID: 11, nombre: "Ana García", direccion: "Calle 45", ciudad: "Monterrey", telefono: 5559876543, correo_electronico: "ana.garcia@example.com"}),
(c12:Cliente {ID: 12, nombre: "Luis Martínez", direccion: "Paseo de la Reforma 89", ciudad: "Guadalajara", telefono: 5556543210, correo_electronico: "luis.martinez@example.com"}),
(c13:Cliente {ID: 13, nombre: "Sofía López", direccion: "Calle Juárez 34", ciudad: "Tijuana", telefono: 5553219876, correo_electronico: "sofia.lopez@example.com"}),
(c14:Cliente {ID: 14, nombre: "Fernando Rodríguez", direccion: "Blvd. Juárez 56", ciudad: "Cancún", telefono: 5557890123, correo_electronico: "fernando.rodriguez@example.com"});

```

## Enlaces

### Inventario

```bash
MATCH (e:Empresa)
MATCH (p:Productos)
MERGE (e)-[:INVENTARIO]->(p)
return e,p;
```

### Pedidos de Compra

```bash
MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "ElectroTech Solutions"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 201,
  nombre_producto: "Laptop Premium Ultra", 
  cantidad: 2, 
  precio_unitario: 45000,
  precio_total: 90000,
  fecha_pedido: "13-04-2024", 
  fecha_recepcion: "23-04-2024",
  id_proveedor: 1
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "ElectroTech Solutions"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 202,  
  nombre_producto: "SSD 1TB NVMe", 
  cantidad: 5, 
  precio_unitario: 3000,
  precio_total: 15000,
  fecha_pedido: "10-05-2024", 
  fecha_recepcion: "20-05-2024",
  id_proveedor: 1
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Digital World Corp"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 203,
  nombre_producto: "Mouse Gaming RGB", 
  cantidad: 10, 
  precio_unitario: 900,
  precio_total: 9000,
  fecha_pedido: "15-04-2024", 
  fecha_recepcion: "26-04-2024",
  id_proveedor: 2
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Digital World Corp"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 204,
  nombre_producto: "Televisor OLED 4K 65", 
  cantidad: 1,
  precio_unitario: 3000,
  precio_total: 35000,
  fecha_pedido: "10-05-2024", 
  fecha_recepcion: "20-05-2024",
  id_proveedor: 2
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Premium Gadgets SA"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 205,
  nombre_producto: "Teclado mecanico", 
  cantidad: 5, 
  precio_unitario: 1500,
  precio_total: 7500,
  fecha_pedido: "26-10-2024", 
  fecha_recepcion: "30-10-2024",
  id_proveedor: 3
  }]->(pr)
return e,pr;


MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Premium Gadgets SA"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 206,
  nombre_producto: "Laptop Creativa Pro", 
  cantidad: 1, 
  precio_unitario: 30000,
  precio_total: 30000,
  fecha_pedido: "26-09-2024", 
  fecha_recepcion: "03-10-2024",
  id_proveedor: 3
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Innovación Global"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 207,
  nombre_producto: "Smart TV QLED 75", 
  cantidad: 2, 
  precio_unitario: 50000,
  precio_total: 100000,
  fecha_pedido: "15-02-2024", 
  fecha_recepcion: "20-02-2024",
  id_proveedor: 4
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Innovación Global"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 208,
  nombre_producto: "Mousepad Gaming XXL", 
  cantidad: 20, 
  precio_unitario: 500,
  precio_total: 10000,
  fecha_pedido: "17-01-2024", 
  fecha_recepcion: "22-01-2024",
  id_proveedor: 4
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "TecnoHogar Ltd."})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 209,
  nombre_producto: "Ultrabook Empresarial", 
  cantidad: 2, 
  precio_unitario: 22000,
  precio_total: 44000,
  fecha_pedido: "10-06-2024", 
  fecha_recepcion: "25-06-2024",
  id_proveedor: 5
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "TecnoHogar Ltd."})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 210,
  nombre_producto: "Auriculares Inalámbricos", 
  cantidad: 5, 
  precio_unitario: 2500,
  precio_total: 12500,
  fecha_pedido: "15-07-2024", 
  fecha_recepcion: "30-07-2024",
  id_proveedor: 5
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Future Vision Electronics"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 211,
  nombre_producto: "Monitor 24 Full HD", 
  cantidad: 5, 
  precio_unitario: 4000,
  precio_total: 20000,
  fecha_pedido: "22-02-2024", 
  fecha_recepcion: "10-02-2024",
  id_proveedor: 6
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Future Vision Electronics"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 212,
  nombre_producto: "Pantalla Curva UltraWide 49", 
  cantidad: 5, 
  precio_unitario: 21000,
  precio_total: 105000,
  fecha_pedido: "10-02-2024", 
  fecha_recepcion: "22-02-2024",
  id_proveedor: 6
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "SmartHome Global"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 213,
  nombre_producto: "Adaptador USB-C a HDMI", 
  cantidad: 20, 
  precio_unitario: 700,
  precio_total: 1400,
  fecha_pedido: "26-11-2024", 
  fecha_recepcion: "30-11-2024",
  id_proveedor: 7
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "SmartHome Global"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 214,
  nombre_producto: "Laptop Gamer Nitro", 
  cantidad: 1, 
  precio_unitario: 42000,
  precio_total: 42000,
  fecha_pedido: "29-09-2024", 
  fecha_recepcion: "10-10-2024",
  id_proveedor: 7
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Innovatek Inc."})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{ 
  id_compra: 215,
  nombre_producto: "Cámara Web HD", 
  cantidad: 5, 
  precio_unitario: 1200,
  precio_total: 6000,
  fecha_pedido: "10-06-2024", 
  fecha_recepcion: "10-08-2024",
  id_proveedor: 8
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Innovatek Inc."})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{ 
  id_compra: 216,
  nombre_producto: "TV 4K UHD 70", 
  cantidad: 10, 
  precio_unitario: 27000,
  precio_total: 270000,
  fecha_pedido: "10-05-2024", 
  fecha_recepcion: "10-08-2024",
  id_proveedor: 8
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Bright Screens Ltd."})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 217,
  nombre_producto: "All-in-One 27 4K", 
  cantidad: 2, 
  precio_unitario: 15000,
  precio_total: 30000,
  fecha_pedido: "10-07-2024", 
  fecha_recepcion: "30-07-2024",
  id_proveedor: 9
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Bright Screens Ltd."})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{ 
  id_compra: 218,
  nombre_producto: "Hub USB 3.0", 
  cantidad: 20, 
  precio_unitario: 600,
  precio_total: 12000,
  fecha_pedido: "01-08-2024", 
  fecha_recepcion: "20-08-2024",
  id_proveedor: 9
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Digital Luxury Goods"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 219,
  nombre_producto: "Televisor Smart UHD 8K 85", 
  cantidad: 1, 
  precio_unitario: 60000,
  precio_total: 60000,
  fecha_pedido: "01-09-2024", 
  fecha_recepcion: "20-09-2024",
  id_proveedor: 10
  }]->(pr)
return e,pr;

MATCH (e:Empresa)
MATCH (pr:Proveedores {nombre: "Digital Luxury Goods"})
MERGE (e)-[pd:PEDIDO_DE_COMPRA{
  id_compra: 219,
  nombre_producto: "Altavoces Bluetooth", 
  cantidad: 10, 
  precio_unitario: 2000,
  precio_total: 20000,
  fecha_pedido: "05-04-2024", 
  fecha_recepcion: "05-05-2024",
  id_proveedor: 10
  }]->(pr)
return e,pr;
```

### Pedidos de Venta

```bash
MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Laura Fernández"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 1,
  productos: ["Mousepad Gaming XXL", "Adaptador USB-C a HDMI"],
  cantidad: [1,1],
  precio_venta: 1200,
  precios_unitarios: [500, 700],
  fecha_entrega: "03-11-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Carlos Martínez"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 2,
  productos: ["Televisor OLED 4K 65"],
  cantidad: [1],
  precio_venta: 35000,
  precios_unitarios: [35000],
  fecha_entrega: "10-05-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Sofía Ramírez"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 3,
  productos: ["Mouse Gaming RGB", "Mousepad Gaming XXL"],
  cantidad: [1,1],
  precio_venta: 1400,
  precios_unitarios: [900,500],
  fecha_entrega: "12-06-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Andrés González"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 4,
  productos: ["Auriculares Inalámbricos", "Hub USB 3.0", "Altavoces Bluetooth"],
  cantidad: [1,1,1],
  precio_venta: 5100,
  precios_unitarios: [2500,600,2000],
  fecha_entrega: "25-03-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Juan Pérez"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 5,
  productos: ["Laptop Creativa Pro"],
  cantidad: [1],
  precio_venta: 30000,
  precios_unitarios: [30000],
  fecha_entrega: "28-02-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "María López"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 6,
  productos: ["Smart TV QLED 75"],
  cantidad: [1],
  precio_venta: 50000,
  precios_unitarios: [50000],
  fecha_entrega: "15-05-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Servicios Integrales SA"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 7,
  productos: ["Ultrabook Empresarial", "All-in-One 27 4K"],
  cantidad: [3,1],
  precio_venta: 81000,
  precios_unitarios: [22000,15000],
  fecha_entrega: "15-08-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Grupo Tech Solutions"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta:8,
  productos: ["Cámara Web HD", "Monitor 24 Full HD"],
  cantidad: [3,3],
  precio_venta: 15600, 
  precios_unitarios: [1200,4000],
  fecha_entrega: "02-01-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Innovaciones 360"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 9,
  productos: ["SSD 1TB NVMe", "Mouse Gaming RGB", "Mousepad Gaming XXL"],
  cantidad: [5,5,5],
  precio_venta: 22000,
  precios_unitarios: [3000,900,500],
  fecha_entrega: "08-11-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Compañía XYZ"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 10,
  productos: ["Ultrabook Empresarial", "All-in-One 27 4K", "Monitor 24 Full HD", "Cámara Web HD"],
  cantidad: [1,3,2,2],
  precio_venta: 77400,
  precios_unitarios: [22000,15000,1200,4000],
  fecha_entrega: ""
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Compañía XYZ"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 11,
  productos: ["SSD 1TB NVMe"],
  cantidad: [5],
  precio_venta: 15000,
  precios_unitarios: [3000],
  fecha_entrega: "11-11-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Luis Martínez"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 12,
  productos: ["Mousepad Gaming XXL", "Teclado Mecánico"],
  cantidad: [1,1],
  precio_venta: 2000,
  precios_unitarios: [500,1500],
  fecha_entrega: "26-06-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Ana García"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 13,
  productos: ["SSD 1TB NVMe", "Mousepad Gaming XXL", "Mouse Gaming RGB"],
  cantidad: [1,1,1],
  precio_venta: 4400,
  precios_unitarios: [3000,500,900],
  fecha_entrega: "30-01-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Sofía López"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 14,
  productos: ["Monitor 24 Full HD"],
  cantidad: [1],
  precio_venta: 4000,
  precios_unitarios: [4000],
  fecha_entrega: "27-07-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Fernando Rodríguez"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 15,
  productos: ["Mouse Gaming RGB"],
  cantidad: [1],
  precio_venta: 900,
  precios_unitarios: [900],
  fecha_entrega: "25-08-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Grupo Tech Solutions"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 16,
  productos: ["Mouse Gaming RGB", "Monitor 24 Full HD"],
  cantidad: [3,3],
  precio_venta: 6700, 
  precios_unitarios: [2700,4000],
  fecha_entrega: "23-11-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Carlos Martínez"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 17,
  productos: ["Mouse Gaming RGB", "Monitor 24 Full HD"],
  cantidad: [1,1],
  precio_venta: 4900,
  precios_unitarios: [900,4000],
  fecha_entrega: "10-05-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Juan Pérez"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 18,
  productos: ["Mouse Gaming RGB"],
  cantidad: [1],
  precio_venta: 900,
  precios_unitarios: [900],
  fecha_entrega: "28-02-2024"
  }]->(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "María López"})
MERGE (e)-[pc:PEDIDO_DE_VENTA{
  id_venta: 19,
  productos: ["Monitor 24 Full HD"],
  cantidad: [1],
  precio_venta: 4000,
  precios_unitarios: [4000],
  fecha_entrega: "15-05-2024"
  }]->(c)
return e,c;

```

### Devoluciones

```bash
MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Laura Fernández"})
MERGE (e)<-[d:DEVOLUCION{
  id_devolucion: 1,
  id_venta: 1,
  producto_devuelto: "Adaptador USB-C a HDMI",
  fecha_devolucion: "05-11-2024",
  motivos_devolucion: "El adaptaddor USB-C a HDMI no funciono",
  reembolso: "Si",
  cantidad_reembolso: 700
  }]-(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Grupo Tech Solutions"})
MERGE (e)<-[d:DEVOLUCION{
  id_devolucion: 2,
  id_venta: 8,
  producto_devuelto: "Cámara Web HD",
  fecha_devolucion: "05-01-2024",
  motivos_devolucion: "una de las camaras no encendio",
  reembolso: "Si",
  cantidad_reembolso: 1200
  }]-(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Sofía Ramírez"})
MERGE (e)<-[d:DEVOLUCION{
  id_devolucion: 3,
  id_venta: 3,
  producto_devuelto: "Mousepad Gaming XXL",
  fecha_devolucion: "05-11-2024",
  motivos_devolucion: "Se rompio mientras lo sacaba del empaque",
  reembolso: "No",
  cantidad_reembolso: 0
  }]-(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Luis Martínez"})
MERGE (e)<-[d:DEVOLUCION{
  id_devolucion: 4,
  id_venta: 12,
  producto_devuelto: "Teclado Mecánico",
  fecha_devolucion: "02-07-2024",
  motivos_devolucion: "No funciono la retroiluminación del teclado",
  reembolso: "Si",
  cantidad_reembolso: 1500
  }]-(c)
return e,c;

MATCH (e:Empresa)
MATCH (c:Cliente {nombre: "Sofía López"})
MERGE (e)<-[d:DEVOLUCION{
  id_devolucion: 5,
  id_venta: 14,
  producto_devuelto: "Monitor 24 Full HD",
  fecha_devolucion: "05-08-2024",
  motivos_devolucion: "El monitor llego con el display dañado",
  reembolso: "Si",
  cantidad_reembolso: 4000
  }]-(c)
return e,c;

```

## Querys

En este apartado se localizan las Querys o consultan que dan solución algunas problematicas del escenario de datos.

### Q00.

Esta query funciona para eliminar todo el escenario de datos, es decir
borra todos los nodos contenidos dentro de Neo4j.

```bash
MATCH (n) DETACH DELETE n
```

### Q01.

Descripcion: Obtener la lista de productos que tienen menos de 10 unidades en stock.

```bash
MATCH (p:Productos)
WHERE p.stock <=10
return p.nombre AS Nombre_Producto,p.stock AS Stock;
```

### Q02.

Descripcion: Encontrar los proveedores que suministran productos de una categoría en específico.

```bash
MATCH (pr:Proveedores)
MATCH (p:Productos)
WHERE pr.ID = p.id_proveedor AND p.categoria = "Televisores"
return pr, p;
```

### Q03.

Descripcion: Obtener la lista de pedidos de compra que fueron realizados a un proveedor en específico.

```bash
MATCH (e:Empresa)
MATCH (p:Proveedores)
MATCH (e:Empresa)-[pd:PEDIDO_DE_COMPRA]->(p:Proveedores {ID: 1})
RETURN e.nombre AS Empresa, p.nombre AS Proveedor, 
pd.nombre_producto AS Producto, pd.cantidad AS Cantidad, 
pd.fecha_recepcion AS Fecha_Pedido;
```

### Q04.

Descripcion: Encontrar los productos que han sido comprados por más de 5 clientes diferentes.

```bash
MATCH (e:Empresa)-[pv:PEDIDO_DE_VENTA]->(c:Cliente)
UNWIND pv.productos AS producto_solicitado
MATCH (e)-[:INVENTARIO]->(p:Productos {nombre: producto_solicitado})
WITH p, COUNT(DISTINCT c) AS total_clientes, COLLECT(DISTINCT c.nombre) AS nombres_clientes
WHERE total_clientes >= 5
RETURN p.nombre AS producto, total_clientes, nombres_clientes;
```

### Q05. 

Descripcion: Obtener la lista de todos los  proveedores.

```bash
MATCH (p:Proveedores)
return p.nombre AS nombre_proveedor;
```

### Q06.

Descripcion: Encontrar los pedidos de venta que tienen una devolución

```bash
MATCH (e:Empresa)-[pv:PEDIDO_DE_VENTA]->(c:Cliente)
MATCH (c)-[d:DEVOLUCION]->(e)
WHERE pv.id_venta = d.id_venta
RETURN e AS empresa, pv AS pedido_con_devolucion, d AS detalles_devolucion, c AS cliente
```

### Q07.

Descripcion: Listar los pedidos de venta que tienen un valor total mayor a $10,000.

```bash
MATCH (e:Empresa)-[pd:PEDIDO_DE_VENTA]->(c:Cliente)
WHERE pd.precio_venta >= 10000
RETURN e.nombre AS Empresa, c.nombre AS Nombre_Cliente, 
pd.productos AS Productos, pd.precio_venta AS Total;
```

### Q08. 

Descripcion: Cambiar todos los productos suministrados por un proveedor a otro proveedor.

```bash
MATCH (p:Productos {id_proveedor: 1})
SET p.id_proveedor = 2
RETURN p;
```

### Q09.

Descripcion: Obtener la lista de proveedores que han recibido pedidos de compra por más de $50,000 en total.

```bash
MATCH (e)-[pc:PEDIDO_DE_COMPRA]->(p:Proveedores)
WHERE pc.precio_total > 50000
return e.nombre AS Empresa,p.nombre AS Proveedor,
pc.nombre_producto AS Productos,
pc.cantidad AS Cantidad,pc.precio_total AS TOTAL;
```

### Q10.

Descripcion: Encontrar los productos que se encuentran agotados (sin stock) en el inventario.

```bash
MATCH (p:Productos)
WHERE  p.stock = 0
return p;
```

### Q11.

Descripcion: Obtener la lista de clientes.

```bash
MATCH (c:Cliente)
return c.nombre AS Nombre_Cliente;
```

### Q12.

Descripcion: Eliminar todos los proveedores y sus nodos asociados.

```bash
MATCH (p:Proveedores)
DETACH DELETE p;
```

### Q13.

Descripcion: Todos los productos de una categoría específica eliminados del inventario.

```bash
MATCH (e:Empresa)-[r:INVENTARIO]->(p:Productos {categoria: "Laptops"})
DETACH DELETE p;
```

### Q14.

Descripcion: Todos los pedidos de compra de un proveedor en particular son transferidos a otro proveedor por un cambio de contrato.

```bash
MATCH (e:Empresa)-[pd:PEDIDO_DE_COMPRA]->(oldProvider:Proveedores {nombre: "TecnoHogar Ltd."})
MATCH (newProvider:Proveedores {ID: 2})
CREATE (e)-[newPd:PEDIDO_DE_COMPRA {
  id_compra: pd.id_compra,
  nombre_producto: pd.nombre_producto,
  cantidad: pd.cantidad,
  precio_unitario: pd.precio_unitario,
  precio_total: pd.precio_total,
  fecha_pedido: pd.fecha_pedido,
  fecha_recepcion: pd.fecha_recepcion,
  id_proveedor: newProvider.ID
}]->(newProvider)
DELETE pd
RETURN e, oldProvider, newProvider;
```

### Q15.

Descripcion: Eliminar todos los clientes que han realizado devoluciones.

```bash
MATCH (c:Cliente)-[d:DEVOLUCION]->(e:Empresa)
DETACH DELETE c;
```
