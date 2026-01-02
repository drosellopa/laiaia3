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
- Creo git init con **commit "Mi primer commit  Instalación del boilerplate"**  y subo al repositorio
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

**Segundo commit "Instalación de Tailwind"**

## Colores y fuentes

### Colores
Lo primero que hago es configurar los colores, para ello configuro el archivo tailwind.config.js añadiendo los colores principales que ya usaba: #FFC107 como primario y el #3F2E85 como secundario. De esta forma en el HTML puedo usar directamente clases como text-primary o bg-secondary.  

Pruebo que los colores funcionan bien: Pongo el h1 de la portada de color text-secondary y funciona.


### Fuente Roboto, Arial, Sans-serif
Para mantener la misma tipografía que en la pac2, que era Roboto añado el enlace a Google Fonts en el <head> de todas las páginas HTML y actualizo la configuración de Tailwind para que use Roboto en lugar de la suya.  

Compruebo la fuente y ya es Roboto.

## Incorporo el header de la PAC2 
Importo el header de la pac2 pero ya empiezo a usar el atomic css de Tailwind.  
Describo lo que hago en cada etiqueta y la toma de decisiones en la documenteción para que quede reflejado todo lo que hago:  
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

 **Tercer commit -m "Creado el header y nav con los estilos de tailwind"**

 ## Incorporo el footer de la PAC2 
 Para poder utilizar los iconos de fotnawesome, he puesto el link link a *../node_modules/@fortawesome/fontawesome-free/css/all.min.css* en el header.
 - footer  
  * bg-gray-200: Fondo gris claro 
  * py-6: Padding arriba y abajo  

- div   
  * container: Limita el ancho máximo del contenido de forma responsive  
  * mx-auto: Centra el contenedor horizontalmente con márgenes auto  
  * px-4: Padding horizontal de 1rem (16px)   
  * flex: flex al contenedor 
  * flex-col: flex columna para que los iconos se vean arriba y el texto del footer abajo
  * items-center: alinea al centro
  * gap-4: separación de hijos del flex, el gap. 

- div de iconos
  * flex: flex en los iconos 
  * gap-4: separación de hijos
  * text-xl: tamaño grande de los iconos  

- Iconos  
  * hover:text-primary: Al pasar el ratón cambia del azul al amarillo 
  * transition: Se añade transición
  * cursor-pointer: Cambia el cursor a pointer   

- div texto legal 
  * text-gray-600: Color gris  
  * text-sm: tamaño pequeño

**Cuarto commit -m "Creado el footer con los estilos de tailwind. Importado FontAwesome"**

## Página contacte.html
He pegado todo el HTML de la pec2 de la página de contacto. He quitado todas las clases y he puesto las clases de Tailwind, se parece bastante al original.  

Las clases:

- main
   * max-w-2xl: He limitado el main para que no sea tan grande, max-width de 672px, para el formulario
  * mx-auto: Centra el contenedor horizontalmente con márgenes auto
  * px-4: Padding horizontal de 1rem (16px)
  * py-10: padding 40px arriba y abajo
- section#contact-form
  * text-2xl: Título grande
  * font-bold: Negrita
  * text-secondary: Texto secundario
  * mb-6: margin-bottom
- Form
  * space-y-5: Margin vertical entre cada campo del formulario
- label
  * block: display: block
  * text-gray-700: Color gris oscuro
  * font-medium: Grueso de 500 un poco más ancho que el normal de 400
  * mb-1: Margen inferior  para separar el label del input
- input y textarea
  * w-full: Ancho 100%
  * px-4, py-2: paddings
  * border-gray-300: Borde gris claro
  * rounded-md: Border radius
  * focus:outline-none: Outline eliminado
  * focus:ring-2: outline de tailwind del input 2px
  * focus:ring-secondary: color del ring secondary
  * focus:border-transparent: Hace que el borde normal se vuelva transparente para que se vea el ring 
- Mensajes de error 
  * mt-1: MArgin top
  * text-sm: Fuente pequeña
  * text-red-600: Color rojo
