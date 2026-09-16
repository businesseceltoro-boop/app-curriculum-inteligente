# 📝 Tipografía - App de Currículum Inteligente

## Filosofía Tipográfica

**Principios**: Formal pero moderno, accesible, profesional y dinámico.

- ✅ Legibilidad óptima en pantalla
- ✅ Modernidad sin perder formalidad
- ✅ Accesibilidad (WCAG AA mínimo)
- ✅ Respuesta adaptable a dispositivos
- ✅ Coherencia visual en toda la app

---

## 1. FAMILIAS TIPOGRÁFICAS PRINCIPALES

### 🎯 Tipografía Principal: INTER
**Categoría**: Sans-serif Humanista  
**Peso**: 400 (Regular), 500 (Medium), 600 (Semibold), 700 (Bold)  
**Uso**: Cuerpo de texto, navegación, párrafos, descripciones

**Características**:
- Muy legible en pantalla
- Neutral pero cálida
- Excelente para interfaces digitales
- Moderna y profesional

**Descargar**: https://fonts.google.com/specimen/Inter

```css
font-family: 'Inter', sans-serif;
```

---

### 📌 Tipografía de Títulos: POPPINS
**Categoría**: Sans-serif Geométrica  
**Peso**: 600 (Semibold), 700 (Bold), 800 (Extrabold)  
**Uso**: H1, H2, H3, títulos de secciones, CTA principales

**Características**:
- Llamativa pero profesional
- Moderna y dinámica
- Excelente para jerarquía visual
- Perfecta para encabezados

**Descargar**: https://fonts.google.com/specimen/Poppins

```css
font-family: 'Poppins', sans-serif;
```

---

### 💻 Tipografía Técnica (Opcional): JetBrains MONO
**Categoría**: Monoespaciada  
**Peso**: 400 (Regular), 600 (Semibold)  
**Uso**: Código, ejemplos técnicos, módulo de programadores

**Características**:
- Diseñada específicamente para desarrolladores
- Clara y profesional
- Perfecta para secciones técnicas

**Descargar**: https://fonts.google.com/specimen/JetBrains+Mono

```css
font-family: 'JetBrains Mono', monospace;
```

---

### ✨ Tipografía Alternativa (Elegancia): LATO
**Categoría**: Sans-serif Humanista  
**Peso**: 300 (Light), 400 (Regular), 700 (Bold)  
**Uso**: Perfiles ejecutivos, currículums formales, secciones premium

**Características**:
- Elegante y refinada
- Excelente para contenido profesional
- Muy legible
- Moderna pero clásica

**Descargar**: https://fonts.google.com/specimen/Lato

```css
font-family: 'Lato', sans-serif;
```

---

## 2. JERARQUÍA TIPOGRÁFICA WEB

### 🔤 Encabezado H1 (Título Principal)
```css
font-family: 'Poppins', sans-serif;
font-size: 48px;
font-weight: 700;
line-height: 1.2;
letter-spacing: -0.02em;
color: #0052CC;
```
**Ejemplo**: "App de Currículum Inteligente"

---

### 🔤 Encabezado H2 (Subtítulo Principal)
```css
font-family: 'Poppins', sans-serif;
font-size: 36px;
font-weight: 600;
line-height: 1.3;
letter-spacing: -0.01em;
color: #1F2937;
```
**Ejemplo**: "Descubre tu Perfil Profesional"

---

### 🔤 Encabezado H3 (Título de Sección)
```css
font-family: 'Poppins', sans-serif;
font-size: 24px;
font-weight: 600;
line-height: 1.4;
letter-spacing: 0em;
color: #1F2937;
```
**Ejemplo**: "Módulos Principales"

---

### 🔤 Encabezado H4 (Subtítulo de Card)
```css
font-family: 'Poppins', sans-serif;
font-size: 18px;
font-weight: 600;
line-height: 1.5;
letter-spacing: 0em;
color: #374151;
```
**Ejemplo**: "Tu Perfil Laboral"

---

### 📄 Cuerpo de Texto (Body)
```css
font-family: 'Inter', sans-serif;
font-size: 16px;
font-weight: 400;
line-height: 1.6;
letter-spacing: 0em;
color: #4B5563;
```
**Ejemplo**: Párrafos de descripción, explicaciones

---

### 📝 Texto Pequeño (Small)
```css
font-family: 'Inter', sans-serif;
font-size: 14px;
font-weight: 400;
line-height: 1.5;
letter-spacing: 0em;
color: #6B7280;
```
**Ejemplo**: Textos secundarios, fechas, metadata

---

### 🏷️ Etiquetas / Badges
```css
font-family: 'Inter', sans-serif;
font-size: 12px;
font-weight: 600;
line-height: 1.4;
letter-spacing: 0.05em;
text-transform: uppercase;
color: #FFFFFF;
```
**Ejemplo**: "Premium", "Nuevo", "Recomendado"

