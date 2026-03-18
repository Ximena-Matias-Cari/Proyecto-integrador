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

## Programa funcionando

<img width="1918" height="1032" alt="image" src="https://github.com/user-attachments/assets/0b69fa6e-28af-4d47-95e0-e5e1f9c9d751" />

<img width="1918" height="912" alt="image" src="https://github.com/user-attachments/assets/90ee60dd-55a7-426c-998e-5663038061d8" />

<img width="1913" height="401" alt="image" src="https://github.com/user-attachments/assets/69e126bd-6124-481b-a402-250f529f84f5" />


## Carpeta con imagenes



<img width="1001" height="452" alt="image" src="https://github.com/user-attachments/assets/00439613-bd16-4e8c-b625-6becfebbefd6" />


## Gestión de Recursos: Configuración del Directorio `assets`

Para permitir que la aplicación reconozca y cargue imágenes locales, se utilizó un directorio llamado `assets`, el cual contiene todos los recursos gráficos del proyecto.

### Estructura del directorio

Se creó una carpeta llamada `assets` en el mismo nivel que el archivo principal del programa (`Tienda.py`):

```
proyecto/
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

Esta organización permite mantener separados los recursos visuales del código fuente, facilitando su administración.

---

### Configuración en el código

Para que el framework reconozca automáticamente las imágenes, se utilizó el parámetro `assets_dir` al ejecutar la aplicación:

```python
ft.app(target=main, assets_dir="assets")
```

Este parámetro indica a Flet que todos los archivos estáticos (como imágenes) se encuentran dentro de la carpeta `assets`.

---

### Uso de imágenes en el código

Dentro del programa, las imágenes se referencian únicamente por su nombre, sin necesidad de especificar la ruta completa:

```python
ft.Image(src=producto["ruta_imagen"])
```

Y en la estructura de datos:

```python
"ruta_imagen": "laptop.jpg"
```

Gracias a la configuración previa, Flet busca automáticamente el archivo dentro del directorio `assets`.

---

### Consideraciones importantes

* La carpeta debe llamarse exactamente `assets` (en minúsculas).
* Debe estar ubicada en el mismo nivel que el archivo principal.
* Los nombres de las imágenes deben coincidir exactamente con los definidos en el código.
* Se recomienda utilizar formatos compatibles como `.jpg` o `.png`.

---

### Resultado

Con esta configuración, la aplicación puede cargar y mostrar correctamente las imágenes de cada producto dentro de las tarjetas, cumpliendo con los requisitos del proyecto.

---

## Conclusión

Este proyecto permitió:

* Comprender el uso de Flet para interfaces gráficas
* Implementar componentes reutilizables
* Organizar el código de forma modular
* Manejar recursos externos como imágenes

Además, el diseño permite escalar el proyecto para futuras mejoras, como conexión a bases de datos o APIs.

---
