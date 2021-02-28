##  Informe práctica 2 - Instalación y Configuración de Visual Studio Code

En esta práctica llevaremos a cabo la instalación y configuración del entorno de desarrollo que utilizaremos durante toda la asignatura, esto es, Visual Studio Code.

Visual Studio Code es un editor de código fuente desarrollado por Microsoft. Incluye soporte para la depuración, control integrado de Git, resaltado de sintaxis, finalización inteligente de código, fragmentos y refactorización de código. También es personalizable, por lo que los usuarios pueden cambiar el tema del editor, los atajos de teclado y las preferencias. Es gratuito y de código abierto. En esta practica instalaremos VS code en la maquina virtual, haremos algunas configuraciones iniciales y ademas instalaremos typescript y su compilador de cara a futuras practicas.

### Instalación y funcionalidad de Visual Studio Code

Para instalar VS code en la maquina local haremos uso de uno(o ambos si la instalacion no fuese correctamente) de los siguientes comandos:

```markdown
[usuario@iaas-dsi2 ~]$sudo apt install code
```
```markdown
[usuario@iaas-dsi2 ~]$sudo snap install code --classic
```
Después de introducir el comando, se iniciara el proceso de instalación y una vez completado, ya tendremos instalado VS code en nuestra maquina local.

### Configuración de Visual Studio Code para conectarse a una máquina remota por SSH

Habiendo instalado en el paso anterior VS code, en este paso lo que haremos sera instalar una extension de VS code que nos permita conectarnos por ssh a la maquina virtual. Para poder realizar este paso debemos ir a la parte de extensiones de VS code e instalar la denominada Remote - SSH. Una vez hecho esto, pulsamos ``` Ctrl + shift + p ``` para abrir el menu de comandos de VS code y acto seguido tecleamos ssh y pulsamos sobre ``` Connect to host ```. Dado que en la practica anterior ya hicimos toda la configuración del ssh en la practica anterior, en el desplegable ahora aparece el nombre de la maquina virtual, al seleccionarla entraremos en la maquina virtual usando VS code.

### Sesiones colaborativas con Visual Studio Live Share

Visual Studio Live Share permite colaborar en las tareas de desarrollo en tiempo real. Para poder utilizarlo, en primer lugar, debe buscar e instalar la extensión denominada Live Share Extension Pack, así como todas las extensiones recomendadas.
Si se diese el caso de que necesitamos una extension en la maquina virtual y no estuviese instalada, aun que este en la maquina local deberemos instalarla igualmente.

### Primer proyecto en TypeScript: “Hola Mundo”

Lo primero que haremos en este apartado es instalar el compilador de typescript, para ello usaremos npm:

```markdown
 [usuario@iaas-dsi2 ~]$npm install --global typescript
 ```

una vez hecho estp, abrimos una terminal en vscode, usando el desplegable de terminal o el comando ``` 1Ctrl + Shift + ` ``` y acto seguido crearemos el directorio donde haremos esta primera prueba. Una vez creado el directorio, iniciaremos npm usando el comando: 
```markdown 
[usuario@iaas-dsi2 ~]$npm init --yes
```
Una vez iniciado npm, creamos un fichero ``` tsconfig.json ``` en el que hira la configuración del compilador de typescript, al que le añadimos las siguientes lineas:
```markdown
{
  "compilerOptions": {
    "target": "ES2018",
    "outDir": "./dist",
    "rootDir": "./src",
    "module": "CommonJS"
  }
 ```

Con lo anterior realizado, ya estara configurado el compilador. Añadiremos un directorio src en nuestra carpeta del ejemplo, en la que añadiremos el codigo typescript, con lo que ya estara todo preparado para poder hacer nuestro primer programa typescript. Creamos un fichero llamado index.ts y le añadimos las siguientes lineas:

```typescript
let myString: string = "Hola Mundo";
console.log(myString);
```

guardamos el codigo y ejecutamos el compilador con el comando tsc, esto creara una carpeta llamada dist donde se guardara el codigo js del proyecto, si ahora hacemos
node  dist/index.js el codigo javascript se ejecutaría y aparecería un hola mundo por pantalla, que es lo que se programó en typescript.
