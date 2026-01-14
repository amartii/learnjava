# Java Chuleta Completa - Sintaxis y Ejecución

## 1. ESTRUCTURA BÁSICA

### Clase Principal
```java
// Archivo: MiClase.java
package com.ejemplo;  // Opcional, pero recomendado

public class MiClase {
    public static void main(String[] args) {
        System.out.println("¡Hola, Java!");
    }
}
```

### Convenciones de Nombres
- **Clases**: `PascalCase` (ej: `MiClase`, `Main`, `Usuario`)
- **Variables/métodos**: `camelCase` (ej: `miVariable`, `calcularSuma()`)
- **Constantes**: `UPPER_SNAKE_CASE` (ej: `PI = 3.14`, `MAX_SIZE = 100`)
- **Paquetes**: `lowercase.con.puntos` (ej: `com.empresa.proyecto`)

---

## 2. TIPOS DE DATOS

### Primitivos
```java
// Números
int edad = 25;                    // Enteros (32 bits)
long telefono = 1234567890L;      // Enteros grandes (64 bits)
float precio = 19.99f;            // Decimales (32 bits)
double salario = 2500.50;         // Decimales (64 bits)

// Lógicos y caracteres
boolean esActivo = true;          // Booleano
char inicial = 'J';               // Carácter único

// Tamaños por defecto
int x = 10;                       // Por defecto int en números sin sufijo
double y = 3.14;                  // Por defecto double en decimales
```

### No-Primitivos (Objetos)
```java
String nombre = "Juan";           // Cadenas de texto
String[] frutas = {"Manzana", "Plátano", "Naranja"};
Integer numero = 42;              // Wrapper (boxeo de int)
Double valor = 3.14;              // Wrapper (boxeo de double)
```

### Casting
```java
// Implícito (automático, sin pérdida)
int entero = 10;
double decimal = entero;          // 10.0

// Explícito (manual, puede perder precisión)
double d = 9.8;
int i = (int) d;                  // 9 (se pierde la parte decimal)

String texto = "123";
int numero = Integer.parseInt(texto);   // "123" → 123
double numero2 = Double.parseDouble("3.14");  // "3.14" → 3.14
```

---

## 3. OPERADORES

### Aritméticos
```java
int a = 10, b = 3;
int suma = a + b;                 // 13
int resta = a - b;                // 7
int mult = a * b;                 // 30
int div = a / b;                  // 3 (división entera)
double div2 = (double) a / b;     // 3.333... (fuerza división decimal)
int resto = a % b;                // 1 (módulo)
int potencia = (int) Math.pow(2, 3);  // 8
```

### Lógicos y Comparación
```java
boolean resultado;

// Comparación
resultado = 5 == 5;               // true (igualdad)
resultado = 5 != 3;               // true (desigualdad)
resultado = 5 > 3;                // true
resultado = 5 >= 5;               // true

// Lógicos
resultado = true && false;        // false (AND - ambos true)
resultado = true || false;        // true (OR - al menos uno true)
resultado = !true;                // false (NOT - negación)
```

### Incremento/Decremento
```java
int x = 5;
x++;                              // x = 6 (post-incremento)
++x;                              // x = 7 (pre-incremento)
x--;                              // x = 6 (post-decremento)
--x;                              // x = 5 (pre-decremento)
```

### Operador Ternario
```java
int edad = 20;
String estado = (edad >= 18) ? "Mayor de edad" : "Menor de edad";
// Si la condición es true → valor1, si false → valor2
```

---

## 4. CONTROL DE FLUJO

### If / Else
```java
int temperatura = 25;

if (temperatura > 30) {
    System.out.println("Hace calor");
} else if (temperatura > 20) {
    System.out.println("Temperatura agradable");
} else {
    System.out.println("Hace frío");
}
```

### Switch
```java
int dia = 3;
switch (dia) {
    case 1:
        System.out.println("Lunes");
        break;
    case 2:
        System.out.println("Martes");
        break;
    case 3:
        System.out.println("Miércoles");
        break;
    default:
        System.out.println("Otro día");
}
```

