# Manual de Implantación de Odoo 19 con Docker Compose

Documento de implantación Odoo
---

## 1. Estructura del Proyecto y Despliegue

La pila de servicios se compone de tres contenedores aislados:
- **PostgreSQL 16:** Base de datos relacional.
- **Odoo 19 Community:** Sistema ERP principal.
- **pgAdmin 4:** Herramienta web de administración de la base de datos.

### Estructura de carpetas y ficheros
![Estructura del proyecto](Estructura.png)

---

### Configuración de despliegue y configuraciones
![Levantamiento] (levantamientoCompose.png)

---

## Credenciales modificadas según la guía del PDF:

![Credenciales](creedencialesEnv.png)


---


## Credenciales sin modificar

![CredencialesSinModificar](envExample.png)

## Gitignore

![Gitignore](gitignore.png)

## Bases de datos creada


Para la guía se crean dos bases de datos

En este apartado cree la demo de Odoo

![OdooDemo](odooDemo.png)

![accesoOdoo](accesoDemoOdoo.png)

---


## Ejercicio 1 Apartado 3

Bienes (sin inventario) Silla de Oficina Desactivado
![Silla](Silla.png)

Bienes (con inventario) Alfombrilla Activado

![alfombrilla](alfombrilla.png)

Servicio (montaje de muebles) Sin impuestos,  N/A

![montajeMueble](montajeMuebleServicio.png)

Combinación set para oficina IVA, rastrea el iventario según componentes

![setOficina](setOficina.png)

---

### Paso 4 Contactos

Contactos Compañía

![contactoCompañia](contactoCompañia.png)

Creación cliente/empresa

![creacionEmpresa](creacionEmpresa.png)

Creación de Hora Soporte y Libro Técnico

![horaSoporte](horaSoporte.png)

![libroTecnico](libroTecnico.png)

Creación pedido cliente

![pedidoEmpresa](pedidoEmpresa.png)

Incidencia, para poder confirmar hay que asignar un almacén

![almacenCreacion](almacenCreacion.png)

Creación Factura

![creacionFactura](creacionFactura.png)

![facturaPDF](facturaPDF.png)

Pago

![crearPago](crearPago.png)
![pagado](pagado.png)


Factura proveedor

![facturaProveedor](proveedoresFactura.png)

Pogramar actividad

![programarActividad](programarActividad.png)

![creado](creadoPro.png)

---

### Paso 5 Vistas, Filtros, Búsquedas

Ejercicio 3 Búsqueda guardada

![filtroFactura](filtroFacturacion.png)


## Modo Desarrollador

Parra ello solo añadimos al final de la url debug=1 para entrar al modo

![modoDesarrollador](modoDesarrollador.png)

Campo técnico 1: vat

![campoTecnico](campoTecnico.png)

Campo técnico 2: vat

![campoTecnico2](campoTecnico2.png)

Campo modelo Facturación: account.move

![modeloFacturacion](modeloFacturacion.png)

## 7. Registro de Incidencias y Soluciones

| Fecha | Síntoma / Error | Causa Probable | Solución Aplicada |
| :--- | :--- | :--- | :--- |
| 11/11/2026 | Operación no válida: Debe configurar un almacén en su pedido de venta. | Al vender productos físicos (bienes), Odoo requiere especificar un almacén de inventario para la salida del stock. | Se accedió a la pestaña *Otra Información* dentro del pedido y se seleccionó el almacén por defecto antes de confirmar. |
| 11/11/2026 | Fallo de permisos / `Access Denied` al crear la base de datos. | Master Password en `odoo.conf` no alineada con los volúmenes del contenedor. | Se corrigió el fichero `config/odoo.conf` y se reiniciaron los volúmenes Docker de forma limpia. |

---


## 8. Declaración de Uso de Inteligencia Artificial

- **Herramienta Utilizada Gemini**
- **Propósito: Asistencia en README.md, para estructurarlo bien, es decir, que sea legible**