# 🏗️ Arquitectura del Sistema - App de Currículum Inteligente

## Diagrama General de Arquitectura

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          CAPA DE PRESENTACIÓN (Frontend)                     │
│                                                                               │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐          │
│  │   Web Browser    │  │  Mobile App      │  │  Progressive Web │          │
│  │   React/Next.js  │  │  React Native    │  │  App (PWA)       │          │
│  └────────┬─────────┘  └────────┬─────────┘  └────────┬─────────┘          │
│           │                      │                      │                    │
│           └──────────────────────┼──────────────────────┘                    │
│                                  │                                           │
│                        ┌─────────▼─────────┐                                │
│                        │   Redux / Zustand │ (Estado Global)                │
│                        │   - Auth State    │                                │
│                        │   - User Profile  │                                │
│                        │   - CV Data       │                                │
│                        └─────────┬─────────┘                                │
│                                  │                                           │
│                        ┌─────────▼─────────┐                                │
│                        │   API Client      │                                │
│                        │   - Axios/Fetch   │                                │
│                        │   - Auth Headers  │                                │
│                        └─────────┬─────────┘                                │
└────────────────────────────────────┼──────────────────────────────────────────┘
                                     │ HTTPS
                    ┌────────────────┼────────────────┐
                    │                │                │
┌───────────────────▼─────────────────▼────────────────▼──────────────────────┐
│                     CAPA DE API GATEWAY / LOAD BALANCER                      │
│                                                                              │
│  ┌────────────────────────────────────────────────────────────┐            │
│  │  API Gateway (Kong / AWS API Gateway)                      │            │
│  │  - Rate Limiting                                           │            │
│  │  - CORS Handling                                           │            │
│  │  - Request Validation                                      │            │
│  └────────────────────┬───────────────────────────────────────┘            │
│                       │                                                     │
│         ┌─────────────┼─────────────┬──────────────┐                       │
│         │             │             │              │                       │
└─────────┼─────────────┼─────────────┼──────────────┼───────────────────────┘
          │             │             │              │
          │ HTTP/REST   │             │              │
┌─────────▼──────────────▼─────────────▼──────────────▼────────────────────┐
│              CAPA DE SERVICIOS (Backend - Microservicios)                │
│                                                                          │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐      │
│  │ Auth Service     │  │ Profile Service  │  │ Curriculum       │      │
│  │ ───────────────  │  │ ───────────────  │  │ Service          │      │
│  │ • Login          │  │ • Get Profile    │  │ ──────────────   │      │
│  │ • Register       │  │ • Diagnóstico    │  │ • Create CV      │      │
│  │ • Verify Token   │  │ • Skills         │  │ • Evaluate CV    │      │
│  │ • Refresh Token  │  │ • Motivations    │  │ • Export PDF     │      │
│  └──────────┬───────┘  └────────┬─────────┘  └────────┬─────────┘      │
│             │                   │                     │                  │
│  ┌──────────▼──────────┐  ┌──────────────────┐  ┌──────────┬──────────┐ │
│  │ Simulator Service   │  │ Job Service      │  │ Payment  │ Portfolio│ │
│  │ ──────────────────  │  │ ──────────────   │  │ Service  │ Service  │ │
│  │ • Interview Quiz    │  │ • Job Listings   │  │ ──────   │ ──────   │ │
│  │ • Practice Games    │  │ • Apply to Job   │  │ • Stripe │ • Track  │ │
│  │ • AI Feedback       │  │ • Save Favorites │  │ • PayPal │ • Certs  │ │
│  │ • Score Analysis    │  │ • Notifications  │  │ • Subscr │ • History│ │
│  └──────────┬──────────┘  └────────┬─────────┘  └──────┬───┴──────────┘ │
│             │                      │                    │                 │
└─────────────┼──────────────────────┼────────────────────┼─────────────────┘
              │                      │                    │
              └──────────────────────┼────────────────────┘
                                     │
