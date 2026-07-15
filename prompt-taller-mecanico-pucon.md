# Rol

Actúa como un Desarrollador Fullstack Senior especializado en Astro, Tailwind CSS y Vercel.

Debes generar un proyecto listo para producción, utilizando buenas prácticas de arquitectura, rendimiento, accesibilidad (WCAG AA), SEO y mantenibilidad.

---

# Objetivo

Desarrollar un sitio web corporativo para un taller mecánico ubicado en la ciudad de Pucón, Chile.

El objetivo del sitio es presentar los servicios, generar confianza y facilitar el contacto de nuevos clientes.

---

# Stack Tecnológico

- Astro (última versión estable)
- TypeScript
- Tailwind CSS
- Vercel (Deployment)
- ESLint
- Prettier

No utilizar React, Vue, Svelte ni otros frameworks de UI.

---

# Arquitectura

Adoptar una **arquitectura modular** basada en dominios/funcionalidades, donde cada módulo sea una unidad autocontenida, desacoplada y reutilizable.

Principios:

- **Alta cohesión**: cada módulo agrupa todo lo relacionado a una funcionalidad (componentes, tipos, datos, estilos, lógica).
- **Bajo acoplamiento**: los módulos se comunican entre sí únicamente mediante su API pública expuesta en un `index.ts` (barrel file).
- **Encapsulación**: los detalles internos viven dentro del módulo y no se importan directamente desde fuera.
- **Composable**: cualquier módulo debe poder moverse, eliminarse o reutilizarse sin romper el resto del proyecto.
- **Separation of concerns**: distinguir claramente UI, lógica de negocio, datos y configuración.

Estructura de carpetas esperada:

```
src/
├── modules/                  # Módulos por dominio/funcionalidad
│   ├── hero/                 # Sección Hero
│   │   ├── components/
│   │   ├── types/
│   │   ├── data/
│   │   └── index.ts          # API pública del módulo
│   ├── about/                # Sobre Nosotros
│   ├── services/             # Servicios
│   ├── why-us/               # ¿Por qué elegirnos?
│   ├── testimonials/         # Testimonios
│   ├── gallery/              # Galería
│   └── contact/              # Contacto
│
├── shared/                   # Elementos compartidos entre módulos
│   ├── components/           # Button, Section, Container, etc.
│   ├── layouts/              # Layout principal
│   ├── ui/                   # Átomos reutilizables
│   └── index.ts
│
├── lib/                      # Utilidades y clientes externos
│   ├── seo.ts
│   └── env.ts
│
├── config/                   # Configuración global (sitio, navegación, constantes)
│
├── assets/                   # Recursos estáticos procesados por Astro
│
├── styles/                   # Estilos globales
│
└── pages/                    # Rutas (composición de módulos)

public/
```

Reglas:

- Ningún módulo debe importar directamente desde la carpeta interna de otro módulo; solo desde su `index.ts`.
- Las páginas (`pages/`) solo orquestan módulos, no contienen lógica de UI ni datos.
- Toda la información del sitio (servicios, testimonios, datos de contacto) vive dentro de cada módulo en `data/` como fuente única de verdad.
- Los tipos e interfaces se definen dentro del módulo al que pertenecen.

---

# Diseño

Inspiración:

- Diseño moderno
- Minimalista
- Profesional
- Responsive
- Excelente experiencia móvil

Paleta sugerida:

- Negro
- Gris oscuro
- Blanco
- Azul mecánico (#2563EB)
- Naranja para llamados a la acción (#F97316)

Paleta alternativa sugerida (azul/teal oscuro):

- `#140e12` — fondo principal (casi negro con tinte cálido)
- `#131f2a` — fondo secundario (azul muy oscuro)
- `#103749` — superficie de apoyo
- `#0d516b` — acento intermedio
- `#0a7191` — CTA / acento fuerte

Tipografía:

- Inter
- Color de fuente: `#FFFFFF` (blanco) sobre fondos oscuros de la paleta

Animaciones:

- Transiciones suaves
- Hover elegantes
- Aparición al hacer scroll
- Sin excesos

---

# Contenido

Empresa:

"Taller Mecánico Pucón"

Ciudad:

Pucón, Chile

Crear contenido completamente en español.

---

# Servicios principales

## Mantención Preventiva

- Cambio de aceite
- Filtros
- Revisión general
- Diagnóstico

---

## Diagnóstico Computarizado

- Scanner automotriz
- Lectura de errores
- Sistemas electrónicos
- Sensores

---

## Reparación General

- Frenos
- Suspensión
- Motor
- Embrague

Cada servicio debe tener:

- Imagen
- Descripción
- Beneficios
- Botón de contacto

---

# Secciones

## Hero

Título llamativo

Subtítulo

Botón:

"Solicitar Presupuesto"

Imagen principal

---

## Sobre Nosotros

Breve historia

Experiencia

Compromiso

---

## Servicios

Tarjetas modernas

Iconos

Imágenes

CTA

---

## ¿Por qué elegirnos?

- Más de 10 años de experiencia
- Atención personalizada
- Repuestos de calidad
- Diagnóstico profesional
- Garantía en los trabajos

---

## Testimonios

Crear tres testimonios ficticios.

---

## Galería

Utilizar imágenes de ejemplo desde Unsplash.

No descargarlas.

Usar únicamente URLs públicas (formato `https://images.unsplash.com/...`).

Todas las imágenes del sitio deben provenir de URLs públicas de Unsplash como fuente única.

---

## Contacto

Formulario con:

- Nombre
- Correo
- Teléfono
- Mensaje

Mapa embebido de Google Maps centrado en Pucón.

Información:

Dirección ficticia

Horario

Teléfono

WhatsApp

---

# SEO

Generar:

- title
- description
- keywords
- Open Graph
- Twitter Cards
- sitemap
- robots.txt

Usar Astro SEO.

---

# Rendimiento

Optimizar:

- Lazy Loading
- Imágenes responsivas
- Lighthouse >95
- Core Web Vitals

---

---

# Variables de entorno

Crear también:

PUBLIC_SITE_URL=http://localhost:4321

PUBLIC_GOOGLE_MAPS_API_KEY=

PUBLIC_CONTACT_EMAIL=

PUBLIC_PHONE=

PUBLIC_WHATSAPP=

---

# Deploy

Preparar el proyecto para desplegar en Vercel.

Incluir:

vercel.json

Configuración necesaria para Astro.

---

# Calidad del código

Utilizar:

- Componentes reutilizables
- TypeScript estricto
- Props tipadas
- Código documentado
- Nombres descriptivos
- Sin duplicación de código
- Módulos autocontenidos con API pública explícita (`index.ts` por módulo)
- Sin dependencias circulares entre módulos
- Datos, tipos y UI co-localizados dentro de cada módulo

---

# Accesibilidad

Cumplir:

- HTML semántico
- Contraste adecuado
- Labels
- Navegación por teclado
- aria-label cuando corresponda

---

# Entregables

Generar:

- Proyecto completo
- README.md
- .env.example
- package.json
- Estructura de carpetas modular (`src/modules/*`, `src/shared/*`, `src/lib/*`, `src/config/*`)
- Un `index.ts` (barrel file) por cada módulo exportando únicamente su API pública
- Componentes reutilizables
- Layout principal
- Página de inicio completamente funcional que orqueste los módulos
- Configuración lista para desplegar en Vercel

No omitir ningún archivo necesario para ejecutar el proyecto.