### For
```java
// For tradicional
for (int i = 0; i < 5; i++) {
    System.out.println(i);        // 0, 1, 2, 3, 4
}

// For-each (para arrays y colecciones)
String[] nombres = {"Ana", "Bob", "Carlos"};
for (String nombre : nombres) {
    System.out.println(nombre);
}

// For con decremento
for (int i = 5; i > 0; i--) {
    System.out.println(i);        // 5, 4, 3, 2, 1
}
```

### While
```java
int contador = 0;
while (contador < 5) {
    System.out.println(contador);
    contador++;
}

// Do-while (ejecuta mínimo una vez)
do {
    System.out.println(contador);
    contador++;
} while (contador < 5);
```

### Break y Continue
```java
for (int i = 0; i < 10; i++) {
    if (i == 3) continue;         // Salta esta iteración
    if (i == 7) break;            // Sale del bucle
    System.out.println(i);        // 0, 1, 2, 4, 5, 6
}
```

---

## 5. STRINGS

### Creación y Concatenación
```java
String nombre = "Juan";
String apellido = "Pérez";
String completo = nombre + " " + apellido;  // "Juan Pérez"

// String concatenation con multiple líneas
String texto = "Línea 1\n" +
               "Línea 2\n" +
               "Línea 3";

// Template strings (Java 21+)
String saludo = "Hola, %s".formatted(nombre);
```

### Métodos de String
```java
String texto = "Hola Mundo";

int longitud = texto.length();              // 11
char letra = texto.charAt(0);               // 'H'
String parte = texto.substring(0, 4);       // "Hola"
String minuscula = texto.toLowerCase();     // "hola mundo"
String mayuscula = texto.toUpperCase();     // "HOLA MUNDO"

boolean contiene = texto.contains("Mundo"); // true
int posicion = texto.indexOf("Mundo");      // 5
String reemplazado = texto.replace("Mundo", "Java");  // "Hola Java"

String[] palabras = texto.split(" ");       // ["Hola", "Mundo"]
String eliminado = texto.strip();           // Elimina espacios al inicio/final
```

### Comparación de Strings
```java
String str1 = "Java";
String str2 = "Java";
String str3 = new String("Java");

str1.equals(str2);                          // true (contenido igual)
str1.equals(str3);                          // true (contenido igual)
str1 == str2;                               // true (misma referencia en pool)
str1 == str3;                               // false (referencias diferentes)
str1.equalsIgnoreCase("java");              // true (ignora mayúsculas)
```

---

## 6. ARRAYS

### Declaración e Inicialización
```java
// Tipo1: Declaración sin inicialización
int[] numeros = new int[5];                 // Array de 5 elementos [0,0,0,0,0]

// Tipo2: Declaración con inicialización
int[] numeros2 = {1, 2, 3, 4, 5};

// Tipo3: Con new y valores
int[] numeros3 = new int[]{1, 2, 3, 4, 5};

// Arrays multidimensionales
int[][] matriz = {{1, 2, 3}, {4, 5, 6}};
int valor = matriz[0][1];                   // 2

// Longitud
int tamano = numeros.length;
```

### Operaciones
```java
int[] arr = {10, 20, 30, 40, 50};

// Iterar
for (int num : arr) {
    System.out.println(num);
}

// Búsqueda (necesita importar Arrays)
import java.util.Arrays;
int indice = Arrays.binarySearch(arr, 30); // 2

// Copiar
int[] copia = Arrays.copyOf(arr, arr.length);

// Ordenar
Arrays.sort(arr);

// Convertir a String
String texto = Arrays.toString(arr);       // "[10, 20, 30, 40, 50]"
```

---

## 7. COLECCIONES (List, Set, Map)

### List (ArrayList)
```java
import java.util.ArrayList;
import java.util.List;

List<String> nombres = new ArrayList<>();
nombres.add("Ana");                         // Agregar
nombres.add("Bob");
nombres.add("Carlos");

String primero = nombres.get(0);            // "Ana"
nombres.set(1, "Benjamin");                 // Modificar
nombres.remove(2);                          // Eliminar por índice
nombres.remove("Ana");                      // Eliminar por valor

int tamaño = nombres.size();                // 2
boolean contiene = nombres.contains("Bob"); // true

for (String nombre : nombres) {
    System.out.println(nombre);
}
```

