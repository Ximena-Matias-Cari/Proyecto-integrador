# Proyecto-integrador
Tienda en línea

# 🛒 TekoStore - Catálogo de Productos con Flet

## Descripción

Este proyecto consiste en el desarrollo de una aplicación de escritorio utilizando Python y el framework Flet. La aplicación muestra un catálogo de productos tecnológicos mediante tarjetas visuales reutilizables.

El objetivo es aplicar conceptos de interfaces gráficas, reutilización de componentes y organización modular del código.

---

## Estructura del Proyecto

```id="e8wz8g"
tienda-flet/
│
├── Tienda.py
│
└── assets/
    ├── laptop.jpg
    ├── audifonos.jpg
    ├── celular.jpg
    ├── tablet.jpg
    └── reloj.jpg
```

### Descripción

* **Tienda.py** → Archivo principal con la lógica de la aplicación
* **assets/** → Carpeta donde se almacenan las imágenes de los productos

---

## Tecnologías utilizadas

* Python
* Flet

---

## Funcionamiento

### Modelo de datos

Se utiliza una lista de diccionarios para almacenar los productos:

```python id="lq1g0u"
productos = [
    {
        "id": 1,
        "nombre": "Laptop Gamer",
        "descripcion": "Laptop potente para videojuegos",
        "precio": 25000,
        "ruta_imagen": "laptop.jpg"
    }
]
```

---

### Componente reutilizable

Se crea una clase llamada `TarjetaProducto` que hereda de `Container`.

Este componente representa visualmente cada producto e incluye:

* Imagen
* Nombre
* Descripción
* Precio
* Botones de acción

---

### Generación dinámica

Las tarjetas se generan automáticamente recorriendo la lista de productos:

```python id="e4n7mk"
for producto in productos:
    tarjetas.append(TarjetaProducto(producto))
```

---

### Diseño adaptable

Se utiliza:

```python id="qghhfl"
ft.ResponsiveRow(controls=tarjetas)
```

Esto permite que los productos se acomoden automáticamente según el tamaño de la ventana.

---

### Manejo de imágenes

Las imágenes se almacenan en la carpeta `assets` y se cargan usando:

```python id="l2a3in"
ft.Image(src=producto["ruta_imagen"])
```

---

## Ejecución

1. Instalar Flet:

```id="2c9u9v"
pip install flet
```

2. Ejecutar la aplicación:

```id="iytn5o"
python Tienda.py
```

---

## Despliegue

El proyecto fue desplegado en Netlify mediante una página informativa, ya que Flet no se ejecuta directamente en entornos web estáticos.

---

## Vista previa

Aquí se muestra la interfaz de la aplicación:

* Catálogo de productos
* Tarjetas con diseño uniforme
* Botones de interacción

---

## Conclusión

Este proyecto permitió:

* Comprender el uso de Flet para interfaces gráficas
* Implementar componentes reutilizables
* Organizar el código de forma modular
* Manejar recursos externos como imágenes

Además, el diseño permite escalar el proyecto para futuras mejoras, como conexión a bases de datos o APIs.

---
