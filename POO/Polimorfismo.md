# Polimorfismo en la Programación Orientada a Objetos (POO)

## 1. ¿Qué es el polimorfismo?

El **polimorfismo** es uno de los **pilares fundamentales de la Programación Orientada a Objetos (POO)**.  
Proviene del griego *“poly” (muchos)* y *“morphos” (formas)*, y significa **“muchas formas”**.

En programación, el polimorfismo permite que **un mismo método o función se comporte de distintas maneras**, dependiendo del **objeto que lo utilice**.

Es decir, **diferentes clases pueden compartir un mismo método**, pero **cada una puede tener su propia implementación**.

---

## 2. Objetivo del polimorfismo

| Objetivo | Descripción |
|-----------|--------------|
| **Reutilización de código** | Se pueden usar los mismos nombres de métodos en distintas clases. |
| **Flexibilidad** | El programa se adapta según el tipo de objeto que lo ejecute. |
| **Extensibilidad** | Se pueden agregar nuevas clases sin cambiar las existentes. |
| **Organización** | Facilita la implementación de comportamientos comunes de forma ordenada. |

---

## 3. Tipos de polimorfismo

| Tipo | Descripción | Ejemplo |
|------|--------------|----------|
| **De sobreescritura (override)** | Una clase hija redefine un método de la clase padre. | `class Perro extends Animal` redefine `hablar()` |
| **De sobrecarga (overload)** | Un mismo método tiene diferentes versiones según sus parámetros. *(JavaScript no lo implementa directamente, pero otros lenguajes como Java sí).* | `sumar(int, int)` y `sumar(double, double)` |
| **De interfaces o abstracción** | Diferentes clases implementan un mismo método de una interfaz o clase base abstracta. | Clases distintas implementan `dibujar()` |

---

## 4. Ejemplo básico de polimorfismo (sobrescritura)

```javascript
class Animal {
  hablar() {
    console.log("El animal hace un sonido.");
  }
}

class Perro extends Animal {
  hablar() {
    console.log("El perro ladra: ¡Guau!");
  }
}

class Gato extends Animal {
  hablar() {
    console.log("El gato maúlla: ¡Miau!");
  }
}

// Lista de animales
const animales = [new Animal(), new Perro(), new Gato()];

// Llamar al mismo método en cada objeto
animales.forEach(animal => animal.hablar());
```
## Con herencia y **super**

```javascript
class Vehiculo {
  encender() {
    console.log("El vehículo está encendido.");
  }
}

class Auto extends Vehiculo {
  encender() {
    super.encender(); // Llama al método del padre
    console.log("El auto está listo para conducir.");
  }
}

const auto = new Auto();
auto.encender();
```

## En Funciones genericas

Un mismo método o función puede aceptar diferentes tipos de objetos si estos comparten el mismo método.

```javascript
class Circulo {
  dibujar() {
    console.log("Dibujando un círculo.");
  }
}

class Cuadrado {
  dibujar() {
    console.log("Dibujando un cuadrado.");
  }
}

function renderizarFigura(figura) {
  figura.dibujar(); // Se comporta distinto según el objeto
}

renderizarFigura(new Circulo());
renderizarFigura(new Cuadrado());
```
