# 🚀 App de Currículum Inteligente con Bolsa de Trabajo y Simuladores

## Descripción General

Plataforma integral que ayuda a profesionales a crear, mejorar y personalizar sus currículums, descubrir su perfil laboral, superar obstáculos personales, y conectarse con bolsas de empleo en tiempo real.

**Sitio web**: [En desarrollo]  
**Licencia**: MIT  
**Versión**: 1.0.0 (En desarrollo)

---

## 📋 Tabla de Contenidos

- [Características Principales](#características-principales)
- [Tecnologías](#tecnologías)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Instalación](#instalación)
- [Configuración](#configuración)
- [Uso](#uso)
- [Documentación](#documentación)
- [Módulos](#módulos)
- [Contribuir](#contribuir)
- [Licencia](#licencia)

---

## ✨ Características Principales

### 🎯 Módulo 1: Descubre tu Perfil Profesional
- Test interactivo de diagnóstico inicial
- Identificación de habilidades, fortalezas y debilidades
- Detección de obstáculos personales (falta de tiempo, desmotivación, etc.)
- Análisis de motivaciones profesionales
- Generación de perfil profesional personalizado

### 🛠️ Módulo 2: Supera tus Obstáculos
- Identificación de causas raíz
- Protocolos personalizados para cada obstáculo
- Recomendaciones de cursos y capacitaciones
- Seguimiento de progreso

### 🧪 Módulo 3: Test de Diagnóstico Profesional
- Cuestionario adaptativo con calificación
- Comparación con perfiles de empresas
- Recomendaciones de especialización

### 📚 Módulo 4: Caja de Herramientas Profesionales
- Cursos recomendados
- Capacitaciones personalizadas
- Integración con plataformas e-learning
- Tracking de habilidades

### 🎮 Módulo 5: Juegos Prácticos y Simuladores
- Juegos interactivos por plaza
- Simulador de entrevistas con IA
- Investigación automática de empresas
- Feedback en tiempo real

### 📄 Módulo 6: Creador de Currículum Inteligente
- Editor visual de CV
- Secciones: Identidad, Competencias, Portafolio, Valor Diferencial
- Generación automática según sector
- Evaluador de calidad de CV
- Exportación PDF/Word

### 💼 Módulo 7: Bolsa de Empleo
- Conexión con múltiples bolsas de trabajo
- Filtros: remoto/presencial, sector, nivel
- Actualización en tiempo real
- Aplicación directa desde plataforma

### 💳 Módulo 8: Sistema de Pagos
- Tarjeta crédito/débito
- PayPal, UglyCash
- Suscripciones premium
- Historial de transacciones

### 🏆 Módulo 9: Portafolio de Prácticas
- Registro de certificaciones
- Historial de entrevistas
- Tracking de aplicaciones
- Estadísticas de éxito

---

## 🛠️ Tecnologías

### Frontend
- **Framework**: React 18+ / Next.js 14+
- **Tipografía**: Inter, Poppins, JetBrains Mono, Lato (Google Fonts)
- **Colores**: Sistema personalizado basado en psicología de colores
- **UI Library**: Tailwind CSS
- **Estado**: Redux / Zustand
- **Formularios**: React Hook Form
- **Gráficos**: Chart.js / Recharts
- **PDF**: PDFKit / jsPDF

### Backend
- **Runtime**: Node.js 18+
- **Framework**: Express.js / NestJS
- **Base de Datos**: PostgreSQL / MongoDB
- **ORM**: Prisma / TypeORM
- **Autenticación**: JWT / OAuth 2.0
- **API**: REST / GraphQL
- **Validación**: Zod / Joi

### DevOps & Deployment
- **Version Control**: Git / GitHub
- **CI/CD**: GitHub Actions
- **Containerización**: Docker
- **Hosting**: Vercel / Railway / AWS
- **Base de Datos**: Supabase / Railway
- **Email**: SendGrid / Nodemailer
- **Almacenamiento**: AWS S3 / Cloudinary

### Herramientas Adicionales
- **Testing**: Jest, Vitest, Cypress
- **Linting**: ESLint, Prettier
- **Documentación**: Swagger/OpenAPI
- **Monitoreo**: Sentry, LogRocket
- **Analytics**: Plausible / Google Analytics

---

## 📁 Estructura del Proyecto

```
app-curriculum-inteligente/
│
├── 📖 DOCUMENTACIÓN
│   ├── PALETA_COLORES.md           # Colores basados en psicología
│   ├── TIPOGRAFIA.md                # Guía de tipografía
│   ├── ARQUITECTURA.md              # Diagrama de arquitectura
│   ├── BD_MODELOS.md                # Modelos de base de datos
│   └── README.md                    # Este archivo
│
├── 📱 frontend/                     # Aplicación React/Next.js
│   ├── public/
│   │   ├── images/
│   │   ├── icons/
│   │   └── fonts/
│   │
│   ├── src/
│   │   ├── components/
│   │   │   ├── common/              # Componentes reutilizables
│   │   │   │   ├── Button/
│   │   │   │   ├── Card/
│   │   │   │   ├── Input/
│   │   │   │   ├── Modal/
│   │   │   │   ├── Badge/
│   │   │   │   ├── ProgressBar/
│   │   │   │   └── ...
│   │   │   │
│   │   │   ├── layouts/             # Layouts principales
│   │   │   │   ├── AuthLayout.tsx
│   │   │   │   ├── DashboardLayout.tsx
│   │   │   │   └── PublicLayout.tsx
│   │   │   │
│   │   │   └── modules/             # Componentes por módulo
│   │   │       ├── perfiles/
│   │   │       ├── diagnóstico/
│   │   │       ├── curriculum/
│   │   │       ├── simuladores/
│   │   │       ├── bolsa-empleo/
│   │   │       ├── pagos/
│   │   │       └── portafolio/
│   │   │
│   │   ├── pages/
│   │   │   ├── auth/
│   │   │   ├── dashboard/
│   │   │   ├── modulos/
│   │   │   └── 404.tsx
│   │   │
│   │   ├── hooks/                   # Custom Hooks
│   │   │   ├── useAuth.ts
│   │   │   ├── useProfile.ts
│   │   │   ├── useCurriculum.ts
│   │   │   └── ...
│   │   │
│   │   ├── store/                   # Estado global (Redux/Zustand)
│   │   │   ├── auth/
│   │   │   ├── profile/
│   │   │   ├── curriculum/
│   │   │   └── ...
│   │   │
│   │   ├── services/                # APIs y llamadas HTTP
│   │   │   ├── authService.ts
│   │   │   ├── profileService.ts
│   │   │   ├── curriculumService.ts
│   │   │   └── ...
│   │   │
│   │   ├── utils/
│   │   │   ├── constants.ts
│   │   │   ├── helpers.ts
│   │   │   ├── validators.ts
│   │   │   └── colors.ts            # Utilidades de colores
│   │   │
│   │   ├── styles/
│   │   │   ├── globals.css
│   │   │   ├── tailwind.config.js
│   │   │   └── typography.css
│   │   │
│   │   ├── types/
│   │   │   ├── user.ts
│   │   │   ├── curriculum.ts
│   │   │   ├── profile.ts
│   │   │   └── ...
│   │   │
│   │   └── App.tsx
│   │
│   ├── .env.example
│   ├── package.json
│   ├── tailwind.config.js
│   ├── tsconfig.json
│   └── next.config.js
│
├── 🔌 backend/                      # API Node.js/Express/NestJS
│   ├── src/
│   │   ├── modules/
│   │   │   ├── auth/
│   │   │   │   ├── auth.controller.ts
│   │   │   │   ├── auth.service.ts
│   │   │   │   ├── auth.module.ts
│   │   │   │   └── auth.repository.ts
│   │   │   │
│   │   │   ├── users/
│   │   │   ├── profiles/
│   │   │   ├── curriculum/
│   │   │   ├── simulators/
│   │   │   ├── jobs/
│   │   │   ├── payments/
│   │   │   └── portfolio/
│   │   │
│   │   ├── database/
│   │   │   ├── migrations/
│   │   │   ├── seeds/
│   │   │   └── schema.prisma
│   │   │
│   │   ├── config/
│   │   │   ├── database.ts
│   │   │   ├── jwt.ts
│   │   │   └── env.ts
│   │   │
│   │   ├── middleware/
│   │   │   ├── auth.middleware.ts
│   │   │   ├── error.middleware.ts
│   │   │   └── validation.middleware.ts
│   │   │
│   │   ├── utils/
│   │   │   ├── logger.ts
│   │   │   └── helpers.ts
│   │   │
│   │   └── main.ts
│   │
│   ├── .env.example
│   ├── package.json
│   ├── tsconfig.json
│   └── docker-compose.yml
│
├── 🗄️ database/                     # Scripts y migraciones
│   ├── migrations/
│   ├── seeds/
│   └── schema.sql
│
├── 📚 docs/                         # Documentación técnica
│   ├── API.md                       # Especificación de API
│   ├── DEPLOYMENT.md                # Guía de despliegue
│   ├── CONTRIBUTING.md              # Cómo contribuir
│   └── SETUP.md                     # Setup local
│
├── 🐳 docker/
│   ├── Dockerfile
│   ├── docker-compose.yml
│   └── .dockerignore
│
├── ⚙️ config/
│   ├── .eslintrc
│   ├── .prettierrc
│   ├── jest.config.js
│   └── vitest.config.ts
│
├── 📋 .github/
│   ├── workflows/
│   │   ├── ci.yml
│   │   ├── cd.yml
│   │   └── tests.yml
│   │
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.md
│       └── feature_request.md
│
├── 🌐 .env.example                  # Variables de entorno ejemplo
├── .gitignore
├── .gitattributes
├── package.json                     # Monorepo root
├── pnpm-workspace.yaml              # Monorepo config
├── turbo.json                       # Build orchestration
├── LICENSE                          # MIT License
└── README.md                        # Este archivo

```

---

## 🚀 Instalación

### Requisitos Previos
- **Node.js**: v18.0.0 o superior
- **npm/pnpm**: v8.0.0 o superior
- **Git**: v2.30.0 o superior
- **PostgreSQL**: v14+ (o MongoDB)
- **Docker** (opcional, recomendado)

### Paso 1: Clonar Repositorio

```bash
git clone https://github.com/businesseceltoro-boop/app-curriculum-inteligente.git
cd app-curriculum-inteligente
```

### Paso 2: Instalar Dependencias

```bash
# Con pnpm (recomendado)
pnpm install

# O con npm
npm install

# O con yarn
yarn install
```

### Paso 3: Configurar Variables de Entorno

```bash
# Frontend
cp frontend/.env.example frontend/.env.local

# Backend
cp backend/.env.example backend/.env.local

# Editar archivos con tus credenciales
```

### Paso 4: Iniciar Base de Datos

```bash
# Con Docker
docker-compose up -d

# O setupear PostgreSQL localmente
psql -U postgres -c "CREATE DATABASE curriculum_app;"
```

### Paso 5: Ejecutar Migraciones

```bash
cd backend
pnpm prisma migrate dev
```

### Paso 6: Ejecutar en Desarrollo

```bash
# En un terminal (Backend - puerto 3001)
cd backend
pnpm dev

# En otro terminal (Frontend - puerto 3000)
cd frontend
pnpm dev
```

---

## ⚙️ Configuración

### Variables de Entorno

**Frontend (.env.local)**
```env
NEXT_PUBLIC_API_URL=http://localhost:3001
NEXT_PUBLIC_APP_NAME=App de Currículum Inteligente
NEXT_PUBLIC_SENTRY_DSN=your_sentry_dsn
```

**Backend (.env)**
```env
PORT=3001
DATABASE_URL=postgresql://user:password@localhost:5432/curriculum_app
JWT_SECRET=your_jwt_secret
JWT_EXPIRY=7d
NODE_ENV=development
```

---

## 📖 Uso

### Inicio de Sesión
1. Acceder a `http://localhost:3000`
2. Registrarse o iniciar sesión
3. Completar test de diagnóstico

### Crear Currículum
1. Ir a "Crear Currículum"
2. Seleccionar sector profesional
3. Llenar información
4. Descargar PDF

### Usar Simulador
1. Ir a "Simuladores"
2. Seleccionar puesto y empresa
3. Responder preguntas
4. Obtener feedback

---

## 📚 Documentación

- **[PALETA_COLORES.md](./PALETA_COLORES.md)** - Colores y psicología
- **[TIPOGRAFIA.md](./TIPOGRAFIA.md)** - Tipografía y escalas
- **[ARQUITECTURA.md](./docs/ARQUITECTURA.md)** - Diagrama técnico
- **[BD_MODELOS.md](./docs/BD_MODELOS.md)** - Modelos de datos
- **[API.md](./docs/API.md)** - Especificación API
- **[SETUP.md](./docs/SETUP.md)** - Guía de setup

---

## 🎯 Módulos

### ✅ Fase 1: MVP (Q4 2026)
- [x] Autenticación
- [x] Test de diagnóstico
- [x] Perfil profesional
- [x] Editor de currículum básico
- [ ] Simulador de entrevistas simple

### 📅 Fase 2: (Q1 2027)
- [ ] Bolsa de empleo MVP
- [ ] Sistema de pagos
- [ ] Módulo de juegos prácticos
- [ ] Caja de herramientas

### 🚀 Fase 3: (Q2 2027)
- [ ] IA avanzada para feedback
- [ ] Integración con plataformas e-learning
- [ ] Portafolio de prácticas
- [ ] Analytics avanzado

---

## 🤝 Contribuir

1. Fork el proyecto
2. Crear rama feature (`git checkout -b feature/AmazingFeature`)
3. Commit cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a rama (`git push origin feature/AmazingFeature`)
5. Abrir Pull Request

Ver [CONTRIBUTING.md](./docs/CONTRIBUTING.md) para más detalles.

---

## 📝 Licencia

Este proyecto está bajo la licencia MIT - Ver archivo [LICENSE](./LICENSE)

---

## 👥 Autor

- **Businesseceltoro-boop** - Autor original

## 🙏 Agradecimientos

- Google Fonts (Tipografías)
- Tailwind CSS (UI Framework)
- Prisma (ORM)
- React (Frontend Framework)

---

## 📞 Soporte

Para reportar bugs o solicitar features:
- **Issues**: [GitHub Issues](https://github.com/businesseceltoro-boop/app-curriculum-inteligente/issues)
- **Discussions**: [GitHub Discussions](https://github.com/businesseceltoro-boop/app-curriculum-inteligente/discussions)

---

## 🔄 Roadmap

- **v1.0** (2026): MVP con diagnóstico, CV y simulador básico
- **v1.1** (2027 Q1): Bolsa de empleo y pagos
- **v1.2** (2027 Q2): Gamificación y IA avanzada
- **v2.0** (2027 Q4): Plataforma completa con todas las features

---

**Última actualización**: 16/09/2026  
**Estado**: 🚧 En desarrollo
