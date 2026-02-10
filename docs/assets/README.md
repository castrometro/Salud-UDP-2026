# Assets Extraídos de SALUD-UDP

Este directorio contiene componentes clave extraídos del proyecto original SALUD-UDP para ser reutilizados en la versión mejorada 2026.

## 📁 Estructura de Archivos

```
docs/assets/
├── auth/                      # Componentes de autenticación
│   ├── LoginPage.tsx         # Página principal de login
│   ├── LoginForm.tsx         # Formulario de login
│   ├── AuthContext.tsx       # Context API para manejo de autenticación
│   └── types/                # Definiciones de tipos TypeScript
│       ├── auth.ts
│       ├── fichas.ts
│       ├── pacientes.ts
│       └── usuarios.ts
├── home/                      # Componentes de página de inicio
│   ├── HomePage.tsx          # Página de inicio principal
│   └── components/           # Componentes compartidos
│       ├── Header.tsx        # Encabezado de la aplicación
│       ├── Footer.tsx        # Pie de página
│       ├── Layout.tsx        # Layout principal
│       └── Card.tsx          # Componente de tarjeta reutilizable
├── fonts/                     # Fuentes personalizadas
│   ├── WorkSans-Regular.ttf
│   ├── WorkSans-Medium.ttf
│   ├── WorkSans-SemiBold.ttf
│   ├── ABCArizonaFlare-Light.otf
│   ├── ABCArizonaFlare-Medium.otf
│   └── fonts.css             # Configuración @font-face
├── services/                  # Servicios y utilidades
│   ├── api.ts                # Cliente Axios configurado
│   └── utils/                # Funciones utilitarias
│       ├── formatRut.ts      # Formateo de RUT chileno
│       └── validateRut.ts    # Validación de RUT chileno
└── README.md                  # Este archivo
```

## 🛠️ Stack Tecnológico Original

### Frontend
- **Framework**: React 18.2.0
- **Lenguaje**: TypeScript 5.2.2
- **Build Tool**: Vite 5.1.4
- **Estilos**: TailwindCSS 3.4.1
- **Routing**: React Router DOM 6.30.0
- **HTTP Client**: Axios 1.13.0
- **Iconos**: Lucide React 0.330.0

### Dependencias Clave
```json
{
  "react": "^18.2.0",
  "react-dom": "^18.2.0",
  "react-router-dom": "^6.30.0",
  "typescript": "^5.2.2",
  "axios": "^1.13.0",
  "lucide-react": "^0.330.0",
  "clsx": "^2.1.0",
  "tailwind-merge": "^2.2.1"
}
```

## 📦 Descripción de Componentes

### Auth
- **LoginPage.tsx**: Página completa de login con diseño responsivo
- **LoginForm.tsx**: Formulario de login con validación de RUT y contraseña
- **AuthContext.tsx**: Context para manejo global del estado de autenticación (login, logout, estado de usuario)
- **types/**: Definiciones TypeScript para entidades del sistema (usuarios, pacientes, fichas)

### Home
- **HomePage.tsx**: Página de inicio con información institucional y enlaces principales
- **Header.tsx**: Encabezado con logo, navegación y estado de sesión
- **Footer.tsx**: Pie de página con información institucional
- **Layout.tsx**: Layout wrapper para estructura consistente de páginas
- **Card.tsx**: Componente reutilizable para tarjetas de información

### Fonts
- **WorkSans**: Familia tipográfica principal (Regular, Medium, SemiBold)
- **ABCArizonaFlare**: Tipografía decorativa para títulos (Light, Medium)
- **fonts.css**: Configuración de fuentes con `@font-face`

### Services
- **api.ts**: Cliente Axios configurado con:
  - Base URL del backend
  - Interceptores para tokens JWT
  - Manejo de errores
  - Headers predeterminados
- **utils/**: Utilidades para validación y formateo de RUT chileno

## 🔗 Dependencias entre Componentes

### LoginPage/LoginForm
- ✅ Requiere: `AuthContext` para manejo de estado
- ✅ Requiere: `api.ts` para llamadas al backend
- ✅ Requiere: `validateRut` para validación de input
- ✅ Requiere: React Router DOM para navegación

### HomePage
- ✅ Requiere: `Header`, `Footer`, `Layout` para estructura
- ✅ Requiere: TailwindCSS para estilos
- ✅ Requiere: React Router DOM para navegación

### AuthContext
- ✅ Requiere: `api.ts` para autenticación
- ✅ Requiere: `types/auth.ts` para tipos

## 🚀 Cómo Integrar en Proyecto Nuevo

### 1. Instalar Dependencias Base
```bash
npm install react react-dom react-router-dom
npm install axios lucide-react clsx tailwind-merge
npm install -D typescript @types/react @types/react-dom
npm install -D tailwindcss postcss autoprefixer
```

### 2. Configurar Fuentes
1. Copiar carpeta `fonts/` a `src/assets/fonts/`
2. Importar `fonts.css` en tu archivo principal (ej: `main.tsx` o `App.tsx`)
3. Configurar TailwindCSS para usar las fuentes

### 3. Integrar Componentes
1. Copiar carpetas `auth/`, `home/`, `services/` a `src/`
2. Ajustar rutas de importación según tu estructura
3. Configurar rutas en React Router
4. Configurar variables de entorno para API URLs

### 4. Variables de Entorno Necesarias
```env
VITE_API_URL=http://localhost:8000  # URL del backend
```

## 📝 Notas Importantes

- Los componentes están diseñados para trabajar con un backend Django REST Framework
- La autenticación usa JWT (JSON Web Tokens)
- El sistema incluye validación específica para RUT chileno
- Los estilos dependen completamente de TailwindCSS
- Los tipos TypeScript están fuertemente acoplados al esquema del backend original

## 🔄 Próximos Pasos

- [ ] Decidir si mantener el stack tecnológico o migrar
- [ ] Adaptar componentes para hacerlos más genéricos si es necesario
- [ ] Definir nueva arquitectura del proyecto 2026
- [ ] Implementar mejoras sobre los componentes base
- [ ] Configurar nuevo backend (si aplica)

## 📌 Origen

Extraído de: **SALUD-UDP** (Sistema de Gestión de Fichas Clínicas)
- Repositorio: `C:\Repos\SALUD-UDP`
- Fecha de extracción: 10 de febrero de 2026
- Versión original: React 18.2 + Django 5.1.4
