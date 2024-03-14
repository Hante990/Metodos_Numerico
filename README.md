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
<h2 align = "center"> <font  font face = "bauhaus 93">  Métodos nlas raíces de una ecuacion </font> </h2>

<h3 align = "center"> <font font face = "forte">  1. Bisección </h3>

<h4> <font font face = "arial"> DESCRIPCIÓN: </h4>

El método de bisección es un algoritmo utilizado para encontrar las raíces de una función en un intervalo dado. Consiste en dividir repetidamente el intervalo a la mitad y seleccionar el subintervalo que contiene la raíz. Este proceso se repite hasta que se alcanza la precisión deseada. Los pasos principales son los siguientes:

<h4> <font font face = "arial">Pasos del Método de Bisección:</h4>
<li><h3>Inicio del Intervalo:</h3> Se elige un intervalo inicial donde se sospecha que se encuentra la raíz.</li>
<li><h3>Cálculo del Punto Medio:</h3> Se calcula el punto medio del intervalo.</li>
<li><h3>Evaluación de la Función:</h3> Se evalúa la función en el punto medio para determinar en qué subintervalo se encuentra la raíz.</li>
<li><h3>Selección del Nuevo Intervalo:</h3> Se selecciona el nuevo intervalo basado en la evaluación de la función en el punto medio.</li>
<li><h3>Iteración:</h3> Se repiten los pasos anteriores hasta que se alcance la precisión deseada, es decir, hasta que el intervalo sea lo suficientemente pequeño.</li>

<h4> <font font face = "arial"> ALGORITMO: </h4>
Paso 1: Elija valores iniciales inferior, xl, y superior, xu, que encierren la raíz, de tal forma que la función cambie de signo en el intervalo. Esto se verifica comprobando
que f(xl) f(xu) < 0.

Paso 2: Una aproximación de la raíz xr se determina mediante:
Xr = (Xl + Xu) / 2

Paso 3: Realice las siguientes evaluaciones para determinar en qué subintervalo está la raíz: 

    a) Si f(xl)f(xr) < 0, entonces la raíz se encuentra dentro del subintervalo inferior o izquierdo. Por lo tanto, haga xu = xr y vuelva al paso 2. 
    b) Si f(xl)f(xr) > 0, entonces la raíz se encuentra dentro del subintervalo superioro derecho. Por lo tanto, haga xl = xr y vuelva al paso 2. 
    c) Si f(xl)f(xr) = 0, la raíz es igual a xr; termina el cálculo.

   
   <h4> <font font face = "arial"> REPRESENTACIÓN GRÁFICA </h4>
   
  ![Imagen de WhatsApp 2024-02-28 a las 22 18 18_c66bb2e7](https://github.com/rubivj13/Metodos_Numericos/assets/147438464/bded96b1-64f6-4520-9fc0-b2dd1b794379)


<h4> <font font face = "arial"> IMPLEMENTACIÓN: </h4>

<h5> <font font face = "arial"> Descripción del ejemplo. </h5>

Función: x^3+4x^2-10      
Limites -> A:1 B:2      
Iteraciones: 10        
Error: 0.0001

<h5> <font font face = "arial"> <b> <i> Ejemplo en código. </i> </b> </h5>

    package biseccion1;
    
    import java.util.Scanner;
    
    public class Biseccion1 {
    
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            
            System.out.println("\t\t\t\t -- Método de bisección (EJERCICIO 1) --");
    
            System.out.print("Ingrese el límite inferior: ");
            double a = scanner.nextDouble();
    
            System.out.print("Ingrese el límite superior: ");
            double b = scanner.nextDouble();
    
            System.out.print("Ingrese el número máximo de iteraciones: ");
            int maxIter = scanner.nextInt();
    
            System.out.print("Ingrese el valor de tolerancia: ");
            double tol = scanner.nextDouble();
    
            // Encontrar la raíz de la función usando el método de bisección
            double root = bisectionMethod(a, b, maxIter, tol);
    
            // La parte %.5f%n sirve para formatear el resultado de la variable root como un número decimal con 5 dígitos después del punto decimal.
            System.out.printf("La raíz de la ecuación es: %.5f%n", root);
        }
    
        // Definir el método de bisección
        public static double bisectionMethod(double a, double b, int maxIter, double tol) {
            // Verificar si la función cambia de signo en el intervalo
            if ((func(a) * func(b)) > 0) {
                System.out.println("El método no puede encontrar una raíz en el intervalo.");
                return -1;
            }
    
            double c;
            // Iterar hasta que se alcance el número máximo de iteraciones
            for (int i = 0; i < maxIter; i++) {
                // Calcular el punto medio del intervalo
                c = (a + b) / 2;
                // Verificar si el punto medio está dentro de la tolerancia
                if (Math.abs(func(c)) < tol) {
                    // Devolver el punto medio como la raíz
                    return c;
                }
                // Actualizar el intervalo
                if (func(a) * func(c) < 0) {
                    b = c;
                } else {
                    a = c;
                }
            }
            // Devolver el punto medio del intervalo final como la raíz
            return (a + b) / 2;
        }
    
        // Definir la función para encontrar la raíz de
        public static double func(double x) {
            return Math.pow(x, 3) + 4 * Math.pow(x, 2) - 10;
        }
    }


<h5> <font font face = "arial"> <b> <i> Corrida del programa. </i> </b> </h5>
  
  ![Imagen de WhatsApp 2024-02-29 a las 21 23 35_14f59d0b](https://github.com/rubivj13/Metodos_Numericos/assets/147438464/381b92ed-11ff-4282-9758-cc91cb53dd78)


<h5> <font font face = "arial"> <b> <i> Visualización de la raíz en GeoGebra. </i> </b> </h5>

  ![Captura de pantalla 2024-02-29 222857](https://github.com/rubivj13/Metodos_Numericos/assets/147438464/035fc501-0729-4ff8-9c91-900f354df65a)


Te invito a que puedas checar mis ejercicios para profundizar en la implementación: <a href="#[INDICE](https://github.com/rubivj13/Metodos_Numericos/tree/main/M%C3%A9todo%20de%20bisecci%C3%B3n)"> <font font face = "arial"> https://github.com/rubivj13/Metodos_Numericos/tree/main/M%C3%A9todo%20de%20bisecci%C3%B3n </font> </a>
