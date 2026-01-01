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

