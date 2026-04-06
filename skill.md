# Crear Página Web desde Carpeta Local

Guía paso a paso para ejecutar este portfolio Next.js en tu máquina local usando el código de referencia de este repositorio.

---

## Requisitos previos

- [Node.js](https://nodejs.org/) v16 o superior
- npm (incluido con Node.js) o yarn
- Cuenta en [Hygraph](https://hygraph.com/) (CMS GraphQL usado por este proyecto)
- Cuenta en [Google Analytics](https://analytics.google.com/) (opcional, para estadísticas)

---

## Pasos para ejecutar el proyecto localmente

### 1. Clonar el repositorio

```bash
git clone https://github.com/Alxmalaga/portfolio-1.git
cd portfolio-1
```

### 2. Instalar dependencias

```bash
npm install
# o con yarn:
yarn
```

### 3. Configurar variables de entorno

Copia el archivo de ejemplo y rellena los valores:

```bash
cp .env.example .env.local
```

Edita `.env.local` con tus credenciales:

```env
# Google Analytics (opcional)
NEXT_PUBLIC_GA_PROPERTY_ID=
NEXT_PUBLIC_GA_CLIENT_EMAIL=
NEXT_PUBLIC_GA_PRIVATE_KEY=

# Hygraph (obligatorio)
NEXT_PUBLIC_HYGRAPH_URL=
NEXT_PUBLIC_HYGRAPH_AUTH_TOKEN=
```

#### Obtener credenciales de Hygraph

1. Clona el proyecto Hygraph de referencia usando este enlace:
   👉 https://app.hygraph.com/clone/61c44d5d9a2640f39c7a617d3bc6cf60?name=Portfolio
2. En tu proyecto clonado ve a **Project Settings → Endpoints → Content API** para obtener `HYGRAPH_URL`.
3. En la misma sección de configuración, desplázate hasta **Permanent Auth Tokens** y crea un nuevo token para obtener `HYGRAPH_AUTH_TOKEN`.

### 4. Iniciar el servidor de desarrollo

```bash
npm run dev
# o con yarn:
yarn dev
```

Abre [http://localhost:3000](http://localhost:3000) en tu navegador para ver el resultado.

---

## Scripts disponibles

| Comando | Descripción |
|---------|-------------|
| `npm run dev` | Inicia el servidor de desarrollo en `localhost:3000` |
| `npm run build` | Genera la build de producción |
| `npm start` | Inicia el servidor en modo producción (requiere build previa) |
| `npm run lint` | Ejecuta el linter ESLint |

---

## Estructura del proyecto

```
portfolio-1/
├── components/        # Componentes React reutilizables
│   ├── aboutPage/
│   ├── resumePage/    # Sección de habilidades y experiencia
│   ├── worksPage/
│   └── ...
├── graphqlOperations/ # Queries GraphQL para Hygraph
├── hooks/             # Custom hooks de React
├── pages/             # Rutas de Next.js
├── public/            # Imágenes y archivos estáticos
├── styles/            # Estilos globales
├── data.ts            # Datos estáticos (menús, redes sociales, etc.)
├── types.d.ts         # Tipos TypeScript
└── .env.local         # Variables de entorno (no se sube al repo)
```

---

## Tecnologías utilizadas

- **[Next.js 12](https://nextjs.org/)** — Framework React con SSR/SSG
- **[TypeScript](https://www.typescriptlang.org/)** — Tipado estático
- **[Tailwind CSS](https://tailwindcss.com/)** — Estilos utilitarios
- **[Apollo Client](https://www.apollographql.com/docs/react/)** — Cliente GraphQL
- **[Hygraph](https://hygraph.com/)** — CMS headless con GraphQL
- **[Framer Motion](https://www.framer.com/motion/)** — Animaciones
- **[DaisyUI](https://daisyui.com/)** — Componentes UI sobre Tailwind

---

## Personalización

Para adaptar el portfolio a tus datos:

1. **Contenido dinámico** (experiencia, habilidades, proyectos): edítalo directamente en el panel de Hygraph.
2. **Datos estáticos** (menús, redes sociales, servicios): edita el archivo `data.ts` en la raíz del proyecto.
3. **Imágenes estáticas**: reemplaza los archivos en la carpeta `public/images/`.
4. **Tipografías y colores**: ajusta `tailwind.config.js` y `styles/globals.css`.

---

## Recursos adicionales

- 📝 Artículo del autor explicando la arquitectura:
  https://dev.to/arafat4693/how-i-built-my-fullstack-and-typesafe-portfolio-website-26ia
- 📚 [Documentación de Next.js](https://nextjs.org/docs)
- 🎨 [Documentación de Tailwind CSS](https://tailwindcss.com/docs)
- 🔗 [Documentación de Hygraph](https://hygraph.com/docs)
