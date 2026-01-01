# PAC3 
## Creación del proyecto
### Descarga del bolierplate
Lo primero que hago es descargar el boilerplate y descomprimirlo en la carpeta PAC3.  
Instalo las dependencias con *npm install* ejecuto *npm run dev* para conmprobar que funciones bien. Todo ok. 
Los siguientes pasos: 

- Borro e body del boilerplae  
- Borro parte del contenido del  home.scss

### Git init y creación del repositorio en Github
- Creo el repositorio de Github llamado laiaia3  
- Creo git init con commit "Mi primer commit  Instalación del boilerplate"  y subo al repositorio
- git remote add origin https://github.com/drosellopa/laiaia3.git
- git branch -M main
- git push -u origin main

### Deploy en Netlify
Creo el proyecto iaia3 en Netlify cuya url es:  
[https://iaia3.netlify.app/](https://iaia3.netlify.app/)

## Instalación de Tailwind
Las instrucciones de la documentación oficial de [Tailwind](https://tailwindcss.com/docs/installation/framework-guides/parcel) que he encontrado están pensadas para css y no acaban de funcionar.  
Al principio intenté seguir al pie de la letra la estructura del boilerplate, usando @use como aparece en el archivo main.scss original, pero al instalar Tailwind me encontré con que Sass obliga a que todas las reglas @use vayan al principio del archivo y las sentencias de Tailwind tienen que ir antes para que PostCSS las procese correctamente.   
Después de muchos intentos, leer documentación, y ver varias intaslaciones de Tailwind sobre Parcel, vi que la única forma de que todo funcione sin errores de compilación era usar @import aunque Sass lo marca como obsoleto. Al final, opté por esta solución porque el proyecto, de esta forma funciona.  
Sé que no es lo más moderno, pero así es la única forma de que funcione.

Segundo commit "Instalación de Tailwind"

## Colores y fuentes

### Colores
Lo primero que hago es configurar los colores, para ello configuro el archivo tailwind.config.js añadiendo los colores principales que ya usaba: #FFC107 como primario y el #3F2E85 como secundario. De esta forma en el HTML puedo usar directamente clases como text-primary o bg-secondary.  

Pruebo que los colores funcionan bien: Pongo el h1 de la portada de color text-secondary y funciona.


### Fuente Roboto, Arial, Sans-serif
Para mantener la misma tipografía que en la pac2, que era Roboto añado el enlace a Google Fonts en el <head> de todas las páginas HTML y actualizo la configuración de Tailwind para que use Roboto en lugar de la suya.  

Compruebo la fuente y ya es Roboto.

## Incorporo el header de la PAC2 
Importo el header de la pac2 pero ya empiezo a usar el atomic css de Tailwind.  
Describo lo que hago en cada etiqueta y la toma de decisiones en la documenteció para que quede reflejado todo lo que hago:  
- Header: 
    * text-secondary: Color secundario para el texto
    * bg-white: Fondo blanco
    * shadow-md => La sombra que le quedaba mejor era la md (media o moderada)
- div: 
    * container: El contenido tendrá limitación de anchura ya que se ajusta el max-width de forma responsive 
    * mx-auto: Centrado con marging auto.
    * px-4: 1 rem de padding horizonta
    * py-3: 0.75 rem de padding vertical
    * flex: display: flex
    * items-center: align-items center
    * justify-between: un space-between en justify content

- Enlace el logo:
    * flex: creación del flex entre la imagen y el texto.
    * items-center: centra verticalmente el logo y el texto,.
    * gap-2: Espacio de separación de los hijos del flex, el gap.
    * font-bold: negrita.
    * text-xl: tamaño de fuente grande
    * no-underline: sin subrallado de las a
- Nav. 
    * hidden: Como no creo el menú  de barras del móvil lo hago desaparecer
    * sm:block: Hago aparecer el menú en pantallas superiores a 640px
- ul 
    * flex: flex horizontal de los items de menú.
    * gap-6: Espacio de separación de los hijos del flex, el gap. En este caso más grande 1.5 rem

- li a
    * hover:text-primary: al hacer un hover, cambia el color del secundario al primario.
    * transition: transición del hover.