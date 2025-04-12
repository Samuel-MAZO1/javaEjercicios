## Ejercicio 1: Registro de Usuarios y Verificación de Mayoría de Edad

**Objetivo:**
 Aplicar la declaración de variables, tipos de datos y estructuras de control para verificar si los usuarios son mayores de edad.

**Instrucciones:**

1. Crea una clase llamada `RegistroUsuarios`.
2. Declara un arreglo de objetos o variables individuales para almacenar el nombre, la edad y el estado (por ejemplo, "Activo") de 5 usuarios.
3. Para cada usuario, verifica con una estructura `if-else` si la edad es mayor o igual a 18 y muestra un mensaje en la consola:
   - Si el usuario es mayor de edad, muestra:
      `"Usuario [nombre] es mayor de edad."`
   - Si el usuario es menor de edad, muestra:
      `"Usuario [nombre] es menor de edad."`
4. Comenta en el código qué tipo de dato utilizas para cada variable.

**Ejemplo de estructura base:**

```java
public class RegistroUsuarios {
    public static void main(String[] args) {
        // Declaración de arrays para almacenar datos de 5 usuarios
        String[] nombres = {"Ana", "Juan", "Carlos", "María", "Luis"};
        int[] edades = {17, 20, 15, 22, 16};
        // Se podría usar un array de boolean para el estado, pero en este caso se usa implícitamente.

        for (int i = 0; i < nombres.length; i++) {
            // Verificar si la edad es mayor o igual a 18
            if (edades[i] >= 18) {
                System.out.println("Usuario " + nombres[i] + " es mayor de edad.");
            } else {
                System.out.println("Usuario " + nombres[i] + " es menor de edad.");
            }
        }
    }
}
```

------

## Ejercicio 2: Datos Personales y Arreglos de Calificaciones

**Objetivo:**
 Practicar la declaración y asignación de variables, y el uso de arreglos en un programa con método `main`.

**Instrucciones:**

1. Crea una clase llamada `InformacionPersonal`.
2. Declara las siguientes variables y asígnales valores:
   - `String nombre`
   - `int edad`
   - `double estatura`
   - `char inicial`
   - `boolean esEstudiante`
3. Imprime en consola un mensaje combinando estos valores.
4. Declara un arreglo de enteros llamado `notas` con 5 calificaciones y recórrelo con un bucle `for` mostrando la posición y el valor de cada elemento.

**Ejemplo de código:**

```java
public class InformacionPersonal {
    public static void main(String[] args) {
        // Declaración y asignación de variables
        String nombre = "Carlos";
        int edad = 21;
        double estatura = 1.80;
        char inicial = 'C';
        boolean esEstudiante = true;

        // Mostrar la información personal en consola
        System.out.println("Hola, me llamo " + nombre + ". Tengo " + edad + " años, mido " + 
                           estatura + " metros, mi inicial es " + inicial + " y es estudiante? " + esEstudiante);

        // Declaración e inicialización de un arreglo de calificaciones
        int[] notas = {85, 90, 78, 92, 88};

        // Recorrer el arreglo y mostrar cada calificación con su índice
        for (int i = 0; i < notas.length; i++) {
            System.out.println("Calificación en la posición " + i + ": " + notas[i]);
        }
    }
}
```

------

## Ejercicio 3: Determinación de Números Pares e Impares

**Objetivo:**
 Utilizar bucles y condicionales junto con la entrada de datos por consola.

**Instrucciones:**

1. Crea una clase llamada `NumerosPares`.
2. Usa la clase `Scanner` para pedir al usuario que ingrese un número entero `n`, que será la cantidad de números a evaluar (del 1 a n).
3. Emplea un bucle `for` o `while` para recorrer los números del 1 hasta `n`.
4. Para cada número, utiliza el operador módulo `%` en una estructura `if` para determinar si el número es par o impar e imprime un mensaje adecuado.

**Ejemplo de código:**

```java
import java.util.Scanner;

public class NumerosPares {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingresa la cantidad de números a evaluar: ");
        int n = scanner.nextInt();

        for (int i = 1; i <= n; i++) {
            if (i % 2 == 0) {
                System.out.println("El número " + i + " es par.");
            } else {
                System.out.println("El número " + i + " es impar.");
            }
        }
        scanner.close();
    }
}
```

------

## Ejercicio 4: Calculadora Básica con Funciones y Operadores

**Objetivo:**
 Practicar la creación de métodos (funciones) y el uso de operadores aritméticos, de comparación y lógicos.

**Instrucciones:**