┌────────────────────────────────────▼──────────────────────────────────────┐
│               CAPA DE DATOS Y PERSISTENCIA                                │
│                                                                            │
│  ┌──────────────────────┐  ┌──────────────────────┐                      │
│  │   Base de Datos      │  │   Cache Layer        │                      │
│  │   PostgreSQL         │  │   Redis              │                      │
│  │ ──────────────────   │  │ ──────────────────   │                      │
│  │ • Users              │  │ • Sessions           │                      │
│  │ • Profiles           │  │ • CV Cache           │                      │
│  │ • CVs                │  │ • Job Listings       │                      │
│  │ • Skills             │  │ • User Preferences   │                      │
│  │ • Jobs               │  │ • API Responses      │                      │
│  │ • Applications       │  │                      │                      │
│  │ • Payments           │  │                      │                      │
│  │ • Certificates       │  │                      │                      │
│  └──────────────────────┘  └──────────────────────┘                      │
│                                                                            │
│  ┌──────────────────────┐  ┌──────────────────────┐                      │
│  │ Almacenamiento       │  │ Message Queue        │                      │
│  │ S3 / Cloudinary      │  │ RabbitMQ / Kafka     │                      │
│  │ ──────────────────   │  │ ──────────────────   │                      │
│  │ • Profile Images     │  │ • Email Notifications│                      │
│  │ • CV PDFs            │  │ • Job Updates        │                      │
│  │ • Portfolio Files    │  │ • Payment Events     │                      │
│  │ • Certificates       │  │ • Async Tasks        │                      │
│  └──────────────────────┘  └──────────────────────┘                      │
└────────────────────────────────────────────────────────────────────────────┘
```

---

## 🔄 Flujo de Datos por Módulo

### Módulo 1: Diagnóstico y Perfil Profesional

```
Frontend                          Backend                      Database
  │                                 │                            │
  ├─ Test Iniciado ──────────────► │                             │
  │                        (POST /api/diagnosis/start)            │
  │                                 │                             │
  │                                 ├─ Crear sesión ─────────────►│
  │                                 │                             │
  │◄─ ID Sesión ──────────────────┤                             │
  │                                 │                             │
  ├─ Respuestas ──────────────────► │                             │
  │                   (POST /api/diagnosis/:id/answer)           │
  │                                 │                             │
  │                                 ├─ Guardar respuesta ───────►│
  │                                 │                             │
  │                                 ├─ Generar perfil ────┐      │
  │                                 │◄─────────────────────┘      │
  │                                 │                             │
  │◄─ Perfil Personalizado ───────┤                             │
  │  - Fortalezas                   │                             │
  │  - Debilidades                  │                             │
  │  - Motivaciones                 │                             │
  │  - Recomendaciones              │                             │
```

### Módulo 2: Editor de Currículum

```
Frontend                          Backend                      Database
  │                                 │                            │
  ├─ CV Template ────────────────► │                             │
  │        (Sector seleccionado)    │                             │
  │                                 ├─ Aplicar Tema ────────────►│
  │◄─ CV Inicial ──────────────────┤ Según Sector               │
  │  - Colores                      │                             │
  │  - Tipografía                   │                             │
  │  - Estructura                   │                             │
  │                                 │                             │
  ├─ Edición en tiempo real ──────► │                             │
  │   (PUT /api/curriculum/:id)     │                             │
  │                                 ├─ Actualizar CV ───────────►│
  │                                 │ (Cada 30 segundos)         │
  │                                 │                             │
  │◄─ CV Actualizado ──────────────┤                             │
  │  - Preview                      │                             │
  │  - Errores validación           │                             │
  │                                 │                             │
  ├─ Descargar PDF ───────────────► │                             │
  │    (GET /api/curriculum/:id/pdf)│                             │
  │                                 ├─ Generar PDF ─────────────►│
  │                                 │ (jsPDF/PDFKit)             │
  │◄─ PDF Descargado ──────────────┤ (S3 Storage)              │
