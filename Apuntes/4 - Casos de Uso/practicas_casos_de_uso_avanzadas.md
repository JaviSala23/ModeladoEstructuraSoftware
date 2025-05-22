
# 🔧 Prácticas Avanzadas de Casos de Uso en UML

Estas actividades están pensadas para estudiantes con conocimientos básicos ya adquiridos en modelado UML, que buscan practicar situaciones más complejas con múltiples actores, relaciones y organización modular.

---

## 🔷 Práctica 1: Plataforma de Cursos Online

**Escenario**: Una plataforma similar a Udemy o Coursera.

**Consigna**:
- El estudiante puede:
  - Registrarse
  - Ver catálogo de cursos
  - Inscribirse a un curso
  - Completar evaluaciones
  - Obtener certificado (`<<extend>>` si aprueba)

- El docente puede:
  - Crear cursos
  - Cargar contenido y evaluaciones
  - Ver resultados de estudiantes

- El administrador puede:
  - Aprobar cursos creados
  - Gestionar usuarios

> Usar `<<include>>` para registrar log de actividad.
> Usar `<<extend>>` para enviar notificaciones automáticas.

---

## 🔷 Práctica 2: Sistema Integral de Hospital

**Escenario**: Hospital moderno con acceso digital para usuarios y personal.

**Consigna**:
- El paciente puede:
  - Iniciar sesión
  - Solicitar turno
  - Consultar historia clínica (`<<include>>`)

- El médico puede:
  - Ingresar al sistema
  - Atender pacientes
  - Cargar evolución médica
  - Derivar a otros especialistas (`<<extend>>`)

- El laboratorio puede:
  - Ver pedidos de estudios
  - Cargar resultados

- El sistema puede generar alertas si el resultado es crítico (`<<extend>>`).

---

## 🔷 Práctica 3: Sistema de Gestión de Proyectos

**Escenario**: Una empresa de desarrollo de software.

**Consigna**:
- El project manager puede:
  - Crear proyectos
  - Asignar tareas
  - Generar informes

- El desarrollador puede:
  - Ver tareas asignadas
  - Registrar avance
  - Reportar bugs

- El cliente puede:
  - Ver progreso de su proyecto
  - Aceptar entregas (`<<extend>>` si cumple criterios)
  - Solicitar cambios (`<<extend>>`)

> Incorporar herencia entre actores: “Usuario” general, con especializaciones “Cliente”, “PM”, “Desarrollador”.

---

## 🔷 Práctica 4: Sistema Bancario Multicanal

**Escenario**: Un banco moderno con múltiples canales de acceso (web, app, cajero).

**Consigna**:
- El cliente puede:
  - Iniciar sesión desde múltiples dispositivos
  - Consultar saldos
  - Realizar transferencias
  - Solicitar préstamos (`<<extend>>` si cumple condiciones)

- El sistema incluye:
  - Validación de identidad (`<<include>>`)
  - Notificación por correo o SMS (`<<extend>>`)
  - Análisis de riesgo automatizado

- El operador de atención puede:
  - Acceder a los casos de clientes
  - Bloquear cuentas
  - Generar reportes regulatorios

> Considerar casos comunes para todos los canales con herencia en actores.

---

## 🧩 Desafío Extra

Elegí uno de los sistemas anteriores y combiná **casos de uso narrativos** (formato texto) con **diagramas gráficos**. Justificá el uso de cada relación (`include`, `extend`, `generalization`) con ejemplos claros.

---

## 🛠️ Herramientas Sugeridas

- [Draw.io](https://draw.io)
- [StarUML](https://staruml.io)
- [Lucidchart](https://lucidchart.com)
- [PlantUML](https://plantuml.com)