### Set (HashSet) - Sin duplicados
```java
import java.util.Set;
import java.util.HashSet;

Set<String> colores = new HashSet<>();
colores.add("Rojo");
colores.add("Verde");
colores.add("Rojo");                        // No se agrega (duplicado)

boolean contiene = colores.contains("Rojo"); // true
colores.remove("Verde");

for (String color : colores) {
    System.out.println(color);              // Orden no garantizado
}
```

### Map (HashMap) - Clave-Valor
```java
import java.util.Map;
import java.util.HashMap;

Map<String, Integer> edades = new HashMap<>();
edades.put("Ana", 25);
edades.put("Bob", 30);
edades.put("Carlos", 28);

Integer edad = edades.get("Bob");           // 30
edades.put("Bob", 31);                      // Actualizar

edades.remove("Carlos");

boolean tieneAna = edades.containsKey("Ana");     // true
boolean tieneSesenta = edades.containsValue(60);  // false

for (String clave : edades.keySet()) {
    System.out.println(clave + ": " + edades.get(clave));
}
```

---

## 8. MÉTODOS Y FUNCIONES

### Declaración Básica
```java
public class Calculadora {
    // Método sin parámetros, sin retorno
    public void saludar() {
        System.out.println("¡Hola!");
    }
    
    // Método con parámetros
    public void saludarPersona(String nombre) {
        System.out.println("¡Hola, " + nombre + "!");
    }
    
    // Método con retorno
    public int suma(int a, int b) {
        return a + b;
    }
    
    // Método con múltiples parámetros y retorno
    public double calcularPromedio(double a, double b, double c) {
        return (a + b + c) / 3.0;
    }
    
    // Método estático (se llama sin instancia)
    public static int multiplicar(int a, int b) {
        return a * b;
    }
}

// Uso
Calculadora calc = new Calculadora();
calc.saludar();
calc.saludarPersona("Juan");
int resultado = calc.suma(5, 3);            // 8
int producto = Calculadora.multiplicar(4, 5); // 20
```

### Parámetros Variables (Varargs)
```java
public int sumarTodos(int... numeros) {
    int suma = 0;
    for (int num : numeros) {
        suma += num;
    }
    return suma;
}

// Uso
sumarTodos(1, 2, 3);                        // 6
sumarTodos(10, 20, 30, 40, 50);            // 150
```

---

## 9. CLASES Y OBJETOS

### Estructura de una Clase
```java
public class Usuario {
    // Atributos (propiedades)
    private String nombre;
    private int edad;
    private String email;
    
    // Constructor sin parámetros
    public Usuario() {
        this.nombre = "Anónimo";
        this.edad = 0;
    }
    
    // Constructor con parámetros
    public Usuario(String nombre, int edad, String email) {
        this.nombre = nombre;
        this.edad = edad;
        this.email = email;
    }
    
    // Getters
    public String getNombre() {
        return nombre;
    }
    
    public int getEdad() {
        return edad;
    }
    
    // Setters
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    
    public void setEdad(int edad) {
        if (edad > 0) {
            this.edad = edad;
        }
    }
    
    // Métodos normales
    public String obtenerInfo() {
        return nombre + " (" + edad + " años) - " + email;
    }
    
    // ToString
    @Override
    public String toString() {
        return "Usuario{" +
               "nombre='" + nombre + '\'' +
               ", edad=" + edad +
               ", email='" + email + '\'' +
               '}';
    }
}

// Uso
Usuario user1 = new Usuario("Juan", 25, "juan@email.com");
User user2 = new Usuario();

System.out.println(user1.getNombre());      // "Juan"
user1.setEdad(26);
System.out.println(user1.obtenerInfo());    // "Juan (26 años) - juan@email.com"
```

### Herencia
```java
// Clase padre
public class Animal {
    protected String nombre;
    
    public Animal(String nombre) {
        this.nombre = nombre;
    }
    
    public void hacer_ruido() {
        System.out.println("Ruido genérico");
    }
}

// Clase hijo
public class Perro extends Animal {
    public Perro(String nombre) {
        super(nombre);                      // Llama al constructor padre
    }
    
    @Override
    public void hacer_ruido() {
        System.out.println(nombre + " ladra: ¡Guau!");
    }
}

// Uso
Perro dog = new Perro("Rex");
dog.hacer_ruido();                          // "Rex ladra: ¡Guau!"
```

