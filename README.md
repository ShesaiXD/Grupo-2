
Proyecto: Galería Canina Interactiva

1. Resumen del Proyecto
   
El proyecto consiste en desarrollar una aplicación web simple y dinámica cuyo objetivo principal es mostrar imágenes de perros obtenidas desde una API pública. La aplicación ofrecerá una experiencia de usuario interactiva, permitiendo generar nuevas imágenes de forma aleatoria con solo un clic. Adicionalmente, se implementará una funcionalidad avanzada para que el usuario pueda filtrar las imágenes por razas específicas.

Este proyecto es un ejercicio práctico excelente para demostrar competencias fundamentales en el desarrollo web, incluyendo la manipulación del DOM, el consumo de APIs (AJAX/Fetch), y la creación de interfaces responsivas.

2. Objetivos Clave
   
Desarrollar una interfaz de usuario limpia y amigable: Crear una estructura HTML y CSS simple que presente un botón de acción claro y un espacio designado para la visualización de la imagen.

Implementar la lógica para consumir una API externa: Utilizar JavaScript (o un lenguaje de backend) para realizar solicitudes HTTP a una API de imágenes de perros (como la Dog CEO API) y procesar la respuesta.

Garantizar la interactividad y dinamismo: Lograr que la imagen en pantalla se actualice instantáneamente tras la acción del usuario (clic en el botón), sin necesidad de recargar la página completa.

Asegurar que la visualización sea adaptable (Responsive Design): La aplicación debe verse y funcionar correctamente en distintos tamaños de pantalla, desde dispositivos móviles hasta monitores de escritorio.

Extender la funcionalidad (Bonus): Añadir un selector (dropdown) que permita al usuario elegir una raza de perro específica para visualizar imágenes correspondientes a su selección.

3. Descripción de Funcionalidades
   
Funcionalidad Principal: Generador de Imágenes Aleatorias

Componentes de la Interfaz:

Un contenedor principal para la imagen.

Un botón con un texto claro como "Mostrar otro perro" o "Generar".


Flujo de Interacción:


Al cargar la página, se puede mostrar una imagen aleatoria inicial o un mensaje de bienvenida.

El usuario hace clic en el botón.

Se activa una función en JavaScript que realiza una solicitud fetch al endpoint de la API que devuelve una imagen aleatoria (ej: https://dog.ceo/api/breeds/image/random).

Una vez recibida la URL de la nueva imagen, el código actualiza el atributo src del elemento <img> en el HTML.

El usuario ve una nueva imagen sin que la página se recargue.

Funcionalidad Adicional (Bonus): Selección por Raza

Componentes de la Interfaz:

Un menú desplegable (<select>) que listará las diferentes razas de perros disponibles.
Este menú se puede poblar dinámicamente haciendo una llamada inicial a la API para obtener la lista de todas las razas (ej: https://dog.ceo/api/breeds/list/all).

Flujo de Interacción:

El usuario selecciona una raza del menú desplegable.

El evento de cambio (onchange) en el selector activa una función.

Esta función construye una URL de solicitud a la API específica para la raza seleccionada (ej: https://dog.ceo/api/breed/hound/images/random).

Se realiza la petición fetch y, al igual que en la funcionalidad principal, se actualiza la imagen en pantalla con el resultado.
4. Arquitectura y Tecnologías Propuestas
El proyecto se puede abordar con distintas arquitecturas, siendo la más directa la de "frontend puro".

Opción 1: JavaScript (Vanilla)

index.html: Estructura semántica del sitio (un título, el botón, el selector y el contenedor de la imagen).

style.css: Reglas de estilo para el layout, la apariencia de los elementos y las media queries para el diseño responsivo. Se usarán conceptos como Flexbox o Grid para centrar y organizar el contenido.

script.js: Lógica de la aplicación.

Selección de elementos del DOM (querySelector).

Manejo de eventos (addEventListener para el clic del botón y el cambio del selector).

Uso de la API Fetch para las solicitudes asíncronas (async/await para un código más limpio).

Manipulación del DOM para cambiar el src de la imagen.

Opción 2: Python (Flask) o PHP

En esta variante, el backend tendría un rol mínimo. Su principal función sería servir los archivos estáticos (HTML, CSS, JS).

El consumo de la API de perros seguiría realizándose desde el lado del cliente (JavaScript), ya que es más eficiente y no requiere un intermediario.

Este enfoque sería útil si en el futuro se quisiera añadir funcionalidades más complejas, como un sistema de usuarios, guardar imágenes favoritas en una base de datos, etc.
