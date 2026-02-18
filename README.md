# Claude CLI Complete Guide 🚀

Guía técnica profesional para instalar y utilizar Claude CLI desde cero.

Este repositorio está enfocado en desarrolladores, arquitectos y profesionales que desean integrar Claude en flujos de trabajo locales y automatizados.

---

## 📌 ¿Qué es Claude CLI?

Claude CLI es la interfaz de línea de comandos oficial para interactuar con Claude, el modelo de lenguaje desarrollado por Anthropic.

Claude es un modelo avanzado diseñado para:

- Generación de texto
- Análisis técnico
- Escritura de código
- Automatización
- Procesamiento de documentos
- Integraciones en pipelines DevOps

Sitio oficial:
https://www.anthropic.com

Documentación:
https://docs.anthropic.com

---

## 🎯 ¿Para qué sirve?

- Consultas técnicas rápidas desde terminal
- Generación de código
- Automatización en scripts
- Integración en CI/CD
- Análisis de archivos
- Refactorización asistida
- Documentación automática

---

## 🏗 Arquitectura de Funcionamiento

Terminal
↓
Claude CLI
↓
API de Anthropic
↓
Modelo Claude


La CLI actúa como cliente que se autentica mediante API Key.

---

## 💻 Requisitos

- Node.js 18+
- npm o yarn
- Cuenta en Anthropic
- API Key válida

---

## 🛠 Instalación

### 1️⃣ Instalar Node.js

Descargar desde:
https://nodejs.org

Verificar:

node -v
npm -v


---

### 2️⃣ Instalar Claude CLI

npm install -g @anthropic-ai/claude-cli


Verificar:

claude --help


---

## 🔐 Configuración de API Key

1. Ingresar a Anthropic Console
2. Generar una API Key
3. Configurar variable de entorno

### Windows (PowerShell)

setx ANTHROPIC_API_KEY "tu_api_key"


### Linux / Mac

export ANTHROPIC_API_KEY="tu_api_key"


Verificar:

echo $ANTHROPIC_API_KEY


---

## ▶️ Uso Básico

Ejemplo:

claude "Explica qué es una arquitectura basada en eventos"


---

## 🌎 Cómo poner Claude CLI en Español

Claude responde en el idioma del prompt.

### Opción 1: Especificar idioma en cada prompt

claude "Responde en español: Explica qué es una arquitectura hexagonal"


---

### Opción 2: Crear alias permanente en Español

Linux / Mac:

alias claude-es='claude "Responde siempre en español de forma técnica y clara:"'


Luego:

claude-es "Explica qué es CQRS"


---

### Opción 3: Script Wrapper Profesional

Crear archivo `claude-es.sh`:

#!/bin/bash
claude "Responde en español técnico profesional: $1"


Dar permisos:

chmod +x claude-es.sh


---

## ⚙ Configuración Avanzada

- Definir modelo específico
- Ajustar temperatura
- Limitar tokens
- Integrar con scripts bash
- Usar redirección de archivos

Ejemplo con archivo:

claude "Analiza el siguiente código:" < app.py


---

## 🔁 Automatización

Ejemplo en bash:

for file in *.py; do
claude "Documenta este archivo:" < "$file"
done


---

## 🛡 Buenas Prácticas

- No subir API Key al repositorio
- Usar .env
- Rotar credenciales periódicamente
- Limitar permisos de la API

---

## 🚀 Casos de Uso Profesionales

- Generación de documentación
- Revisión de código automática
- Asistente DevOps
- Auditoría básica de seguridad
- Generación de tests unitarios

---

## 📄 Licencia

MIT — contribuciones bienvenidas 🚀

---

## 👨‍💻 Desarrollado por Isaac Esteban Haro Torres

**Ingeniero en Sistemas · Full Stack · Automatización · Data**

- 📧 Email: zackharo1@gmail.com
- 📱 WhatsApp: 098805517
- 💻 GitHub: https://github.com/ieharo1
- 🌐 Portafolio: https://ieharo1.github.io/portafolio-isaac.haro/

---

© 2026 Isaac Esteban Haro Torres - Todos los derechos reservados.