1. Crea una clase llamada `CalculadoraBasica`.
2. Define los siguientes métodos:
   - `public static int sumar(int a, int b)`
   - `public static int restar(int a, int b)`
   - `public static int multiplicar(int a, int b)`
   - `public static double dividir(int a, int b)`
      *Recuerda controlar la división por cero.*
3. En el método `main`, solicita al usuario que ingrese dos números enteros utilizando `Scanner`.
4. Llama a cada uno de los métodos definidos y muestra los resultados.
5. Agrega una comparación entre los dos números para determinar cuál es mayor o si son iguales, utilizando operadores lógicos y de comparación.

**Ejemplo de código:**

```java
import java.util.Scanner;

public class CalculadoraBasica {

    public static int sumar(int a, int b) {
        return a + b;
    }

    public static int restar(int a, int b) {
        return a - b;
    }

    public static int multiplicar(int a, int b) {
        return a * b;
    }

    public static double dividir(int a, int b) {
        if (b == 0) {
            System.out.println("Error: División por cero.");
            return 0;
        }
        return (double)a / b;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingresa el primer número: ");
        int num1 = scanner.nextInt();

        System.out.print("Ingresa el segundo número: ");
        int num2 = scanner.nextInt();

        // Realizar operaciones
        System.out.println("Suma: " + sumar(num1, num2));
        System.out.println("Resta: " + restar(num1, num2));
        System.out.println("Multiplicación: " + multiplicar(num1, num2));
        System.out.println("División: " + dividir(num1, num2));

        // Comparar los números usando operadores lógicos y de comparación
        if (num1 > num2) {
            System.out.println("El primer número es mayor que el segundo.");
        } else if (num1 < num2) {
            System.out.println("El segundo número es mayor que el primero.");
        } else {
            System.out.println("Ambos números son iguales.");
        }
        scanner.close();
    }
}
```

------

## Ejercicio 5: Menú Interactivo y Cálculo de Áreas

**Objetivo:**
 Aplicar la modularización mediante métodos y manejar un menú interactivo con entrada de usuario.

**Instrucciones:**

1. Crea una clase llamada `MenuCalculadora`.
2. Implementa un menú que se repita hasta que el usuario elija salir. Las opciones del menú deben ser:
   - Opción 1: Calcular el área de un rectángulo.
   - Opción 2: Calcular el área de un círculo.
   - Opción 3: Calcular el área de un triángulo.
   - Opción 4: Salir.
3. Para cada opción, solicita al usuario los datos necesarios y llama a métodos específicos:
   - `public static double calcularAreaRectangulo(double base, double altura)`
   - `public static double calcularAreaCirculo(double radio)`
   - `public static double calcularAreaTriangulo(double base, double altura)`
4. Valida la entrada de datos y muestra mensajes de error en caso de valores no válidos.

**Ejemplo de código:**

```java
import java.util.Scanner;

public class MenuCalculadora {

    public static double calcularAreaRectangulo(double base, double altura) {
        return base * altura;
    }

    public static double calcularAreaCirculo(double radio) {
        return Math.PI * radio * radio;
    }

    public static double calcularAreaTriangulo(double base, double altura) {
        return (base * altura) / 2;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int opcion = 0;

        while (opcion != 4) {
            // Mostrar menú
            System.out.println("\n--- Menú Calculadora ---");
            System.out.println("1. Calcular el área de un rectángulo");
            System.out.println("2. Calcular el área de un círculo");
            System.out.println("3. Calcular el área de un triángulo");
            System.out.println("4. Salir");
            System.out.print("Elige una opción: ");
            opcion = scanner.nextInt();

            switch (opcion) {
                case 1:
                    System.out.print("Ingresa la base del rectángulo: ");
                    double base = scanner.nextDouble();
                    System.out.print("Ingresa la altura del rectángulo: ");
                    double altura = scanner.nextDouble();
                    System.out.println("El área del rectángulo es: " + calcularAreaRectangulo(base, altura));
                    break;
                case 2:
                    System.out.print("Ingresa el radio del círculo: ");
                    double radio = scanner.nextDouble();
                    System.out.println("El área del círculo es: " + calcularAreaCirculo(radio));
                    break;
                case 3:
                    System.out.print("Ingresa la base del triángulo: ");
                    double baseTri = scanner.nextDouble();
                    System.out.print("Ingresa la altura del triángulo: ");
                    double alturaTri = scanner.nextDouble();
                    System.out.println("El área del triángulo es: " + calcularAreaTriangulo(baseTri, alturaTri));
                    break;
                case 4:
                    System.out.println("Saliendo del programa...");
                    break;
                default:
                    System.out.println("Opción inválida. Intenta nuevamente.");
            }
        }
        scanner.close();
    }
}
```