```

### Módulo 3: Simulador de Entrevistas

```
Frontend                          Backend                      External APIs
  │                                 │                            │
  ├─ Seleccionar Empresa/Puesto──► │                             │
  │     (POST /api/simulator/start) │                             │
  │                                 ├─ Buscar info Empresa ─────►│ Google API
  │                                 │                             │◄─ Info Empresa
  │                                 │◄────────────────────────────┤
  │                                 │                             │
  │                                 ├─ Generar preguntas ────────►│ OpenAI/Claude
  │                                 │ (Basadas en empresa)        │ (IA)
  │                                 │                             │◄─ Questions
  │                                 │◄────────────────────────────┤
  │                                 │                             │
  │◄─ Primera Pregunta ────────────┤                             │
  │                                 │                             │
  ├─ Respuesta Usuario ───────────► │                             │
  │   (POST /api/simulator/:id/answer)                           │
  │                                 │                             │
  │                                 ├─ Analizar Respuesta ──────►│ OpenAI/Claude
  │                                 │ (IA - NLP)                 │ (Sentiment Analysis)
  │                                 │                             │◄─ Score & Feedback
  │                                 │◄────────────────────────────┤
  │                                 │                             │
  │◄─ Feedback + Siguiente Pregunta┤                             │
  │  - Puntuación                   │                             │
  │  - Recomendaciones              │                             │
```

### Módulo 4: Bolsa de Empleo

```
Frontend                      Backend                    Database/External
  │                             │                           │
  ├─ Solicitar Empleos ───────► │                           │
  │  (GET /api/jobs)            │                           │
  │  - Filtros aplicados        │                           │
  │                             ├─ Buscar en Cache ───────► │ Redis
  │                             │◄─ Empleos               │
  │                             │                           │
  │                             ├─ Si no en Cache:         │
  │                             │  ├─ LinkedIn API ───────►│
  │                             │  ├─ Indeed API ─────────►│
  │                             │  └─ Local Jobs API ─────►│
  │                             │◄─ Resultados             │
  │                             │                           │
  │                             ├─ Guardar en Cache ──────► │ Redis (24h)
  │                             │                           │
  │◄─ Lista de Empleos ────────┤                           │
  │  - Título                   │                           │
  │  - Empresa                  │                           │
  │  - Ubicación                │                           │
  │  - Remoto/Presencial        │                           │
  │  - Salario                  │                           │
  │  - Match score              │                           │
  │                             │                           │
  ├─ Aplicar a Empleo ────────► │                           │
  │  (POST /api/jobs/:id/apply) │                           │
  │                             ├─ Guardar aplicación ────►│ PostgreSQL
  │                             │                           │
  │                             ├─ Enviar Email ─────────► │ SendGrid
  │                             │ (Confirmación)            │
  │                             │                           │
  │◄─ Confirmación ────────────┤                           │
```

### Módulo 5: Sistema de Pagos

```
Frontend                      Backend                    Payment Provider
  │                             │                           │
  ├─ Seleccionar Plan ────────► │                           │
  │  (Premium/Enterprise)       │                           │
  │                             │                           │
  ├─ Datos de Pago ───────────► │                           │
  │  (Tarjeta/PayPal)          │                           │
  │  (POST /api/payments)       │                           │
  │                             ├─ Validar datos ──────────►│
  │                             │◄─ Datos válidos           │
  │                             │                           │
  │                             ├─ Crear transacción ──────►│ Stripe/PayPal
  │                             │                           │◄─ Token
  │                             │◄────────────────────────────┤
  │                             │                           │
  │                             ├─ Guardar transacción ────►│ PostgreSQL
  │                             │                           │
  │                             ├─ Activar suscripción ────►│ PostgreSQL
  │                             │                           │
  │                             ├─ Enviar recibo ──────────►│ SendGrid
  │                             │                           │
  │◄─ Pago Exitoso ────────────┤                           │
  │  - Recibo                   │                           │
  │  - Acceso Premium           │                           │
  │  - Fecha renovación         │                           │
