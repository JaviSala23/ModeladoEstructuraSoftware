
# 🐍 Guía Experta: Programación Orientada a Objetos en Python

## 📑 Índice
1. [Fundamentos Avanzados](#fundamentos-avanzados)
2. [Patrones de Diseño y Mejores Prácticas](#patrones-de-diseño-y-mejores-prácticas)
3. [Metaprogramación y Decoradores](#metaprogramación-y-decoradores)
4. [Gestión Avanzada de Memoria](#gestión-avanzada-de-memoria)
5. [Protocolos y Métodos Especiales](#protocolos-y-métodos-especiales)
6. [Concurrencia y POO](#concurrencia-y-poo)

---

## 🎯 Fundamentos Avanzados

### Descriptores y Control de Atributos

Los **descriptores** permiten personalizar el acceso y la manipulación de atributos en las clases. Esta es una característica avanzada que te da control sobre el comportamiento de atributos individuales cuando se acceden, asignan o eliminan.

```python
class Validador:
    """Descriptor que valida el valor de un atributo"""
    def __init__(self, minimo=None, maximo=None):
        self.minimo = minimo
        self.maximo = maximo
        self._nombre = None

    def __set_name__(self, owner, name):
        self._nombre = name

    def __get__(self, instance, owner):
        if instance is None:
            return self
        return instance.__dict__.get(self._nombre)

    def __set__(self, instance, value):
        if self.minimo is not None and value < self.minimo:
            raise ValueError(f"{self._nombre} no puede ser menor que {self.minimo}")
        if self.maximo is not None and value > self.maximo:
            raise ValueError(f"{self._nombre} no puede ser mayor que {self.maximo}")
        instance.__dict__[self._nombre] = value
```

Este código crea un descriptor que controla los valores permitidos para atributos específicos, lanzando excepciones si los valores asignados están fuera de los límites definidos. En la clase `Coche`, se utilizan descriptores para validar `velocidad` y `año`.

```python
class Coche:
    velocidad = Validador(0, 300)  # Velocidad entre 0 y 300 km/h
    año = Validador(1886, 2024)    # Año entre 1886 y 2024

    def __init__(self, velocidad, año):
        self.velocidad = velocidad
        self.año = año
```

### Slots y Optimización de Memoria

Los **slots** son una técnica de optimización en Python que restringe los atributos permitidos en una clase, lo que resulta en una menor huella de memoria.

```python
class CocheOptimizado:
    __slots__ = ['marca', 'modelo', 'velocidad']  # Restringe y optimiza atributos
    
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo
        self.velocidad = 0
```

Al utilizar `__slots__`, se evita la creación de un diccionario para cada instancia de la clase, lo que reduce el consumo de memoria.

---

## 🏗️ Patrones de Diseño y Mejores Prácticas

### Patrón Singleton con Metaclase

El **Patrón Singleton** garantiza que una clase solo tenga una instancia en todo momento. Con metaclases, puedes controlar la creación de instancias de clases, lo que permite implementar este patrón de manera elegante.

```python
class Singleton(type):
    _instances = {}
    
    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]

class ConfiguracionGlobal(metaclass=Singleton):
    def __init__(self):
        self.debug = False
        self.host = 'localhost'
        self.puerto = 8000
```

---

## 🔄 Metaprogramación y Decoradores

### Decorador de Clase con Parámetros

Los **decoradores de clase** permiten modificar el comportamiento de las clases completas. En este caso, se usa para registrar el tiempo de ejecución de métodos que superen un umbral específico.

```python
from functools import wraps
import time
from typing import Type, TypeVar, Callable

T = TypeVar('T')

def registrar_tiempo_ejecucion(umbral: float = 0.0):
    def decorador(cls: Type[T]) -> Type[T]:
        class ClaseWrapper(cls):
            def __getattribute__(self, name):
                attr = super().__getattribute__(name)
                if callable(attr):
                    @wraps(attr)
                    def wrapper(*args, **kwargs):
                        inicio = time.time()
                        resultado = attr(*args, **kwargs)
                        tiempo_total = time.time() - inicio
                        if tiempo_total > umbral:
                            print(f"¡Advertencia! {cls.__name__}.{name} "
                                  f"tardó {tiempo_total:.2f} segundos")
                        return resultado
                    return wrapper
                return attr
        return ClaseWrapper
    return decorador
```

---

## 🧮 Gestión Avanzada de Memoria

### Context Managers Personalizados

Los **context managers** permiten la gestión eficiente de recursos, asegurando que se liberen correctamente incluso si ocurre una excepción. Python permite definir context managers personalizados mediante `__enter__` y `__exit__`, o utilizando decoradores como `@contextmanager`.

```python
class RecursoBase:
    def __init__(self, nombre: str):
        self.nombre = nombre
        self._recurso: Optional[str] = None

    def inicializar(self) -> None:
        print(f"Inicializando recurso {self.nombre}")
        self._recurso = f"Recurso_{self.nombre}"

    def liberar(self) -> None:
        print(f"Liberando recurso {self.nombre}")
        self._recurso = None
```

```python
@contextlib.contextmanager
def administrar_recurso(nombre: str):
    recurso = RecursoBase(nombre)
    try:
        recurso.inicializar()
        yield recurso
    finally:
        recurso.liberar()
```

---

## 📜 Protocolos y Métodos Especiales

### Implementación de Protocolos

Un protocolo define un conjunto de métodos que una clase debe implementar. Aquí, `ListaCircular` es una clase que implementa el protocolo `Sequence`, lo que permite que la clase actúe como una lista circular.

```python
class ListaCircular(Sequence):
    def __init__(self, datos: Iterable[Any]):
        self._datos = list(datos)
        
    def __len__(self) -> int:
        return len(self._datos)
    
    def __getitem__(self, indice: int) -> Any:
        return self._datos[indice % len(self)]
```

---

## 🔄 Concurrencia y POO

### Patrones de Concurrencia

La concurrencia en Python puede lograrse utilizando **bloqueos** y compartiendo datos de manera segura entre hilos con `Lock`.

```python
from threading import Lock

class Compartido:
    def __init__(self, valor):
        self._valor = valor
        self._lock = Lock()

    def obtener(self):
        with self._lock:
            return self._valor
```

--- 

## 🎓 Ejercicios de Nivel Experto
- Implementa un sistema de caché thread-safe con expiración de elementos.
- Crea un ORM simple usando metaclases y descriptores.
- Desarrolla un sistema de plugins usando importación dinámica.
- Implementa un pool de conexiones con límite de recursos.
- Crea un decorador que implemente retry con backoff exponencial.

## 📚 Recursos y Referencias Avanzadas

- Python Data Model
- Python Type Hints
- Python Design Patterns
- Python Descriptors
- Python Metaclasses
