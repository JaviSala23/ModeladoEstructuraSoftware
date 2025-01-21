Principios SOLID 🧱

Los principios SOLID son un conjunto de cinco reglas fundamentales en el diseño de software orientado a objetos que buscan hacer el código más mantenible, flexible y fácil de entender. Cada letra representa un principio que guía la estructura y el comportamiento de las clases y objetos.
Principio de Responsabilidad Única (SRP) 🧩

    Definición: Una clase debe tener una, y solo una, razón para cambiar, lo que significa que debe tener una única responsabilidad.
    Propósito: Simplificar el diseño manteniendo cada clase enfocada en una única tarea.
    Ejemplo: En una aplicación de ventas, una clase GestorDeVentas debería encargarse solo de calcular ventas, y no de enviar facturas o administrar inventario.

Principio de Abierto/Cerrado (OCP) 🔓🚫

    Definición: Las entidades de software (clases, módulos, funciones, etc.) deben estar abiertas para la extensión, pero cerradas para la modificación.
    Propósito: Facilitar la extensión de funcionalidad sin modificar el código existente, reduciendo riesgos de errores en el código estable.
    Ejemplo: Si tienes una clase CalculadoraDeImpuestos, puedes extenderla para soportar nuevos tipos de impuestos mediante la herencia o composición, sin modificar la lógica original.

Principio de Sustitución de Liskov (LSP) 🔄

    Definición: Los objetos de una clase derivada deben poder sustituir a los objetos de una clase base sin alterar el comportamiento del programa.
    Propósito: Mantener la interoperabilidad y previsibilidad del sistema, permitiendo que las subclases se usen de forma intercambiable con las clases padre.
    Ejemplo: Si tienes una clase base Ave y una subclase Pato, el Pato debería comportarse como un Ave sin causar errores inesperados.

Principio de Segregación de Interfaces (ISP) ✂️

    Definición: Ningún cliente debe verse obligado a depender de métodos que no utiliza.
    Propósito: Crear interfaces específicas y evitar interfaces monolíticas que obliguen a las clases a implementar métodos que no necesitan.
    Ejemplo: En lugar de tener una interfaz Trabajador con métodos como escribirInforme, realizarMantenimiento, y supervisar, es mejor dividirla en interfaces específicas como Escritor, Mantenimiento, y Supervisor.

Principio de Inversión de Dependencias (DIP) 🔄🔌

    Definición: Los módulos de alto nivel no deben depender de módulos de bajo nivel; ambos deben depender de abstracciones. Además, las abstracciones no deben depender de los detalles, sino que los detalles deben depender de las abstracciones.
    Propósito: Aumentar la flexibilidad del sistema al desacoplar módulos de alto y bajo nivel.
    Ejemplo: En lugar de que una clase ControladorDePagos dependa de una clase concreta ServicioDePaypal, se podría definir una interfaz ServicioDePago que sea implementada tanto por ServicioDePaypal como por ServicioDeStripe.

Conclusión 📜

Los principios SOLID son herramientas poderosas para mejorar la calidad del diseño orientado a objetos, promoviendo un código más modular, fácil de mantener y menos propenso a errores. Al seguir estos principios, se facilita la colaboración en equipo y se potencia la escalabilidad del software.




[🎥 Video Explicativo](https://www.youtube.com/watch?v=g1shhx5Nvv8)


[📘 Link con Apuntes](https://www.freecodecamp.org/espanol/news/los-principios-solid-explicados-en-espanol/)


