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

## Abstracción
La abstracción es la práctica de mostrar solo la información esencial de un objeto y ocultar los detalles de implementación.

Ejemplo:
```
public abstract class Vehiculo {
public abstract void arrancar();
public abstract void frenar();
}

public class Coche extends Vehiculo {

public void arrancar() {
System.out.println("Arrancando el coche");
}

public void frenar() {
System.out.println("Frenando el coche");
}
}

public class Moto extends Vehiculo {

public void arrancar() {
System.out.println("Arrancando la moto");
}

public void frenar() {
System.out.println("Frenando la moto");
}
}

// Crear un array de objetos de tipo Vehiculo
Vehiculo[] vehiculos = new Vehiculo[] {new Coche(), new Moto()};

// Llamar a los métodos arrancar() y frenar() en cada objeto del array
for (Vehiculo vehiculo : vehiculos) {
vehiculo.arrancar();
vehiculo.frenar();
}
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

## Polimorfismo: meme --> https://www.youtube.com/watch?v=Nz8ssH7LiB0&t=6s
El polimorfismo permite que un objeto se comporte de diferentes maneras dependiendo del contexto.

Ejemplo:
```
public class FiguraGeometrica {
    public void dibujar() {
        System.out.println("Dibujando una figura geométrica");
    }
}

public class Circulo extends FiguraGeometrica {
    
    public void dibujar() {
        System.out.println("Dibujando un círculo");
    }
}

public class Rectangulo extends FiguraGeometrica {
    
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
### Artículos interesantes de leetcode (equivalente a codewars.com) 

- https://leetcode.com/discuss/post/5321129/oops-revision-1-java-by-lazy_code_19236-7e4v/
- https://leetcode.com/discuss/post/5321424/oops-revision-2-java-by-lazy_code_19236-2i6n/
- https://leetcode.com/discuss/post/5345963/oops-revision-3-java-by-lazy_code_19236-mlx1/
