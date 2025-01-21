# 💪 Requisito de Software: Sistema de Gestión de Gimnasio

## 📝 Descripción General

El sistema de gestión de gimnasio permitirá a los usuarios (clientes y administradores) reservar clases, gestionar su perfil, pagar membresías y hacer seguimiento de su historial de actividades.

## ⚙️ Funcionalidades

### 1. 👤 Registro de Usuarios:
- Los usuarios podrán registrarse con su información personal: nombre, correo electrónico, teléfono, tipo de membresía.
- Los usuarios tendrán que elegir un nombre de usuario y una contraseña para acceder al sistema.

### 2. 🏋️‍♂️ Reserva de Clases:
- Los usuarios podrán visualizar el calendario de clases disponibles (yoga, crossfit, spinning, etc.).
- Podrán reservar una clase seleccionando la fecha, hora y entrenador.
- Los administradores podrán crear, modificar y eliminar clases del calendario.

### 3. 👥 Gestión de Perfil:
- Los usuarios podrán actualizar su información personal y ver el estado de su membresía (activa o inactiva).
- Los administradores podrán gestionar la información de los usuarios.

### 4. 📊 Historial de Actividades:
- Los usuarios podrán visualizar su historial de clases reservadas y asistencias.
- Podrán ver el progreso físico registrado, como peso, porcentaje de grasa corporal, y mejoras en los ejercicios.

### 5. 💳 Pago de Membresía:
- Los usuarios podrán pagar sus membresías a través de diferentes métodos de pago.
- El sistema deberá enviar notificaciones cuando la membresía esté a punto de expirar. ⏰

---

# 📚 Consigna de Trabajo Práctico

## 🎯 Objetivo
Crear un **diagrama de casos de uso** y un **diagrama de clases** correspondientes al sistema de gestión de gimnasio.

## 🔧 Instrucciones

### Parte 1: 🔄 Diagramas

1. **Diagrama de Casos de Uso**:
   - Identificar los actores principales. 👥
   - Definir los casos de uso para cada uno de los actores siguiendo las funcionalidades del sistema.
   - Utilizar una herramienta como Hazo o cualquier otro software para crear el diagrama.

2. **Diagrama de Clases**:
   - Crear un diagrama de clases que incluya:
     - Las clases principales. 🏷️
     - Atributos principales de cada clase.
     - Relaciones entre las clases (asociaciones, herencias si es necesario).
   - ⚠️ **Recuerda** utilizar las convenciones correctas (ej. las relaciones de "uno a muchos" y "muchos a muchos" donde corresponda).

### Parte 2: 💻 Programación de Clases

1. **Estructura de las Clases**:
   - Crear las clases en código Python con su estructura básica:
     - Definir los **atributos** en cada clase. 📋
     - Crear los **métodos** o **funciones** que realizarán las operaciones correspondientes.
     - ⚠️ **Recuerda**: en cada método, coloca `pass` ya que la funcionalidad se agregará más tarde.
     - ❗ **No olvides el constructor** (`__init__`) para inicializar los atributos de las clases.

### Ejemplo de Clase en Python:

```python
class Usuario:
    def __init__(self, nombre, email, telefono, tipo_membresia):
        self.nombre = nombre
        self.email = email
        self.telefono = telefono
        self.tipo_membresia = tipo_membresia
    
    def actualizar_perfil(self):
        pass
    
    def ver_historial(self):
        pass


```
>[!NOTE]
💡 No olvides prestar atención a la correcta estructuración de las clases y métodos.🧠
## 🚀Entrega;
   - Subir los archivos de los diagramas (como imagen o PDF). 🖼️
   - Subir el código con la estructura de clases en un archivo .py. 💾