### Modificadores de Acceso
```java
public class Ejemplo {
    public int publico;                     // Visible desde cualquier lugar
    protected int protegido;                // Visible en la clase y subclases
    int predeterminado;                     // Visible solo en el paquete
    private int privado;                    // Visible solo en esta clase
}
```

---

## 10. MANEJO DE EXCEPCIONES

### Try-Catch-Finally
```java
try {
    int resultado = 10 / 0;                 // Esto lanza excepción
} catch (ArithmeticException e) {
    System.out.println("Error: no puedes dividir por cero");
    System.out.println("Mensaje: " + e.getMessage());
} catch (Exception e) {
    System.out.println("Otra excepción: " + e.getMessage());
} finally {
    System.out.println("Esto se ejecuta siempre");
}
```

### Throws
```java
public void leerArchivo(String ruta) throws IOException {
    // Si hay error, la excepción se propaga al llamador
    FileReader fr = new FileReader(ruta);
}
```

### Excepciones Comunes
```java
NullPointerException        // Acceder a null
ArrayIndexOutOfBoundsException  // Índice fuera de rango
ArithmeticException         // División por cero
NumberFormatException       // Conversión numérica fallida
FileNotFoundException       // Archivo no existe
IOException                 // Error de entrada/salida
ClassNotFoundException      // Clase no encontrada
```

---

## 11. CLASES ÚTILES

### Math
```java
Math.abs(-5);                   // 5 (valor absoluto)
Math.sqrt(16);                  // 4.0 (raíz cuadrada)
Math.pow(2, 3);                 // 8.0 (potencia)
Math.round(3.6);                // 4 (redondear)
Math.max(5, 8);                 // 8
Math.min(5, 8);                 // 5
Math.random();                  // 0.0 a 1.0
int aleatorio = (int)(Math.random() * 10); // 0-9
```

### System
```java
System.out.println("Salida estándar");
System.out.print("Sin salto de línea");
System.err.println("Error");

System.exit(0);                 // Terminar programa

long tiempo = System.currentTimeMillis(); // Milisegundos
```

### Scanner (Entrada del usuario)
```java
import java.util.Scanner;

Scanner scanner = new Scanner(System.in);

System.out.print("¿Cuál es tu nombre? ");
String nombre = scanner.nextLine();         // Lee línea completa

System.out.print("¿Cuál es tu edad? ");
int edad = scanner.nextInt();               // Lee entero

System.out.print("¿Cuál es tu altura? ");
double altura = scanner.nextDouble();       // Lee decimal

scanner.close();                            // Cerrar scanner
```

### SimpleDateFormat
```java
import java.util.Date;
import java.text.SimpleDateFormat;

Date ahora = new Date();
SimpleDateFormat formato = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
String fechaFormato = formato.format(ahora);
System.out.println(fechaFormato);           // 14/01/2026 10:54:00
```

---

## 12. EJECUCIÓN Y COMPILACIÓN

### Compilación Básica (Terminal)
```bash
# Compilar un archivo
javac MiClase.java
# Genera MiClase.class

# Compilar múltiples archivos
javac *.java

# Compilar con destino específico
javac -d ./bin MiClase.java
# Genera el .class en la carpeta bin/
```

### Ejecución (Terminal)
```bash
# Ejecutar una clase
java MiClase

# Ejecutar con paquete
java com.ejemplo.MiClase

# Ejecutar con classpath específico
java -cp ./bin MiClase

# Ejecutar archivo JAR
java -jar mi-aplicacion.jar
```

### VS Code - Atajos y Ejecución

#### Atajos de Teclado
| Acción | Atajo |
|--------|-------|
| Ejecutar archivo actual | `Ctrl+F5` (Win/Linux) o `Cmd+F5` (Mac) |
| Depurar (Debug) | `F5` |
| Ver "Run Code" (Extension) | `Ctrl+Alt+N` |
| Parar ejecución | `Ctrl+Alt+M` |
| Ir a definición | `F12` o `Ctrl+Click` |
| Ver referencias | `Shift+F12` |
| Autocompletar | `Ctrl+Space` |
| Formatear código | `Shift+Alt+F` |
| Refactorizar | `Ctrl+Shift+R` |

#### Métodos de Ejecución en VS Code

