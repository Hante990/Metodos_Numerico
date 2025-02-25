<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Solución de Ecuaciones</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            background-color: #f4f4f4;
            margin: 0;
            padding: 20px;
        }
        h1, h2, h3, h4, h5 {
            text-align: center;
            color: #333;
        }
        .indice {
            list-style: none;
            padding: 0;
            text-align: center;
        }
        .indice li {
            margin: 10px 0;
        }
        .indice a {
            text-decoration: none;
            color: darkorange;
            font-weight: bold;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        pre {
            background: #222;
            color: #fff;
            padding: 10px;
            border-radius: 5px;
            overflow-x: auto;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Solución de Ecuaciones</h1>
        <h2>Índice</h2>
        <ul class="indice">
            <li><a href="#descripcion">Descripción del Problemario</a></li>
            <li><a href="#materia">Sobre la materia</a>
                <ul>
                    <li><a href="#competencia-asignatura">Competencia de la Asignatura</a></li>
                    <li><a href="#competencia-tema">Competencia del Tema</a></li>
                    <li><a href="#temario">Temario</a></li>
                </ul>
            </li>
            <li><a href="#metodos">Métodos Numéricos para Encontrar las Raíces</a>
                <ul>
                    <li><a href="#biseccion">Método de Bisección</a></li>
                    <li><a href="#falsa-posicion">Método de la Falsa Posición</a></li>
                    <li><a href="#secante">Método de la Secante</a></li>
                    <li><a href="#newton">Método de Newton-Raphson</a></li>
                </ul>
            </li>
        </ul>

        <h2 id="descripcion">Descripción</h2>
        <p>En este documento se presentan ejercicios sobre métodos numéricos para encontrar raíces de ecuaciones.</p>

        <h2 id="materia">Sobre la materia</h2>
        <h3 id="competencia-asignatura">Competencia de la Asignatura</h3>
        <p>Aplicar métodos numéricos para resolver problemas científicos y de ingeniería utilizando la computadora.</p>

        <h3 id="competencia-tema">Competencia del Tema</h3>
        <p>Utilizar métodos numéricos para la solución de ecuaciones mediante intervalos e interpolación.</p>

        <h2 id="temario">Temario</h2>
        <ul>
            <li>Método de Bisección</li>
            <li>Método de Falsa Posición</li>
            <li>Método de la Secante</li>
            <li>Método de Newton</li>
        </ul>

        <h1 id="metodos">Métodos Numéricos para Encontrar las Raíces</h1>

        <h2 id="biseccion">Método de Bisección</h2>
        <p>El método de bisección es un algoritmo que encuentra la raíz de una función en un intervalo dado...</p>
        <pre>
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
        </pre>

        <h2 id="falsa-posicion">Método de la Falsa Posición</h2>
        <p>El método de falsa posición utiliza interpolación lineal para aproximar la raíz...</p>

        <h2 id="secante">Método de la Secante</h2>
        <p>El método de la secante es una mejora del método de bisección sin la necesidad de un intervalo...</p>

        <h2 id="newton">Método de Newton-Raphson</h2>
        <p>El método de Newton-Raphson es un algoritmo iterativo que usa la derivada para encontrar la raíz...</p>

        <h3>Realizado por:</h3>
        <ul>
            <li>Diego Alonso Fernández Delagadillo</li>
            <li>Adriana Jamileth Mendoza Ortiz</li>
        </ul>
    </div>
</body>
</html>