```

---

## 🗄️ Esquema de Base de Datos

```sql
-- Tabla de Usuarios
CREATE TABLE users (
  id UUID PRIMARY KEY,
  email VARCHAR(255) UNIQUE,
  password_hash VARCHAR(255),
  first_name VARCHAR(100),
  last_name VARCHAR(100),
  profile_picture_url VARCHAR(500),
  is_active BOOLEAN DEFAULT true,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de Perfiles Profesionales
CREATE TABLE professional_profiles (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  strengths JSONB,              -- Fortalezas identificadas
  weaknesses JSONB,             -- Debilidades
  motivations JSONB,            -- Motivaciones
  obstacles JSONB,              -- Obstáculos identificados
  sector VARCHAR(100),
  level VARCHAR(50),            -- Junior, Mid, Senior, Lead
  test_score INT,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de Currículums
CREATE TABLE curriculums (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  title VARCHAR(200),
  sector VARCHAR(100),
  professional_title VARCHAR(200),
  contact_info JSONB,
  summary TEXT,
  theme_color VARCHAR(7),       -- Color HEX
  font_family VARCHAR(50),
  is_published BOOLEAN DEFAULT false,
  view_count INT DEFAULT 0,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de Experiencia Laboral
CREATE TABLE cv_experience (
  id UUID PRIMARY KEY,
  curriculum_id UUID REFERENCES curriculums(id),
  company_name VARCHAR(200),
  job_title VARCHAR(200),
  description TEXT,
  start_date DATE,
  end_date DATE,
  is_current BOOLEAN,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de Competencias
CREATE TABLE cv_skills (
  id UUID PRIMARY KEY,
  curriculum_id UUID REFERENCES curriculums(id),
  skill_name VARCHAR(100),
  proficiency_level INT (1-5),
  years_experience INT,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de Trabajos/Empleos
CREATE TABLE jobs (
  id UUID PRIMARY KEY,
  title VARCHAR(200),
  company_name VARCHAR(200),
  description TEXT,
  salary_min INT,
  salary_max INT,
  location VARCHAR(200),
  is_remote BOOLEAN,
  sector VARCHAR(100),
  level VARCHAR(50),
  requirements JSONB,
  source VARCHAR(50),           -- LinkedIn, Indeed, Local
  source_url VARCHAR(500),
  posted_date TIMESTAMP,
  expires_date TIMESTAMP,
  active BOOLEAN DEFAULT true,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de Aplicaciones a Empleos
CREATE TABLE job_applications (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  job_id UUID REFERENCES jobs(id),
  applied_date TIMESTAMP DEFAULT NOW(),
  status VARCHAR(50),           -- Applied, Viewed, Rejected, Accepted
  response_date TIMESTAMP,
  notes TEXT
);

-- Tabla de Simuladores/Tests
CREATE TABLE simulator_sessions (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  job_id UUID REFERENCES jobs(id),
  company_name VARCHAR(200),
  start_time TIMESTAMP,
  end_time TIMESTAMP,
  score INT,
  feedback TEXT,
  questions_answered INT,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de Preguntas en Simuladores
CREATE TABLE simulator_questions (
  id UUID PRIMARY KEY,
  session_id UUID REFERENCES simulator_sessions(id),
  question_text TEXT,
  user_answer TEXT,
  ai_score INT,
  ai_feedback TEXT,
  answer_order INT
);

-- Tabla de Pagos/Transacciones
CREATE TABLE transactions (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  amount DECIMAL(10, 2),
  currency VARCHAR(3),          -- USD, EUR, etc.
  payment_method VARCHAR(50),   -- card, paypal, etc.
  plan_type VARCHAR(50),        -- Premium, Enterprise
  status VARCHAR(50),           -- Pending, Completed, Failed
  provider_transaction_id VARCHAR(255),
  created_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de Suscripciones
CREATE TABLE subscriptions (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  plan_type VARCHAR(50),        -- Premium, Enterprise
  start_date TIMESTAMP,
  end_date TIMESTAMP,
  is_active BOOLEAN,
  auto_renewal BOOLEAN DEFAULT true,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Tabla de Certificaciones
CREATE TABLE certifications (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  title VARCHAR(200),
  issuer VARCHAR(200),
  issue_date DATE,
  expiration_date DATE,
  credential_url VARCHAR(500),
  credential_id VARCHAR(200),
  created_at TIMESTAMP DEFAULT NOW()
);
```

---

## 🔐 Seguridad

### Autenticación y Autorización
```
┌─────────────────┐
│   Usuario Login │
└────────┬────────┘
         │
         ▼
┌──────────────────────┐
│ Validar Credenciales │
└────────┬─────────────┘
         │
         ▼
┌────────────────────────┐
│ Generar JWT Token      │
│ - Access Token (15min) │
│ - Refresh Token (7d)   │
└────────┬───────────────┘
         │
         ▼
┌──────────────────────────┐
│ Almacenar en Cliente     │
│ - Local Storage (Token)  │
│ - HttpOnly Cookie (RT)   │
└────────┬─────────────────┘
         │
         ▼
┌──────────────────────────┐
│ Incluir en Headers       │
│ Authorization: Bearer {} │
└──────────────────────────┘
```

### Protección de Datos
- ✅ Hashing de contraseñas: bcrypt
- ✅ Encriptación de datos sensibles: AES-256
- ✅ HTTPS obligatorio
- ✅ CORS configurado
- ✅ Rate limiting
- ✅ Input validation/sanitization

---

## 📊 Escalabilidad

### Estrategia de Escalado
```
Load Balancer (AWS/Kong)
        │
    ┌───┴───┐
    │       │
   ┌▼─┐   ┌─▼┐
   │ S1│   │S2│  ... (N servidores)
   └┬─┘   └─┬┘
    │       │
    └───┬───┘
        │
    ┌───▼────────┐
    │ PostgreSQL │ (Master-Replica)
    └────────────┘
        │
    ┌───▼────┐
    │ Redis  │ (Cluster)
    └────────┘
```

### Cache Strategy
- Frontend: LocalStorage + SessionStorage
- Backend: Redis (24h TTL para jobs, 1h para perfiles)
- CDN: Imágenes, fonts, assets estáticos

---

## 📈 Monitoreo y Logging

```
┌──────────────────────┐
│  Aplicación          │
│  - Requests          │
│  - Errors            │
│  - Performance       │
└────────┬─────────────┘
         │
    ┌────▼─────┐
    │  Logger   │ (Winston/Pino)
    └────┬─────┘
         │
    ┌────▼──────────────┬──────────────┐
    │                   │              │
┌───▼────┐  ┌──────────▼──┐  ┌────────▼────┐
│ Sentry │  │ LogRocket   │  │ DataDog     │
│ (Errors)  │ (Frontend)  │  │ (Metrics)   │
└────────┘  └─────────────┘  └─────────────┘
```

---

## 🚀 Deployment

```
GitHub Repo
    │
    ▼
GitHub Actions (CI/CD)
    │
    ├─ Lint & Format Check
    ├─ Unit Tests
    ├─ Integration Tests
    ├─ Build Docker Image
    │
    ▼
Container Registry (Docker Hub/ECR)
    │
    ▼
Staging Environment (Testing)
    │ (Manual Approval)
    ▼
Production Environment
    │
    ├─ Vercel (Frontend)
    ├─ Railway/AWS (Backend)
    └─ Database migrations
```

---

**Versión**: 1.0  
**Última actualización**: 2026-09-16
