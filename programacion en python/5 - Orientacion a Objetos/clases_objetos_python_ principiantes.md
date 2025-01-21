
# 🐍 Explicación Sencilla: Clases y Objetos en Python

## 📖 ¿Qué es una Clase?

Una **clase** es un plano o plantilla que define las propiedades y comportamientos de un tipo de objeto. En Python, las clases permiten organizar datos y funciones en una estructura lógica.

```python
class Coche:
    def __init__(self, marca, modelo):
        self.marca = marca  # Propiedad (atributo)
        self.modelo = modelo  # Propiedad (atributo)

    def acelerar(self):
        print(f"El {self.marca} {self.modelo} está acelerando.")  # Método (función)
```

En este ejemplo:
- `Coche` es la clase.
- El método `__init__` es el **constructor** que se ejecuta cuando creamos un objeto.
- `marca` y `modelo` son **atributos**.
- `acelerar` es un **método** (una función que pertenece a la clase).

---

## 🚗 ¿Qué es un Objeto?

Un **objeto** es una instancia de una clase. Cuando creamos un objeto, estamos creando algo basado en la plantilla de la clase.

```python
mi_coche = Coche("Toyota", "Corolla")  # Creamos un objeto de la clase Coche
mi_coche.acelerar()  # Llamamos al método 'acelerar' del objeto
```

Aquí, `mi_coche` es un objeto basado en la clase `Coche`. Utiliza el método `acelerar` que muestra el mensaje: 
`El Toyota Corolla está acelerando.`

---

## 🔑 Conceptos Clave:

1. **Atributos:** Son las propiedades de un objeto (como `marca` y `modelo` en el ejemplo anterior).
2. **Métodos:** Son las funciones que pueden ejecutar los objetos (como `acelerar`).
3. **Objetos:** Son instancias de una clase. Puedes crear múltiples objetos a partir de la misma clase.

```python
coche1 = Coche("Honda", "Civic")
coche2 = Coche("Ford", "Fiesta")

coche1.acelerar()  # El Honda Civic está acelerando.
coche2.acelerar()  # El Ford Fiesta está acelerando.
```

---

## 🎯 Resumen

- Una clase es un plano que define los atributos y métodos.
- Un objeto es una instancia de una clase.
- Puedes crear múltiples objetos a partir de una clase, cada uno con sus propios valores de atributos.