- Submit
  * px-6, p-2: paddings
  * bg-secondary: Fondo violeta
  * text-white: Texto blanco
  * font-medium: Font weight regular
  * rounded-md: Bordes redondeados
  * hover:bg-primary: Al pasar el ratón, el fondo cambia a amarillo 
  * hover:text-secondary: El texto cambia a violeta al hacer hover
  * transition: Transición al hacer hover.

  **Quinto commit -m "Acabados estilos de contacte.html"**

  ## Página jornades2025.html
  Creo que he conseguido que se parezca bastante a la de la pac2.
  Esta página tiene varias secciones etiquetadas con los id:  
  - banner
  - intro 
  - activitats
  - homenatge
  Cada una de ellas está tratada de una forma distinta, vamos a analizarlas
  ### La sección Banner
  A la sección banner no le he puesto ancho máximo pero si he jugado con el padding vertical y el tamaño del título para que sea responsive.
  - **py-10 sm:py-20 md:py-[100px] px-5**: El contenedor banner tiene un padding vertical de pequeño en móviles (tailwind es mobilefirst), el doble en pantallas pequeñas (sm), 100px en medianas o más (md), y siempre 20px de padding horizontal. 
  - **text-3xl md:text-4xl lg:text-5xl**: En tamño del texto va creciendo también en función del dispositivo.

  La imagen de fondo es lo único que he puesto en estilos por lo que los he incrustado con un style por no crear un externo. Creo que por un selector solo no es necesario crear un css externo.

  ### La sección intro
  Esta sección tiene un flex simple con un gap entre el título y los párrafos. También tiene como las siguientes secciones un ancho máximo. Todo esto lo refleja su clase: **flex flex-col md:flex-row gap-10 max-w-6xl mx-auto px-4**

  ### La sección _activitats_ 
  Esta sección ha costado más, he probado con un grid y ha quedado muy bien. Los iconos los he posicionado de forma absoluta con respecto a su li, para ello he utilizado las clases **absolute** y **relative**

  ### La sección _homenatge_
  Lo destacable de esta sección es el cite al que le he puesto un ancho máximo de 500px (max-w-[500px] ) y un lineheight, que no había usado hasta ahora de 2.5rem (leading-10).
  Lo demás es bastante común.


  ## index.html
  Como pone el enunciado, he realizado un index bastante sencillo, con una breve introducción y un par de enlaces a las páginas anteriores.

**Sexto commit -m "Creado jornades2025.html y index.html"** 


## @apply
En ocasiones hay que repetir muchas veces las mismas clases en los mismos elementos y hace pensar que el atomic-css no es una buena opción pero con @aplly se solucionan esos problemas. Simplemente pones una clase en el elemento correspondiente y le aplicas todos estos estilos repetitivos. Yo lo he hecho en:
- Iconos de lista en jornades2025.html donde se repetía muchas veces en la imagen del icono esta clase: class="absolute left-0 top-0.5 w-8 h-8"; Lo que he hecho es poner una clase  solo en esa imagen: class="activitats_icon" y en un estilo incrustado (de momento para probar y como solo está en esta página ya sería suficiente), he puesto:
.activitats_icon {  
      @apply absolute left-0 top-0.5 w-8 h-8;  
}  
- H3 de #activitats: En esta ocación pasa algo parecido, se repite 3 veces la misma configuración por lo que, en lugar de crear una clase nueva he "atacado" a #activitats h3 y le he aplicado el text-lg font-semibold text-secondary mb-2 que tenía. He aprovechado el mismo estilo incrustado

- input y textarea: En esta ocación era más que necesario un @apply, he atadado a los inputs y al texarea y le he aplicado la interminable lista de clases de css atómico => w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-secondary focus:border-transparent    

**Séptimo commit -m "creado los 3 apply en css incrustado"**

## Error Envío formulario en Netlyfy
He congigurado la página gracies.html para que se vea cuando se envía un formulario. Desde el build local se ve sin problemas al enviar el formulario pero desde Netlify no. He realizado varios commits para colucionarlo sin éxito.  
Al no tener JS, los errores del formulario se siguen viendo. Lo dejo así porque esta pack no va de este tema.  

##  3 componentes con posthtml-include
Voy a extraer:
- **El formulario de contacto** por si se quiere reusar en otro lugar de la web. Para ello creo un form.html en views y hago el include en la página de contacto.

- **El Nav**: He reutilizdo el nav, con el nombre nav.html, para mostrarlo tanto en el head como en la página de inicio, así lo tenemos centralzado. 

- **Las redes sociales**: He credo social.html para incluirlo en el footer, pero serí bueno también incluirlo en otras páginas.



