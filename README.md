# Metodos_Numericos
Realizado por:
  <li>Diego Alonso Fernández Delagadillo</li>
  <li> Antonio Guerrero Lazcano</li>
  <li>Miguel Angel Flores Lopez</li>
  <li>Xavier Valle Dorantes</li>
<h2 align = "center"> <font color = "darkorange" size = "+6"  font face = "bauhaus 93">  INDICE </font> </h2>
<header> <font color = "red" size="+1" font face = "aharoni">
                <nav class="navegacion">
                    <ul class="Indice">
                       <li> <a href="#Descripción del Problemario"> Descripción del Problemario. </a> <br> </li>
                        <li> <a href="#SOBRE LA MATERIA"> SOBRE LA MATERIA. </a> <br> </li>
                            <ul class="subindice"> 
                                <li> <a href="#Competencia de la Asignatura"> Competencia de la Asignatura. </a> </li>
                                <li> <a href="#Competencia del TEMA"> Competencia del TEMA. </a> </li>
                                <li> <a href="#TEMARIO"> TEMARIO. </a> </li>  
                            </ul>
     <li> <a href="#Métodos numéricos para encontrar las raíces de ecuaciones que se encuentran en nuestro repositorio"> Métodos numéricos para encontrar las raíces de ecuaciones que se encuentran en nuestro repositorio. </a> <br> </li>
                            <ul class="subindice"> 
                                <li> <a href="#Método de Bisección"> Método de Bisección. </a> </li>
                                <li> <a href="#Método de la Falsa Posición"> Método de la Falsa Posición. </a> </li>
                                <li> <a href="#Método de la Secante"> Método de la Secante. </a> </li> 
                                <li> <a href="#Método de Newton-Raphson"> Método de Newton-Raphson. </a> </li> 
                            </ul>
                    </ul>
                </nav>
            </font> </header>

# Descripción
En este documento vamos a ver varios ejercicios sobre los distintos metodos como lo son:
  <li>1.-Biseccion</li>
  <li>2.-Falsa posición</li>
  <li>3.-De la secante</li>
  <li>4.-Newton</li>
  
# Sobre la materia 
<h2 align = "center"> <font  size = "+6" > Competencia de la asignatura</font> </h2>
Aplica los métodos numéricos para resolver problemas científicos y de ingeniería utilizando la computadora.
<h2 align = "center"> <font size = "+6"  > Competencia del tema</font> </h2>
Aplica los métodos numéricos con el objeto de solucionar ecuaciones mediante los métodos de intervalo e interpolación apoyada de un lenguaje de programación.  


<h3> <font font face = "forte"> <a name="TEMARIO"> TEMARIO  </a> </h3>

   2.1 Métodos de intervalo. 
   
   2.2 Método de bisección.
   
   2.3 Método de aproximaciones sucesivas. 
   
   2.4 Métodos de interpolación. 
   
   2.5 Aplicaciones.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
<h1 align = "center"> <font  font face = "bauhaus 93">  Métodos para enontrar las raíces de una ecuacion </font> </h1>

<h2 align = "center"> <font font face = "forte">  1. Bisección </h2>

<h3> <font font face = "arial"> DESCRIPCIÓN: </h3>

El método de bisección es un algoritmo utilizado para encontrar las raíces de una función en un intervalo dado. Consiste en dividir repetidamente el intervalo a la mitad y seleccionar el subintervalo que contiene la raíz. Este proceso se repite hasta que se alcanza la precisión deseada. Los pasos principales son los siguientes:

<h3> <font font face = "arial">Pasos del Método de Bisección:</h3>
<h5>Inicio del Intervalo:</h5> Se elige un intervalo inicial donde se sospecha que se encuentra la raíz.
<h5>Cálculo del Punto Medio:</h5> Se calcula el punto medio del intervalo.
<h5>Evaluación de la Función:</h5> Se evalúa la función en el punto medio para determinar en qué subintervalo se encuentra la raíz.
<h5>Selección del Nuevo Intervalo:</h5> Se selecciona el nuevo intervalo basado en la evaluación de la función en el punto medio.
<h5>Iteración:</h5> Se repiten los pasos anteriores hasta que se alcance la precisión deseada, es decir, hasta que el intervalo sea lo suficientemente pequeño.
   
   <h4> <font font face = "arial"> REPRESENTACIÓN GRÁFICA </h4>
   
  ![Imagen de WhatsApp 2024-02-28 a las 22 18 18_c66bb2e7]((https://algoritmosyalgomas.com/wp-content/uploads/2020/12/biseccion.png))


<h5> <font font face = "arial"> <b> <i> Ejemplo en código. </i> </b> </h5>

  import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Ingrese el límite inferior: ");
        double a = input.nextDouble();

        System.out.print("Ingrese el límite superior: ");
        double b = input.nextDouble();

        System.out.print("Ingrese el máximo de iteraciones: ");
        int maxIterations = input.nextInt();

        System.out.print("Ingrese el error permitido: ");
        double error = input.nextDouble();

        double root = bisection(a, b, maxIterations, error);
        System.out.println("La raíz de la función es: " + root);
    }

    public static double bisection(double a, double b, int maxIterations, double error) {
        double fa = f(a);
        double fb = f(b);

        if (fa * fb > 0) {
            System.out.println("No se puede garantizar la existencia de una raíz en el intervalo dado.");
            return Double.NaN;
        }

        for (int i = 0; i < maxIterations; i++) {
            double c = (a + b) / 2;
            double fc = f(c);

            if (Math.abs(fc) < error) {
                return c;
            }

            if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
        }

        return (a + b) / 2;
    }

    public static double f(double x) {
    
        return x*x - 4; 
    }
}


