# Herencia en la Programación Orientada a Objetos (POO)

## 1. ¿Qué es la herencia?

La **herencia** es un principio fundamental de la **Programación Orientada a Objetos (POO)** que permite que **una clase (hija o derivada)** herede atributos y métodos de **otra clase (padre o base)**.

Gracias a la herencia:
- Se **reutiliza código**.
- Se evitan repeticiones.
- Se puede **extender o modificar** el comportamiento de una clase sin alterar la original.

---

## 2. Conceptos clave

| Término | Descripción | Ejemplo |
|----------|--------------|---------|
| **Clase padre (superclase)** | La clase original que contiene propiedades y métodos comunes. | `class Persona { ... }` |
| **Clase hija (subclase)** | La clase que hereda de otra. Puede tener nuevos métodos o redefinir los heredados. | `class Estudiante extends Persona { ... }` |
| **Palabra clave `extends`** | Indica que una clase hereda de otra. | `class Hija extends Padre` |
| **Palabra clave `super`** | Permite acceder al constructor o métodos de la clase padre. | `super(nombre, edad)` |

---

## 3. Ejemplo básico en JavaScript

```javascript
// Clase padre
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }

  presentarse() {
    console.log(`Soy ${this.nombre} y tengo ${this.edad} años.`);
  }
}

// Clase hija que hereda de Persona
class Estudiante extends Persona {
  constructor(nombre, edad, carrera) {
    super(nombre, edad); // Llama al constructor de la clase padre
    this.carrera = carrera;
  }

  estudiar() {
    console.log(`${this.nombre} está estudiando ${this.carrera}.`);
  }
}

// Crear una instancia
const estudiante1 = new Estudiante("Ian", 19, "Programación");
estudiante1.presentarse(); // Método heredado
estudiante1.estudiar();    // Método propio
```

## Herencia Multinivel

Una clase puede heredar de otra que a su vez hereda de otra.
Esto se llama herencia en cadena o multinivel.

```javascript
class SerVivo {
  respirar() {
    console.log("Respirando...");
  }
}

class Animal extends SerVivo {
  mover() {
    console.log("El animal se mueve.");
  }
}

class Ave extends Animal {
  volar() {
    console.log("El ave está volando.");
  }
}

const pajaro = new Ave();
pajaro.respirar(); // Heredado de SerVivo
pajaro.mover();    // Heredado de Animal
pajaro.volar();    // Propio de Ave
```