**1. Botón "Run" (Interfaz)**
- Abre el archivo con `public static void main()`
- Haz clic en el botón **"Run"** (play) arriba a la derecha
- Automáticamente compila y ejecuta

**2. Configuración de Lanzamiento (launch.json)**
Crea archivo `.vscode/launch.json`:
```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Java Launch",
            "type": "java",
            "name": "Launch Current File",
            "request": "launch",
            "mainClass": "${fileBasenameWithoutExtension}",
            "projectName": "${workspaceFolderBasename}"
        }
    ]
}
```

**3. Maven (Si es proyecto Maven)**
```bash
mvn clean compile          # Compilar
mvn clean package         # Compilar y empaquetar
mvn exec:java -Dexec.mainClass="com.ejemplo.MiClase"  # Ejecutar
```

**4. Gradle (Si es proyecto Gradle)**
```bash
gradle build              # Compilar
gradle run               # Ejecutar
gradle clean            # Limpiar
```

**5. Spring Boot (Si es proyecto Spring)**
```bash
# Ejecutar desde VS Code: botón Run en la clase @SpringBootApplication
# O desde terminal:
mvn spring-boot:run

# Para ejecutar JAR compilado:
java -jar target/mi-app-0.0.1-SNAPSHOT.jar
```

---

## 13. FLUJO RÁPIDO: CREAR Y EJECUTAR

### Opción 1: Archivo Simple
```bash
# Crear archivo
echo 'public class HolaMundo { public static void main(String[] args) { System.out.println("¡Hola!"); } }' > HolaMundo.java

# Compilar
javac HolaMundo.java

# Ejecutar
java HolaMundo
```

### Opción 2: VS Code (Recomendado)
1. Abrir VS Code
2. Crear nuevo proyecto: `Ctrl+Shift+P` → "Java: Create Java Project"
3. Seleccionar tipo (Maven, Gradle, o simple)
4. Escribir código en `src/main/java/MiClase.java`
5. Hacer clic en **Run** (botón play) o `Ctrl+F5`
6. Ver salida en la consola integrada

### Opción 3: Maven (Para proyectos mayores)
```bash
# Crear proyecto
mvn archetype:generate -DgroupId=com.ejemplo -DartifactId=mi-app -DarchetypeArtifactId=maven-archetype-quickstart

# Compilar y ejecutar
cd mi-app
mvn clean compile
mvn exec:java -Dexec.mainClass="com.ejemplo.App"
```

---

## 14. IMPORTACIONES COMUNES

```java
// Entrada/Salida
import java.util.Scanner;
import java.io.*;

// Colecciones
import java.util.List;
import java.util.ArrayList;
import java.util.Set;
import java.util.HashSet;
import java.util.Map;
import java.util.HashMap;
import java.util.Arrays;

// Fechas y Tiempo
import java.util.Date;
import java.text.SimpleDateFormat;
import java.time.*;        // Java 8+ (recomendado)

// Utilidades
import java.util.*;        // Importa todo java.util

// Spring Boot (si aplica)
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
```

---

## 15. TIPS FINALES

✅ **Haz esto:**
- Usa camelCase para variables/métodos
- Siempre cierra recursos (Scanner, FileReader, etc.)
- Declara variables con el tipo más específico
- Usa `final` para constantes
- Documenta con comentarios: `// Comentario` o `/* */`
- Maneja excepciones con try-catch

❌ **Evita esto:**
- Comparar String con `==` (usa `.equals()`)
- Arrays estáticos si necesitas flexibilidad (usa ArrayList)
- Variables globales innecesarias
- Métodos muy largos (divide en métodos más pequeños)
- Ignorar advertencias del compilador

---

## Resumen Rápido de Comandos

```bash
# COMPILACIÓN
javac MiClase.java                          # Compilar simple
javac -d ./bin MiClase.java                 # Compilar a carpeta

# EJECUCIÓN
java MiClase                                # Ejecutar simple
java -cp ./bin MiClase                      # Con ruta específica
java -jar aplicacion.jar                    # JAR empaquetado

# VS CODE
Ctrl+F5                                     # Ejecutar
F5                                          # Depurar
Shift+Alt+F                                 # Formatear

# MAVEN
mvn clean compile                           # Compilar
mvn exec:java -Dexec.mainClass="Clase"     # Ejecutar
mvn spring-boot:run                         # Spring Boot
```

---

