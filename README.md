___

# Introducción

En este proyecto veremos todo lo indispensable para empezar un proyecto con `Vite` y `TypeScript`. Veremos lo más esencial y un ejemplo práctico simple.

Este proyecto también contiene el componente `HelloUser.vue` que en principio mostrará un mensaje genérico que cambiará luego de apretar el botón.

---

# Preparación

Lo primero sería descargar `npm` o actualizarlo a su versión más nueva. En cualquier distribución de Linux usaremos el siguiente comando:

```sh
sudo apt install npm
```

Para Windows, tendremos que dirigirnos al sitio oficial de [Node.js](https://nodejs.org/es), luego tendremos que descargar la versión **LTS** y ejecutar el instalador `.msi` y si vamos al **CMD** y ejecutamos el siguiente comando:

```sh
node -v
```

Veremos la versión de `npm` que tenemos.

---

# Crear un proyecto

Para crear un proyecto tendremos que ejecutar este comando:

```sh
 npm create vite@latest
```

Nos preguntará por los siguientes campos:

- Nombre del proyecto.
- Seleccionar framework.
- Seleccionar la variante..
- Instalar con `npm` e iniciar.

Lo iniciará automáticamente, pero en caso de querer iniciarlo en otro momento ejecutaremos este comando:

```sh
npm run dev
```

Una vez se nos ha creado el proyecto tendrá esta estructura:

<img width="237" height="827" alt="image" src="https://github.com/user-attachments/assets/69cfe47e-721c-4847-8aa4-0e2e92dd8e16" />


Esta es la estructura predeterminada de **Vue**.

---

