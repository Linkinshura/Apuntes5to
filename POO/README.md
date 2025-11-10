# Programación Orientada a Objetos (POO)

## 1. ¿Qué es la POO?

La **Programación Orientada a Objetos (POO)** es un **paradigma de programación** que organiza el código en **objetos**, los cuales combinan **datos (atributos)** y **comportamientos (métodos)** relacionados.

Su objetivo principal es **modelar problemas del mundo real** en el software, representando entidades como “Persona”, “Auto”, “Usuario”, etc., a través de clases y objetos.

---

## 2. Conceptos principales

| Concepto | Descripción | Ejemplo (JavaScript) |
|-----------|--------------|----------------------|
| **Clase** | Es una plantilla o modelo que define las características y comportamientos de un tipo de objeto. | `class Persona { ... }` |
| **Objeto** | Es una instancia concreta de una clase. | `const persona1 = new Persona()` |
| **Atributo** | Son las propiedades o datos del objeto. | `this.nombre` |
| **Método** | Son las funciones que definen las acciones del objeto. | `saludar() { ... }` |
| **Constructor** | Método especial que se ejecuta al crear un objeto. | `constructor(nombre) { this.nombre = nombre }` |
| **Encapsulamiento** | Ocultar los datos internos de un objeto y permitir acceso controlado. | Métodos `get` y `set` |
| **Herencia** | Una clase puede heredar propiedades y métodos de otra. | `class Estudiante extends Persona` |
| **Polimorfismo** | Capacidad de redefinir métodos según el contexto. | Sobrescribir un método heredado |

---

## 3. Ejemplo básico en JavaScript

```javascript
// Definición de una clase
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre} y tengo ${this.edad} años.`);
  }
}

// Crear un objeto (instancia)
const persona1 = new Persona("Ian", 18);
persona1.saludar(); // Hola, soy Ian y tengo 18 años.
```

