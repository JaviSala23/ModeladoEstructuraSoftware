# 🐍 Guía Avanzada: Programación Orientada a Objetos en Python

## 📚 Índice
1. [Conceptos Fundamentales](#conceptos-fundamentales)
2. [Decoradores en Python](#decoradores-en-python)
3. [Clases y Objetos en Profundidad](#clases-y-objetos-en-profundidad)
4. [Herencia y Composición](#herencia-y-composición)
5. [Encapsulamiento y Propiedades](#encapsulamiento-y-propiedades)
6. [Métodos Especiales](#métodos-especiales)
7. [Patrones Avanzados](#patrones-avanzados)

## Conceptos Fundamentales

### ¿Qué es una Clase?
Una clase es un plano o plantilla para crear objetos. Define un conjunto de atributos y métodos que determinarán el estado y comportamiento de los objetos creados a partir de ella.

```python
class Coche:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo
```

### Tipos de Atributos y Métodos
1. **Atributos de instancia**: Específicos para cada objeto
2. **Atributos de clase**: Compartidos por todas las instancias
3. **Métodos de instancia**: Operan sobre un objeto específico
4. **Métodos de clase**: Operan sobre la clase misma
5. **Métodos estáticos**: No dependen de la instancia ni de la clase

## Decoradores en Python

### ¿Qué son los Decoradores?
Los decoradores son un patrón de diseño que permite modificar o extender el comportamiento de funciones o métodos sin modificar su código directamente. En Python, se indican con el símbolo `@`.

### Decoradores Comunes en POO

#### 1. @classmethod
```python
class Coche:
    _total_coches = 0
    
    @classmethod
    def obtener_total_coches(cls):
        return cls._total_coches
```
- **¿Por qué usarlo?**
  - Permite trabajar con atributos de clase
  - Puede ser usado como constructor alternativo
  - Recibe la clase como primer argumento (cls)
  - No necesita una instancia para ser llamado

#### 2. @staticmethod
```python
class Coche:
    @staticmethod
    def convertir_km_a_millas(km):
        return km * 0.621371
```
- **¿Por qué usarlo?**
  - Para funciones que no necesitan acceder a atributos de instancia o clase
  - Útil para operaciones auxiliares relacionadas con la clase
  - No recibe automáticamente self ni cls
  - Mejora la organización del código

#### 3. @property
```python
class Coche:
    def __init__(self, velocidad):
        self._velocidad = velocidad
    
    @property
    def velocidad(self):
        return self._velocidad
    
    @velocidad.setter
    def velocidad(self, valor):
        if valor < 0:
            raise ValueError("La velocidad no puede ser negativa")
        self._velocidad = valor
```
- **¿Por qué usarlo?**
  - Permite acceder a métodos como si fueran atributos
  - Facilita la validación de datos
  - Implementa el encapsulamiento de manera elegante
  - Permite cambiar la implementación sin afectar el código cliente

## Clases y Objetos en Profundidad

### Ejemplo Completo
```python
class Vehiculo:
    # Atributo de clase
    contador_vehiculos = 0
    
    def __init__(self, marca, modelo, velocidad_max=200):
        # Atributos de instancia
        self._marca = marca
        self._modelo = modelo
        self._velocidad_actual = 0
        self._velocidad_max = velocidad_max
        Vehiculo.contador_vehiculos += 1
    
    @property
    def velocidad_actual(self):
        return self._velocidad_actual
    
    @velocidad_actual.setter
    def velocidad_actual(self, velocidad):
        if 0 <= velocidad <= self._velocidad_max:
            self._velocidad_actual = velocidad
        else:
            raise ValueError("Velocidad fuera de rango")
    
    @classmethod
    def crear_deportivo(cls, marca):
        """Constructor alternativo para crear vehículos deportivos"""
        return cls(marca, "Deportivo", velocidad_max=300)
    
    @staticmethod
    def es_velocidad_segura(velocidad):
        """Verifica si una velocidad es segura"""
        return velocidad <= 120

    def acelerar(self, incremento):
        """Método de instancia para acelerar el vehículo"""
        nueva_velocidad = self._velocidad_actual + incremento
        self.velocidad_actual = nueva_velocidad
```

## Herencia y Composición

### Herencia Múltiple
```python
class VehiculoTerrestre:
    def moverse(self):
        return "Rodando por tierra"

class VehiculoAnfibio:
    def nadar(self):
        return "Navegando en agua"

class CarroAnfibio(VehiculoTerrestre, VehiculoAnfibio):
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo
```

### Composición
```python
class Motor:
    def __init__(self, tipo, potencia):
        self.tipo = tipo
        self.potencia = potencia

class Coche:
    def __init__(self, marca, modelo, tipo_motor, potencia_motor):
        self.marca = marca
        self.modelo = modelo
        self.motor = Motor(tipo_motor, potencia_motor)
```

## Encapsulamiento y Propiedades

### Niveles de Acceso
```python
class CuentaBancaria:
    def __init__(self):
        self.saldo_publico = 0      # Público
        self._saldo = 0             # Protegido
        self.__saldo_secreto = 0    # Privado
```

### Properties Avanzadas
```python
class Temperatura:
    def __init__(self):
        self._celsius = 0
    
    @property
    def celsius(self):
        return self._celsius
    
    @celsius.setter
    def celsius(self, valor):
        self._celsius = valor
    
    @property
    def fahrenheit(self):
        return (self._celsius * 9/5) + 32
    
    @fahrenheit.setter
    def fahrenheit(self, valor):
        self._celsius = (valor - 32) * 5/9
```

## Métodos Especiales

### Métodos Mágicos Comunes
```python
class Libro:
    def __init__(self, titulo, autor):
        self.titulo = titulo
        self.autor = autor
    
    def __str__(self):
        """Representación en string para usuarios"""
        return f"{self.titulo} por {self.autor}"
    
    def __repr__(self):
        """Representación en string para desarrolladores"""
        return f"Libro(titulo='{self.titulo}', autor='{self.autor}')"
    
    def __len__(self):
        """Retorna la longitud del título"""
        return len(self.titulo)
    
    def __eq__(self, otro):
        """Compara dos libros"""
        if not isinstance(otro, Libro):
            return False
        return self.titulo == otro.titulo and self.autor == otro.autor
```

## Patrones Avanzados

### Singleton
```python
class Singleton:
    _instancia = None
    
    def __new__(cls):
        if cls._instancia is None:
            cls._instancia = super().__new__(cls)
        return cls._instancia
```

### Factory Method
```python
class CreadorVehiculo:
    @staticmethod
    def crear_vehiculo(tipo):
        if tipo == "coche":
            return Coche()
        elif tipo == "moto":
            return Moto()
        else:
            raise ValueError("Tipo de vehículo no soportado")
```

### 🎯 Ejercicios Prácticos

1. Crear una clase `Biblioteca` que use diferentes tipos de decoradores
2. Implementar un sistema de vehículos usando herencia múltiple
3. Crear una clase con properties que convierta diferentes unidades de medida
4. Implementar un patrón Singleton para un sistema de logging

### 📚 Referencias y Recursos Adicionales
- [Python Documentation - Classes](https://docs.python.org/3/tutorial/classes.html)
- [Python Documentation - Decorators](https://docs.python.org/3/glossary.html#term-decorator)
- [Python Documentation - Special Method Names](https://docs.python.org/3/reference/datamodel.html#special-method-names)
