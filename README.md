# Solución de Ecuaciones

## Índice
- [Descripción del Problemario](#descripción-del-problemario)
- [Sobre la materia](#sobre-la-materia)
  - [Competencia de la Asignatura](#competencia-de-la-asignatura)
  - [Competencia del Tema](#competencia-del-tema)
  - [Temario](#temario)
- [Métodos numéricos para encontrar las raíces](#métodos-numéricos-para-encontrar-las-raíces)
  - [Método de Bisección](#método-de-bisección)
  - [Método de la Falsa Posición](#método-de-la-falsa-posición)
  - [Método de la Secante](#método-de-la-secante)
  - [Método de Newton-Raphson](#método-de-newton-raphson)

## Descripción del Problemario
En este documento vamos a ver varios ejercicios sobre los distintos métodos numéricos:

1. Bisección
2. Falsa posición
3. Secante
4. Newton-Raphson

## Sobre la materia
### Competencia de la Asignatura
Aplicar métodos numéricos para resolver problemas científicos y de ingeniería utilizando la computadora.

### Competencia del Tema
Utilizar métodos numéricos con el objeto de solucionar ecuaciones mediante los métodos de intervalo e interpolación apoyados en un lenguaje de programación.

### Temario
- Método de Bisección
- Método de Falsa Posición
- Método de la Secante
- Método de Newton-Raphson

---

# Métodos numéricos para encontrar las raíces

## Método de Bisección
**Descripción:**
El método de bisección es un algoritmo utilizado para encontrar raíces de una función en un intervalo dado. Consiste en dividir repetidamente el intervalo a la mitad y seleccionar el subintervalo que contiene la raíz hasta alcanzar la precisión deseada.

**Pasos del Método de Bisección:**
1. Se elige un intervalo inicial.
2. Se calcula el punto medio.
3. Se evalúa la función en el punto medio.
4. Se selecciona el nuevo intervalo.
5. Se repiten los pasos anteriores hasta alcanzar la precisión deseada.

**Ejemplo en código (Java):**
```java
import java.util.Scanner;

public class Biseccion {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Ingrese el límite inferior: ");
        double a = input.nextDouble();
        System.out.print("Ingrese el límite superior: ");
        double b = input.nextDouble();
        System.out.print("Ingrese el error permitido: ");
        double error = input.nextDouble();
        double root = bisection(a, b, error);
        System.out.println("Raíz aproximada: " + root);
    }
    public static double bisection(double a, double b, double error) {
        while ((b - a) / 2 > error) {
            double c = (a + b) / 2;
            if (f(c) == 0) return c;
            if (f(a) * f(c) < 0) b = c;
            else a = c;
        }
        return (a + b) / 2;
    }
    public static double f(double x) {
        return x * x - 4;
    }
}
```

## Método de la Falsa Posición
**Descripción:**
El método de la falsa posición, también conocido como método de la regla falsa o regula falsi, es un algoritmo para encontrar las raíces de una función. A diferencia del método de bisección, que divide el intervalo por la mitad, este utiliza una línea recta para aproximar la función en el intervalo y encontrar la raíz.

**Ejemplo en código (Java):**
```java
import java.util.Scanner;
public class FalsaPosicion {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Ingrese el límite inferior: ");
        double a = input.nextDouble();
        System.out.print("Ingrese el límite superior: ");
        double b = input.nextDouble();
        System.out.print("Ingrese el error permitido: ");
        double error = input.nextDouble();
        double root = falsePosition(a, b, error);
        System.out.println("Raíz aproximada: " + root);
    }
    public static double falsePosition(double a, double b, double error) {
        double fa = f(a);
        double fb = f(b);
        if (fa * fb > 0) {
            System.out.println("No se puede garantizar la existencia de una raíz en el intervalo dado.");
            return Double.NaN;
        }
        for (int i = 0; i < 100; i++) {
            double c = (a * fb - b * fa) / (fb - fa);
            double fc = f(c);
            if (Math.abs(fc) < error) return c;
            if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
        }
        return (a * fb - b * fa) / (fb - fa);
    }
    public static double f(double x) {
        return x * x - 4;
    }
}
```

## Método de la Secante
**Descripción:**
El método de la secante es un algoritmo numérico utilizado para encontrar las raíces de una función. Se diferencia de la bisección en que no requiere que la función cambie de signo en el intervalo inicial.

## Método de Newton-Raphson
**Descripción:**
El método de Newton-Raphson es un algoritmo iterativo que usa la derivada para encontrar la raíz.

---

### Realizado por:
- Diego Alonso Fernández Delagadillo
- Adriana Jamileth Mendoza Ortiz
