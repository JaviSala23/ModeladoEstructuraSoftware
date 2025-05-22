
# 🧪 Prácticas Iniciales de Casos de Uso en UML

Estas actividades están diseñadas para estudiantes que recién comienzan con el modelado UML. Cada práctica propone un caso sencillo para representar mediante **diagramas de casos de uso**.

---

## 🟢 Práctica 1: Sistema de Cajero Automático

**Objetivo**: Identificar actores y casos de uso simples.

**Consigna**: Dibuja un diagrama de casos de uso para un cajero automático que permita a un cliente:

- Ingresar su tarjeta.
- Ver saldo.
- Retirar dinero.
- Cambiar su PIN.

> **Desafío adicional**: Agregá un actor secundario encargado del mantenimiento del cajero.

---

## 🟢 Práctica 2: Sistema de Biblioteca Escolar

**Objetivo**: Usar relaciones de inclusión y extensión (`<<include>>` / `<<extend>>`).

**Consigna**: Modelá los siguientes casos de uso:

- Un alumno puede **buscar libros** y **reservar libros**.
- Un bibliotecario puede **registrar devoluciones** y **agregar nuevos libros**.
- Toda **reserva de libro** debe incluir la verificación de disponibilidad (`<<include>>`).
- Si el alumno tiene libros vencidos, se le muestra una advertencia (`<<extend>>`).

---

## 🟢 Práctica 3: Sistema de Gestión de Turnos Médicos

**Objetivo**: Representar múltiples actores y casos de uso realistas.

**Consigna**:

- El paciente puede:
  - Registrarse
  - Pedir turno
  - Consultar sus turnos

- El médico puede:
  - Consultar agenda
  - Marcar asistencia

- El recepcionista puede:
  - Crear pacientes
  - Agendar turnos
  - Cancelar turnos

> Considerá usar **generalización de actores** si lo creés necesario.

---

## 🟢 Práctica 4: Sistema de Delivery Online

**Objetivo**: Integrar relaciones `<<include>>`, `<<extend>>` y varios actores.

**Consigna**:

- El cliente puede:
  - Ver menú
  - Realizar pedido
  - Pagar

- El repartidor puede:
  - Ver pedidos asignados
  - Marcar como entregado

- El administrador puede:
  - Gestionar menú
  - Ver estadísticas

- El pago debe incluir `<<include>>` para verificar el método de pago y confirmar operación.
- Puede haber `<<extend>>` si el cliente aplica un cupón de descuento.

---

## ✍️ Recomendación

Estas prácticas pueden resolverse a mano o con herramientas como:
- [Draw.io](https://draw.io)
- [Lucidchart](https://lucidchart.com)
- [StarUML](https://staruml.io)
- [PlantUML](https://plantuml.com)