---

### 🔘 Botones (Button Text)
```css
font-family: 'Poppins', sans-serif;
font-size: 16px;
font-weight: 600;
line-height: 1.5;
letter-spacing: 0em;
color: #FFFFFF;
text-transform: capitalize;
```
**Ejemplo**: "Comenzar Evaluación", "Crear Currículum"

---

### 💻 Código / Técnico
```css
font-family: 'JetBrains Mono', monospace;
font-size: 14px;
font-weight: 400;
line-height: 1.6;
letter-spacing: 0.02em;
color: #1F2937;
background-color: #F3F4F6;
```

---

## 3. ESCALA TIPOGRÁFICA (Responsive)

### Desktop (1920px+)
| Elemento | Tamaño |
|----------|--------|
| H1 | 48px |
| H2 | 36px |
| H3 | 24px |
| H4 | 18px |
| Body | 16px |
| Small | 14px |

### Tablet (768px - 1024px)
| Elemento | Tamaño |
|----------|--------|
| H1 | 40px |
| H2 | 28px |
| H3 | 20px |
| H4 | 16px |
| Body | 15px |
| Small | 13px |

### Mobile (320px - 767px)
| Elemento | Tamaño |
|----------|--------|
| H1 | 32px |
| H2 | 24px |
| H3 | 18px |
| H4 | 14px |
| Body | 14px |
| Small | 12px |

---

## 4. TIPOGRAFÍA POR MÓDULO

### 🎯 Dashboard Principal
- Títulos: **Poppins Bold** (600-700)
- Subtítulos: **Poppins Medium** (500-600)
- Cuerpo: **Inter Regular** (400)
- Metadata: **Inter Light** (300)

### 📋 Módulo de Diagnóstico
- Preguntas: **Poppins Semibold** (600)
- Opciones: **Inter Regular** (400)
- Explicaciones: **Inter Regular** (400, color gris)
- Resultado: **Poppins Bold** (700)

### 🎓 Módulo de Perfiles
- Nombre del Perfil: **Poppins Bold** (700)
- Descripción: **Inter Regular** (400)
- Competencias: **Inter Semibold** (500)
- Niveles: **Inter Regular** (400)

### 💼 Módulo de Currículum
- Nombre Completo: **Poppins Bold** (700) - 24px
- Título Profesional: **Poppins Semibold** (600) - 18px
- Secciones (Experiencia, Competencias): **Poppins Semibold** (600)
- Contenido: **Inter Regular** (400)
- Fechas/Detalles: **Inter Regular** (400, gris)

### 🎮 Módulo de Simuladores
- Pregunta: **Poppins Semibold** (600)
- Opciones de respuesta: **Inter Regular** (400)
- Feedback: **Inter Medium** (500)
- Puntuación: **Poppins Bold** (700)

### 💰 Módulo de Pagos
- Plan Name: **Poppins Bold** (700)
- Precio: **Poppins Bold** (700, color dorado)
- Características: **Inter Regular** (400)
- CTA: **Poppins Semibold** (600)

### 🏢 Bolsa de Empleo
- Nombre de Empresa: **Poppins Semibold** (600)
- Puesto: **Poppins Medium** (500)
- Descripción: **Inter Regular** (400)
- Ubicación/Remoto: **Inter Regular** (400, gris)
- Plazas disponibles: **Inter Bold** (700, verde)

---

## 5. TIPOGRAFÍA PARA CURRÍCULUMS (CV Dinámico)

### Estructura Base

```
┌──────────────────────────────────────────┐
│ NOMBRE COMPLETO                          │  ← Poppins Bold, 24px
│ Título Profesional                       │  ← Poppins Semibold, 16px
│ 📧 email@example.com | 📱 +XX XXX XXXX │  ← Inter Regular, 12px
└──────────────────────────────────────────┘

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📌 PERFIL PROFESIONAL
Lorem ipsum...                               ← Inter Regular, 14px

🎓 EXPERIENCIA PROFESIONAL
Empresa XYZ (2020-2024)                     ← Poppins Semibold, 13px
Puesto: Senior Developer                    ← Inter Semibold, 12px
Logros y responsabilidades...               ← Inter Regular, 11px

🏆 COMPETENCIAS
• Leadership      [████████░░]
• Python          [██████████]               ← Inter Regular, 12px

📜 CERTIFICACIONES
Google Cloud Associate - 2024               ← Inter Semibold, 12px
```

---

### 5.1 Variantes por Sector

