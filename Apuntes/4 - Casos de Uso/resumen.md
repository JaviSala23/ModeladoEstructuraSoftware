
# 🧠 Apunte Completo: Casos de Uso en UML

## 🎯 Objetivo General
Comprender y aplicar el concepto de **Casos de Uso** dentro del modelado UML, como herramienta fundamental para representar los requisitos funcionales de un sistema desde la perspectiva del usuario.

---

## 1. ¿Qué es un Caso de Uso?

Un **caso de uso** representa una funcionalidad específica del sistema vista desde el exterior. Muestra cómo un **actor** (persona, otro sistema o entidad externa) interactúa con el sistema para lograr un objetivo de valor.

> ✅ *“Un caso de uso es una narrativa que describe cómo un actor interactúa con un sistema para alcanzar un objetivo concreto.”*

---

## 2. ¿Por qué utilizar Casos de Uso?

- Son fáciles de entender para los usuarios no técnicos.
- Promueven el diálogo entre el cliente y el equipo de desarrollo.
- Ayudan a descubrir y validar requisitos funcionales.
- Sirven como base para el diseño, desarrollo, pruebas y documentación.

---

## 3. Componentes de un Caso de Uso

### 🎭 Actor
Es quien inicia la interacción con el sistema. Puede ser:
- **Primario**: El que inicia el caso de uso (ej. Cliente).
- **Secundario**: Ayuda al sistema durante el proceso (ej. Base de datos externa).

### 🧩 Caso de Uso
Representa una unidad funcional del sistema. Tiene un **nombre** claro y representa una **interacción completa**.

### 🔗 Relaciones
- **Asociación**: Línea entre actor y caso de uso.
- **Include (`<<include>>`)**: Un caso de uso *siempre* incluye otro.
- **Extend (`<<extend>>`)**: Un caso de uso *puede* extender otro opcionalmente.
- **Generalización**: Herencia entre actores o entre casos de uso.

---

## 4. Diagrama de Casos de Uso

```plaintext
         +-----------------------------+
         |        Sistema de Ventas    |
         |                             |
         |   (1) Realizar Venta        |
         |   (2) Consultar Producto    |
         |   (3) Generar Reporte       |
         +-----------------------------+
             ^           ^
             |           |
           Cajero     Gerente
```

---

## 5. Estructura de un Caso de Uso (Formato Narrativo)

### 📄 Plantilla sugerida:

- **Nombre**: Reservar libro
- **Actores**: Usuario
- **Precondiciones**: El usuario está autenticado.
- **Flujo principal**:
  1. El usuario busca un libro.
  2. El sistema muestra disponibilidad.
  3. El usuario selecciona el libro.
  4. El sistema confirma la reserva.
- **Flujos alternativos**:
  - Si el libro no está disponible, muestra un mensaje de espera.
- **Postcondiciones**: El libro queda reservado para el usuario.

---

## 6. Buenas Prácticas

- Usar nombres claros y específicos (evitar "Gestionar todo").
- Describir desde el punto de vista del actor.
- No mezclar lógica interna del sistema con interacción del usuario.
- Dividir casos grandes en subcasos con `<<include>>` o `<<extend>>`.

---

## 7. Ejemplo de Caso de Uso Detallado

### 📘 Caso de Uso: Realizar Pedido

- **Actor Primario**: Cliente
- **Precondición**: El cliente está registrado y autenticado.
- **Flujo Principal**:
    1. El cliente selecciona productos.
    2. El sistema muestra el carrito actualizado.
    3. El cliente confirma el pedido.
    4. El sistema registra la orden y envía confirmación.
- **Flujos Alternativos**:
    - Si hay error en la conexión, muestra mensaje de error.
- **Postcondición**: El pedido queda registrado en el sistema.

---

## 8. Relación con Otros Diagramas UML

- Los **casos de uso** alimentan el desarrollo de diagramas de:
  - Actividad
  - Secuencia
  - Estados
  - Clases
- Permiten modelar de forma progresiva el comportamiento del sistema.

---

## 9. Herramientas para Diagramas UML

- **Draw.io**
- **StarUML**
- **Lucidchart**
- **Enterprise Architect**
- **Visual Paradigm**
- **PlantUML** (para generar desde texto)

---

## 🧪 Actividades de Repaso

1. Dibujar un diagrama de casos de uso para un sistema de inscripción a materias.



---

## 📌 Cierre

Los **Casos de Uso** permiten comunicar claramente qué se espera que haga el sistema. Son una herramienta de modelado fundamental para entender y definir los requisitos funcionales en etapas tempranas del desarrollo.

