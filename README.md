## 📦 Modelo de Base de Datos

### 👤 Empleado

Representa a los trabajadores del sistema, que pueden tener distintos roles.

- `user`: Relación uno a uno con el modelo `User` de Django para autenticación.
- `nombre`: Nombre completo del empleado.
- `dni`: Documento Nacional de Identidad (único).
- `correo`: Correo electrónico del empleado (único).
- `rol`: Rol del usuario (`admin` o `empleado`).
- `activo`: Estado activo/inactivo.
- `fecha_creacion`: Fecha de creación automática del registro.

---

### 📘 Producto

Representa los productos que vende la papelería.

- `nombre`: Nombre del producto.
- `precio`: Precio unitario.
- `stock`: Cantidad disponible en inventario.

---

### 🛠️ Servicio

Representa los servicios que ofrece la papelería (como impresiones, plastificados, etc.).

- `descripcion`: Descripción del servicio.
- `precio`: Precio del servicio.

---

### 🧾 Venta

Registro general de una venta realizada por un empleado.

- `empleado`: Empleado responsable de la venta.
- `fecha`: Fecha y hora en la que se realizó la venta.

---

### 🧺 DetalleVentaProducto

Detalle de los productos vendidos en una venta específica.

- `venta`: Referencia a la venta.
- `producto`: Producto vendido.
- `cantidad`: Número de unidades vendidas.

---

### 🧾 DetalleVentaServicio

Detalle de los servicios prestados en una venta específica.

- `venta`: Referencia a la venta.
- `servicio`: Servicio prestado.
- `detalle`: Información adicional sobre el servicio (opcional).

---

### 🗂️ Notas Técnicas

- Todas las tablas incluyen `Meta: db_table` para definir explícitamente el nombre de la tabla en la base de datos.
- El método `__str__()` en cada modelo ayuda a representar los datos de manera legible en el panel de administración de Django o en logs.
