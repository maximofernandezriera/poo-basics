# poo-basics

Un poco más allá de los "crespells". Vamos con la orientación a objetos en Java:

## Clases y Objetos
Una clase es una plantilla que define las propiedades y comportamientos de un objeto. Un objeto es una instancia de una clase.

Ejemplo:
```
public class Persona {
    private String nombre;
    private int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    public void saludar() {
        System.out.println("Hola, me llamo " + nombre + " y tengo " + edad + " años.");
    }
}

// Crear un objeto de la clase Persona
Persona persona = new Persona("Juan", 30);
persona.saludar();
```

## Herencia
La herencia permite que una clase herede las propiedades y comportamientos de otra clase.

Ejemplo:
```
public class Empleado extends Persona {
    private double salario;

    public Empleado(String nombre, int edad, double salario) {
        super(nombre, edad);
        this.salario = salario;
    }

    public void mostrarSalario() {
        System.out.println("Mi salario es " + salario);
    }
}

// Crear un objeto de la clase Empleado
Empleado empleado = new Empleado("Juan", 30, 50000);
empleado.saludar();
empleado.mostrarSalario();
```

## Polimorfismo
El polimorfismo permite que un objeto se comporte de diferentes maneras dependiendo del contexto.

Ejemplo:
```
public class FiguraGeometrica {
    public void dibujar() {
        System.out.println("Dibujando una figura geométrica");
    }
}

public class Circulo extends FiguraGeometrica {
    @Override
    public void dibujar() {
        System.out.println("Dibujando un círculo");
    }
}

public class Rectangulo extends FiguraGeometrica {
    @Override
    public void dibujar() {
        System.out.println("Dibujando un rectángulo");
    }
}

// Crear un array de objetos de tipo FiguraGeometrica
FiguraGeometrica[] figuras = new FiguraGeometrica[] {new Circulo(), new Rectangulo()};

// Llamar al método dibujar() en cada objeto del array
for (FiguraGeometrica figura : figuras) {
    figura.dibujar();
}
```

## Encapsulamiento
El encapsulamiento es la práctica de ocultar los detalles de implementación de un objeto y solo exponer los métodos necesarios para interactuar con él.

Ejemplo:
```
public class CuentaBancaria {
    private double saldo;

    public CuentaBancaria(double saldo) {
        this.saldo = saldo;
    }

    public void depositar(double cantidad) {
        saldo += cantidad;
    }

    public void retirar(double cantidad) {
        if (saldo >= cantidad) {
            saldo -= cantidad;
        } else {
            System.out.println("No hay suficiente saldo");
        }
    }

    public double getSaldo() {
        return saldo;
    }
}

// Crear un objeto de la clase CuentaBancaria
CuentaBancaria cuenta = new CuentaBancaria(1000);
cuenta.depositar(500);
cuenta.retirar(200);
System.out.println("Saldo actual: " + cuenta.getSaldo());
```
