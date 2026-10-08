# Guía React: primeros pasos

Proyecto de acompañamiento de la guía en PDF. Cada pestaña de la aplicación corresponde a un capítulo.

## Requisitos

- Node.js 20.19 o superior (o 22.12 en adelante). Revisa con `node -v`.

## Cómo ejecutarlo

```bash
npm install
npm run dev
```

Abre la dirección que muestra la terminal (normalmente http://localhost:5173).

## Scripts

| Comando | Qué hace |
|---|---|
| `npm run dev` | Servidor de desarrollo con recarga en caliente |
| `npm run build` | Versión de producción en `dist/` |
| `npm run preview` | Sirve `dist/` para probarla |
| `npm run lint` | Revisa el código con oxlint |
| `npm run repaso` | Ejecuta el repaso de JavaScript en la terminal |
| `npm test` | Corre las pruebas unitarias (Karma + Jasmine) |
| `npm run test:watch` | Pruebas en modo continuo |

## Estructura

```
repaso-js/                 repaso de JavaScript moderno (npm run repaso)
docs/                      guía en PDF y su fuente LaTeX
src/
  main.jsx                 punto de entrada: createRoot + render
  App.jsx                  navegación entre secciones
  index.css                variables CSS y reglas base
  styles/utilidades.css    clases compartidas (.caja, .fila, .alerta)
  logica/                  funciones puras y sus pruebas (*.spec.js)
  components/
    Ejemplo.jsx            marco que muestra título y archivo de cada ejemplo
    basicos/               ejemplos principales de cada capítulo
    jsx/ props/ estado/ eventos/ condicional/ listas/ formularios/ efectos/
                           ejemplos adicionales por tema
    render/DemoRender.jsx  cuándo se vuelve a renderizar un componente
    tareas/                proyecto integrador (lista de tareas)
```

Cada componente con estilos propios tiene su archivo `.css` al lado, importado desde el `.jsx`. `Buscador` usa un CSS Module (`Buscador.module.css`) para mostrar la diferencia.

Cada ejemplo en pantalla indica la ruta de su archivo. Ábrelo, cámbialo y guarda: el navegador se actualiza solo.

## Pruebas

`npm test` levanta Karma, abre Chrome sin interfaz y ejecuta las pruebas de `src/logica/*.spec.js` y `src/components/basicos/Contador.spec.jsx`. Se necesita Chrome instalado; si Karma no lo encuentra, define la variable `CHROME_BIN` con su ruta. La configuración está en `karma.conf.cjs`.

La guía en PDF y su fuente LaTeX están en `docs/`.

La sección "useEffect" consume https://jsonplaceholder.typicode.com, por lo que necesita conexión a internet.
