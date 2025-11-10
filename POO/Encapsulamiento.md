# Encapsulamiento en la Programación Orientada a Objetos (POO)

## 1. ¿Qué es el encapsulamiento?

El **encapsulamiento** es uno de los **pilares fundamentales de la Programación Orientada a Objetos (POO)**.  
Consiste en **ocultar los datos internos de un objeto** y permitir el **acceso controlado** a ellos mediante métodos específicos.

Su propósito principal es **proteger la información** y **evitar modificaciones no deseadas** desde fuera del objeto.

En otras palabras, el encapsulamiento permite **ocultar cómo funciona algo internamente**, mostrando solo lo necesario al resto del programa.

---

## 2. Objetivos del encapsulamiento

| Objetivo | Descripción |
|-----------|--------------|
| **Proteger datos** | Evita que variables internas sean modificadas directamente. |
| **Controlar el acceso** | Permite definir quién puede leer o cambiar un valor. |
| **Facilitar mantenimiento** | Si se cambia la estructura interna, el resto del código no se ve afectado. |
| **Evitar errores** | Previene el uso incorrecto de los objetos. |

---

## 3. Ejemplo sin encapsulamiento

```javascript
class Cuenta {
  constructor() {
    this.saldo = 0;
  }
}

const cuenta = new Cuenta();
cuenta.saldo = -500; //  Permite modificar el saldo libremente
console.log(cuenta.saldo); // -500 (error lógico)
```

## Getter y Setters

Otra forma de controlar el acceso es usando los métodos getter y setter, que permiten leer o modificar atributos de manera controlada.

```javascript
class Usuario {
  #nombre;

  constructor(nombre) {
    this.#nombre = nombre;
  }

  // Getter (leer valor)
  get nombre() {
    return this.#nombre;
  }

  // Setter (modificar valor)
  set nombre(nuevoNombre) {
    if (nuevoNombre.length > 0) {
      this.#nombre = nuevoNombre;
    } else {
      console.log("Nombre inválido");
    }
  }
}

const user = new Usuario("Ian");
console.log(user.nombre); // Ian
user.nombre = "María";
console.log(user.nombre); // María
user.nombre = ""; // Nombre inválido
```
