## Despliegue en Web del Proyecto

Para publicar la aplicación en la web, se realizó un proceso de conversión y despliegue utilizando herramientas de desarrollo web modernas.

### 1. Instalación de herramientas necesarias

Primero, se instaló la herramienta de línea de comandos de Netlify (Netlify CLI) mediante el uso de Node.js y npm:

```bash
npm install -g netlify-cli
```

Esto permitió gestionar el despliegue directamente desde la terminal.

---

### 2. Preparación del proyecto

Debido a que Flet es un framework que genera interfaces interactivas, se ejecutó la aplicación en modo web para generar los archivos necesarios:

```bash
flet run --web
```

Este comando permite visualizar la aplicación en el navegador y preparar los recursos para su publicación.

---

### 3. Generación de archivos estáticos

Posteriormente, se generó una versión exportable del proyecto, la cual contiene archivos HTML, CSS y JavaScript necesarios para su ejecución en la web:

```bash
flet build web
```

Esto creó una carpeta con los archivos listos para ser desplegados.

---

### 4. Despliegue en Netlify

Una vez generados los archivos, se utilizó Netlify para publicar el sitio:

```bash
netlify deploy
```

Durante este proceso:

* Se seleccionó la carpeta generada por Flet (build/web)
* Se configuró como sitio público
* Se obtuvo una URL de acceso en línea

Finalmente, para hacer el sitio permanente:

```bash
netlify deploy --prod
```

---

### 5. Resultado del despliegue

El proyecto quedó disponible en línea mediante un enlace público, permitiendo acceder al catálogo de productos desde cualquier navegador sin necesidad de instalar el entorno de desarrollo.

---

### Conclusión

El uso de herramientas como Flet y Netlify permitió transformar una aplicación local en una aplicación web accesible, demostrando la capacidad de desplegar interfaces modernas utilizando tecnologías actuales.

---
