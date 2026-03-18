# Funcionamiento del Código - TekoStore (Flet)

## 1. Modelo de Datos (Capa de Lógica)

El programa inicia definiendo una lista llamada `productos`, la cual contiene varios diccionarios.

Cada diccionario representa un producto con los siguientes atributos:

* `id`: identificador único
* `nombre`: nombre del producto
* `descripcion`: breve explicación
* `precio`: valor numérico
* `ruta_imagen`: nombre de la imagen almacenada en la carpeta `assets`

Esta estructura permite manejar la información de forma organizada y escalable.

---

## 2. Componente Reutilizable (Clase TarjetaProducto)

Se crea una clase personalizada llamada `TarjetaProducto`, la cual hereda de `ft.Container`.

### Herencia utilizada

```python
class TarjetaProducto(ft.Container):
```

Esto permite:

* Crear un componente visual propio
* Reutilizarlo múltiples veces
* Mantener el código limpio y modular

---

### Diseño del contenedor principal

Dentro de la clase se configuran propiedades visuales como:

* `width`: ancho fijo (uniformidad)
* `padding`: espacio interno
* `border_radius`: bordes redondeados
* `bgcolor`: color de fondo
* `shadow`: sombra para dar profundidad

Esto cumple con el diseño solicitado en el proyecto.

---

### Contenido interno (self.content)

Se utiliza un `Column` para organizar verticalmente los elementos:

#### Imagen

```python
ft.Image(src=producto["ruta_imagen"])
```

Carga la imagen desde la carpeta `assets`.

---

#### Textos

* Nombre → en negritas y tamaño mayor
* Descripción → más pequeña y en color tenue
* Precio → resaltado en color diferente (verde)

---

#### Barra de acciones

Se usa un `Row` para organizar horizontalmente:

* Botón de favorito (ícono)
* Botón "Agregar al carrito"

Estos botones son visuales (sin funcionalidad lógica).

---

## 3. Interfaz Principal (main)

La función `main(page: ft.Page)` es el punto de entrada de la aplicación.

### Configuración de la página

```python
page.title = "TekoStore"
page.bgcolor = ...
page.scroll = "auto"
```

Se define:

* Título de la ventana
* Color de fondo
* Scroll automático

---

### Generación de tarjetas

Se recorre la lista de productos:

```python
for producto in productos:
    tarjetas.append(TarjetaProducto(producto))
```

Esto crea una tarjeta por cada producto, reutilizando la clase creada.

---

### Layout adaptable

```python
ft.ResponsiveRow(controls=tarjetas)
```

Permite que las tarjetas:

* Se acomoden automáticamente
* Se adapten al tamaño de la ventana

---

### Encabezado

Se agrega un `Text` con el nombre de la tienda:

```python
"TechStore - Catálogo de Productos"
```

Esto cumple con la identidad visual del sistema.

---

## 4. Gestión de Recursos (Assets)

Las imágenes se almacenan en la carpeta:

```id="assets_path"
assets/
```

Y se enlazan al ejecutar la app:

```python
ft.app(target=main, assets_dir="assets")
```

Esto permite que Flet pueda acceder a los archivos correctamente.

---

## 5. Flujo General del Programa

1. Se define la lista de productos
2. Se crea la clase reutilizable (`TarjetaProducto`)
3. Se ejecuta la función `main`
4. Se generan las tarjetas dinámicamente
5. Se muestran en pantalla mediante un layout adaptable

---

## 6. Escalabilidad del Proyecto

El código está diseñado de forma modular, lo que permite:

* Cambiar fácilmente la fuente de datos (API o base de datos)
* Reutilizar el componente en otros proyectos
* Agregar funcionalidades sin modificar la estructura principal

---

## Conclusión

El programa implementa correctamente:

* Uso de herencia para crear componentes personalizados
* Separación entre datos y presentación
* Reutilización de código
* Diseño adaptable

Esto facilita el mantenimiento y evolución del sistema en futuras unidades.

---