#### Tecnología (Moderno)
- Nombre: **JetBrains Mono Bold** (700) - 20px
- Título: **Inter Semibold** (600) - 14px
- Secciones: **Inter Bold** (700) - 12px
- Cuerpo: **Inter Regular** (400) - 11px
- Color primario: Cian (#06B6D4)
- Estilo: Minimalista, líneas geométricas

#### Administración (Formal)
- Nombre: **Poppins Bold** (700) - 22px
- Título: **Poppins Semibold** (600) - 14px
- Secciones: **Poppins Semibold** (600) - 12px
- Cuerpo: **Inter Regular** (400) - 11px
- Color primario: Azul Marino (#1E3A8A)
- Estilo: Elegante y ordenado

#### Diseño Creativo (Dinámico)
- Nombre: **Poppins Extrabold** (800) - 24px
- Título: **Poppins Bold** (700) - 16px
- Secciones: **Poppins Bold** (700) - 14px
- Cuerpo: **Inter Regular** (400) - 11px
- Color primario: Magenta (#EC4899)
- Estilo: Llamativo, con espacios visuales

#### Ejecutivo (Premium)
- Nombre: **Lato Bold** (700) - 22px
- Título: **Lato Semibold** (600) - 14px
- Secciones: **Lato Bold** (700) - 12px
- Cuerpo: **Lato Regular** (400) - 11px
- Color primario: Azul Oscuro (#0F172A)
- Estilo: Refinado y profesional

#### Salud (Accesible)
- Nombre: **Poppins Bold** (700) - 20px
- Título: **Inter Semibold** (600) - 13px
- Secciones: **Inter Bold** (700) - 11px
- Cuerpo: **Inter Regular** (400) - 11px
- Color primario: Azul Claro (#0EA5E9)
- Estilo: Clara y accesible

---

## 6. CONFIGURACIÓN TAILWIND CSS

```html
<!-- tailwind.config.js -->
module.exports = {
  theme: {
    fontFamily: {
      'sans': ['Inter', 'sans-serif'],
      'display': ['Poppins', 'sans-serif'],
      'mono': ['JetBrains Mono', 'monospace'],
      'elegant': ['Lato', 'sans-serif'],
    },
    fontSize: {
      'xs': ['12px', { lineHeight: '1.4' }],
      'sm': ['14px', { lineHeight: '1.5' }],
      'base': ['16px', { lineHeight: '1.6' }],
      'lg': ['18px', { lineHeight: '1.5' }],
      'xl': ['24px', { lineHeight: '1.4' }],
      '2xl': ['36px', { lineHeight: '1.3' }],
      '3xl': ['48px', { lineHeight: '1.2' }],
    },
    fontWeight: {
      'light': 300,
      'normal': 400,
      'medium': 500,
      'semibold': 600,
      'bold': 700,
      'extrabold': 800,
    },
    letterSpacing: {
      'tight': '-0.02em',
      'normal': '0em',
      'wide': '0.05em',
    },
  },
};
```

---

## 7. IMPORTACIÓN GOOGLE FONTS

```html
<!-- En el <head> del HTML -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Poppins:wght@500;600;700;800&family=JetBrains+Mono:wght@400;600&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
```

---

## 8. REGLAS DE TIPOGRAFÍA

### ✅ Qué Hacer

- ✅ Usar **máximo 3 familias tipográficas** en toda la app
- ✅ Mantener **contraste de color** (AA mínimo WCAG)
- ✅ Usar **line-height mínimo 1.5** para accesibilidad
- ✅ Respetar **jerarquía visual** clara
- ✅ Usar **font-weight para énfasis**, no tamaño
- ✅ Aplicar **tracking/letter-spacing** en títulos
- ✅ **Probar en dispositivos reales**

### ❌ Qué Evitar

- ❌ Usar más de 3 tipografías diferentes
- ❌ Textos menores a 12px (excepto metadata)
- ❌ Contrastar blanco sobre amarillo
- ❌ Usar cursiva para textos largos
- ❌ Abandonar la jerarquía visual
- ❌ Ignorar responsive en tipografía
- ❌ Usar todas las variaciones de peso simultáneamente

---

## 9. ACCESIBILIDAD TIPOGRÁFICA

### Contraste Mínimo (WCAG AA)
- **Texto normal**: Ratio 4.5:1
- **Texto grande** (18px+ o 14px bold+): Ratio 3:1

### Recomendaciones

```css
/* Bien */
color: #1F2937;        /* Gris oscuro sobre blanco = 18.4:1 ✅ */
background: #FFFFFF;

/* Evitar */
color: #9CA3AF;        /* Gris claro sobre blanco = 3.9:1 ❌ */
background: #FFFFFF;

/* Mejor para metadata */
color: #6B7280;        /* Gris sobre blanco = 7.7:1 ✅ */
background: #FFFFFF;
```

---

## 10. GUÍA DE ESTILO POR CONTEXTO

### Página de Inicio
```
H1: Poppins Bold 48px - Azul Principal
Tagline: Inter Regular 18px - Gris
CTA: Poppins Semibold 16px - Verde
```

### Perfil de Usuario
```
Nombre: Poppins Bold 20px - Azul Principal
Estado: Inter Semibold 14px - Verde/Amarillo
Descripción: Inter Regular 14px - Gris
```

### Card de Módulo
```
Título: Poppins Semibold 16px - Azul Principal
Descripción: Inter Regular 14px - Gris
Botón: Poppins Semibold 14px - Verde
```

### Modal / Diálogo
```
Encabezado: Poppins Bold 20px - Azul Principal
Contenido: Inter Regular 14px - Gris
Botones: Poppins Semibold 14px - Verde/Gris
```

---

## 11. EJEMPLO DE IMPLEMENTACIÓN HTML/CSS

```html
<div class="cv-container">
  <!-- Encabezado -->
  <header class="cv-header">
    <h1 class="cv-name">Juan Pérez García</h1>
    <p class="cv-title">Ingeniero de Software Senior</p>
    <div class="cv-contact">
      <span>📧 juan@example.com</span>
      <span>📱 +34 123 456 789</span>
    </div>
  </header>

  <!-- Sección de Experiencia -->
  <section class="cv-section">
    <h2 class="cv-section-title">Experiencia Profesional</h2>
    
    <div class="cv-job">
      <h3 class="cv-company">Tech Company XYZ</h3>
      <p class="cv-position">Senior Developer</p>
      <p class="cv-date">2020 - Presente</p>
      <ul class="cv-achievements">
        <li>Lideré equipo de 5 desarrolladores</li>
        <li>Implementé arquitectura microservicios</li>
      </ul>
    </div>
  </section>

  <!-- Sección de Competencias -->
  <section class="cv-section">
    <h2 class="cv-section-title">Competencias</h2>
    <div class="cv-skills">
      <div class="cv-skill">
        <span class="cv-skill-name">Python</span>
        <div class="cv-skill-bar">
          <div class="cv-skill-progress" style="width: 90%"></div>
        </div>
      </div>
    </div>
  </section>
</div>

<style>
  .cv-header {
    border-bottom: 2px solid #0052CC;
    padding-bottom: 16px;
    margin-bottom: 24px;
  }

  .cv-name {
    font-family: 'Poppins', sans-serif;
    font-size: 24px;
    font-weight: 700;
    color: #0052CC;
    margin: 0;
  }

  .cv-title {
    font-family: 'Poppins', sans-serif;
    font-size: 16px;
    font-weight: 600;
    color: #374151;
    margin: 8px 0;
  }

  .cv-section-title {
    font-family: 'Poppins', sans-serif;
    font-size: 16px;
    font-weight: 600;
    color: #1F2937;
    border-left: 4px solid #0052CC;
    padding-left: 12px;
    margin-bottom: 12px;
  }

  .cv-company {
    font-family: 'Inter', sans-serif;
    font-size: 14px;
    font-weight: 600;
    color: #1F2937;
    margin: 0;
  }

  .cv-position {
    font-family: 'Inter', sans-serif;
    font-size: 13px;
    font-weight: 500;
    color: #6B7280;
    margin: 4px 0;
  }

  .cv-achievements {
    font-family: 'Inter', sans-serif;
    font-size: 13px;
    color: #4B5563;
    line-height: 1.6;
    margin: 8px 0 0 0;
    padding-left: 20px;
  }
</style>
```

---

## 12. VARIABLES DE TIPOGRAFÍA (SCSS)

```scss
// Tipografía Principal
$font-display: 'Poppins', sans-serif;
$font-body: 'Inter', sans-serif;
$font-mono: 'JetBrains Mono', monospace;
$font-elegant: 'Lato', sans-serif;

// Tamaños
$size-h1: 48px;
$size-h2: 36px;
$size-h3: 24px;
$size-h4: 18px;
$size-body: 16px;
$size-small: 14px;

// Pesos
$weight-light: 300;
$weight-normal: 400;
$weight-medium: 500;
$weight-semibold: 600;
$weight-bold: 700;
$weight-extrabold: 800;

// Mixins
@mixin heading-1 {
  font-family: $font-display;
  font-size: $size-h1;
  font-weight: $weight-bold;
  line-height: 1.2;
  letter-spacing: -0.02em;
}

@mixin body-text {
  font-family: $font-body;
  font-size: $size-body;
  font-weight: $weight-normal;
  line-height: 1.6;
}
```

---

**Versión**: 1.0  
**Última actualización**: 2026-09-16  
**Autor**: App de Currículum Inteligente