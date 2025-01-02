---
{"dg-publish":true,"permalink":"/curso-2024-2025/conceptos-de-programacion/","tags":["gardenEntry"]}
---

#Curso 
# Estructuras de Datos

Las estructuras de datos permiten organizar y almacenar datos de manera eficiente. En Java, las principales estructuras se pueden clasificar en:

1. **Arrays**
2. **Listas** (`ArrayList`, `LinkedList`)
3. **Sets** (`HashSet`, `TreeSet`)
4. **Maps** (`HashMap`, `TreeMap`)

## **1. Arrays** 🗂️

Un **array** es una estructura de datos que almacena una colección de elementos del mismo tipo en posiciones contiguas de memoria. Su tamaño es fijo y se accede a los elementos por su índice.

### Operaciones

- **Insertar:** En el caso de Java no se puede cambiar el tamaño del array después de crearse.
- **Actualizar:** `numeros[1] = 5;`
- **Ordenar:** `Arrays.sort(numeros);`

### Ejemplo:

```java
int[] numeros = {1, 2, 3, 4, 5};  
numeros[2] = 10; // Actualización  
Arrays.sort(numeros); // Ordenación
```

---
## **2. Listas** 📋

Las listas se encuentran en el paquete `java.util` y son estructuras más dinámicas, ejemplos de estas son: `ArrayList` o `LinkedList` entre otras. Por lo que permiten manipular sus elementos de manera más flexible.
### Operaciones

- **Insertar:** `lista.add("NuevoElemento");`
- **Borrar:** `lista.remove("Elemento");`
- **Actualizar:** `lista.set(0, "Actualizado");`
- **Ordenar:** `Collections.sort(lista);`

### Ejemplo:

```java
List<Integer> lista = new ArrayList<>();  
lista.add(1); // Inserción  
lista.remove(0); // Borrado  
lista.set(0, 10); // Actualización
```

---
## **3. Sets** 🪄✨

Un **Set** es una estructura de datos que representa una colección de elementos **únicos**. Por lo que no se permiten duplicados, y estos datos pueden estar **desordenados** u **ordenados**, dependiendo de como se implementen.

### Implementaciones Comunes:

- **`HashSet`**: No garantiza orden.
- **`TreeSet`**: Mantiene los elementos ordenados de manera natural.

### Operaciones

- **Insertar:** `set.add("Azul");`
- **Borrar:** `set.remove("Rojo");`

### Ejemplo:

```java
Set<String> colores = new HashSet<>();
colores.add("Rojo");
colores.add("Azul");
colores.add("Rojo"); // No se añade porque es un duplicado.
```

---
## **4. Map** 🗝️

Un **Map** es una estructura que almacena pares llamados **"clave-valor"**. Cada clave es **única** y está asociada a un valor. Es útil para búsquedas rápidas de información mediante claves.
### Implementaciones Comunes:

- **`HashMap`**: No garantiza orden en las claves.
- **`TreeMap`**: Mantiene las claves ordenadas de manera natural.

### Operaciones

- **Inserción:** `mapa.put("NuevaClave", 2);`
- **Borrado:** `mapa.remove("Clave");`
- **Actualización:** `mapa.put("Clave", 3);`

### Ejemplo:

```java
Map<String, Integer> edades = new HashMap<>();
edades.put("David", 25);
edades.put("Ana", 30);
```

---
---
# Programación Orientada a Objetos {POO}

La **Programación Orientada a Objetos** es un paradigma de programación que organiza el código en torno a **objetos**, los cuales representan entidades del mundo real. Cada objeto tiene **atributos** (datos) y **métodos** (funcionalidades).

## **1. Conceptos fundamentales de POO** 💡:

Primero, hay que establecer 2 conceptos primordiales que se van a aplicar en el resto de conceptos, las `Clases` y los `Objetos`: 

### **A. Clases** 🏗️

Una **clase** es una plantilla o molde para crear objetos. Define las propiedades (**atributos**) y los comportamientos (**métodos**) que compartirán los objetos creados a partir de ella.

```java
class Persona {
    public static void main(String[] args) {
        // Atributos
        String nombre = "David";
        int edad = 25;
		
        // Saludo
        System.out.println("Hola, soy " + nombre + " y tengo " + edad + " años");
    }
}
```

### B. **Objetos** 🧱

Un **objeto** es como un "**bloque**" o "**unidad**" que representa algo del mundo real o algo abstracto. 

Cada objeto tiene atributos o propiedades como por ejemplo, un coche, este puede tener color, marca y velocidad. 

Los objetos también pueden hacer cosas (llamadas **métodos**). Por ejemplo, un coche que puede acelerar, frenar o encenderse.

```java
// Nuevo Objeto
Persona persona1 = new Persona();

// Valores para persona 1
persona1.nombre = "David";
persona1.edad = 25;

// Muestra el metodo Saludar
persona1.saludar();
```

En este caso, `persona1` es un objeto creado a partir de la clase `Persona`. Su estado es:

- `nombre: "David"`
- `edad: 25`

Y puede ejecutar el método `saludar()`. 

---
## **2. Herencia** 👶:

La **herencia** permite crear una clase hija (**subclase**) dentro de una clase existente (**superclase**), heredando sus atributos y métodos. 

Esta herencia permite dos cosas:

1. `Reutilizar Codigo:` Básicamente, la clase hija puede acceder a todos los métodos del padre evitando que tengamos que volver a escribir código innecesariamente.

2. `Sobrescritura:` Las hijas pueden cambiar a su gusto lo establecido por su clase padre ya sea cambiando parámetros o añadiendo los suyos propios.

```java
class Persona {
    // Atributo para almacenar el nombre de la persona
    String nombre;
	
    // Método para saludar, imprime un mensaje con el nombre
    void saludar() {
        System.out.println("Hola, soy " + nombre);
    }
}

// Clase Empleado que hereda de Persona
class Empleado extends Persona {
    // Atributo adicional para el salario del empleado
    double salario;
}
```

En este ejemplo, `Empleado` hereda los atributos y métodos de `Persona` y puede agregar otros nuevos como `salario`.

---
## **3. Abstracción** ⚛️:

La **abstracción** permite **ocultar los detalles internos** de implementación y mostrar solo lo necesario para interactuar con un objeto. Su objetivo principal es simplificar el diseño y centrarse en **qué hace un objeto** en lugar de **cómo lo hace**.

Este concepto facilita la creación de sistemas más escalables, ya que organiza mejor código, haciendo que sea más fácil de mantener y extender.

> [!faq] ¿Por qué Ocultar Detalles Internos?
> La abstracción es útil porque:
>1. **Reduce la complejidad:** En métodos públicos, el usuario solo necesita saber cómo usar un objeto sin preocuparse por su implementación interna.
>>
>2. **Mejora la seguridad:** Protege los datos sensibles al ocultar su manipulación interna
>>
>3. **Facilita cambios futuros:** Los cambios en la implementación no afectan al resto del sistema.
>>
>4. **Fomenta la reutilización de código:** Los comportamientos comunes se reutilizan en las clases concretas.
### **A. Clase Abstracta 🎓:**

Las clases abstractas son un tipo de clase que no se puede utilizar directamente para crear objetos. Así que, se usan como plantillas para definir atributos y comportamientos comunes que heredaran otras clases.

En este ejemplo defino una clase abstracta con los dos tipos de método:

```java
abstract class Animal {
    abstract void hacerSonido();  // Método abstracto
	
    void dormir() {  // Método concreto
        System.out.println("El animal está durmiendo.");
    }
}
``` 

> [!info] Atención
> Cualquier clase que herede de una **clase abstracta** o que implemente una **interfaz** tiene la obligación de proporcionar su propia versión (implementación) de esos métodos abstractos.

Vamos a crear una clase hija para ver como funciona y luego lo ejecutamos en un Main: 

```java
abstract class Animal {
    // Método abstracto
    abstract void hacerSonido();  
	
    // Método concreto
    void dormir() {
        System.out.println("El animal está durmiendo.");
    }
}

// Clase Hija de Animal
class Perro extends Animal {
    // Implementación del método abstracto de su Clase Padre
    void hacerSonido() {
        System.out.println("El perro dice: Guau!");
    }
}

public class Main {
    public static void main(String[] args) {
        Perro perro = new Perro(); // Nuevo Objeto
        perro.hacerSonido();  // Salida: El perro dice: Guau!
        perro.dormir();       // Salida: El animal está durmiendo.
    }
}
```

> [!important] Nota Importante
> **Heredar no es lo mismo que usar abstracción.** Ambos tienen propósitos distintos:
> - **Herencia**: Se usa para **reutilizar código** entre clases relacionadas.
>>
> - **Abstracción**: Se utiliza para **controlar el diseño**, definiendo lo esencial y ocultando los detalles de implementación.
> 
> Por lo tanto, la herencia facilita expandir funcionalidades que ya existen, la abstracción establece las reglas y las estructuras que las clases deben seguir, creando sistemas más organizados y fáciles de mantener.
### **B. Interfaz 🪞:**

Una interfaz define un conjunto de métodos que una clase debe implementar. No se puede usar directamente para crear objetos, pero sirve como un contrato que garantiza que las clases que la implementen tendrán ciertos comportamientos definidos.

Imagina a la **interfaz** como un "cajón" donde defines **solo las firmas** de los métodos, es decir, el nombre, los parámetros y el tipo de retorno. Las interfaces **no contienen lógica ni detalles de implementación**, solo las reglas para que las clases las sigan.

Las clases que **implementan** esa interfaz están **obligadas** a proporcionar la implementación concreta de esos métodos, de modo que cada clase pueda hacer cosas diferentes con esos mismos métodos.

Veamos un ejemplo, primero definiremos una interfaz: 

```java
interface Vehiculo {
    void moverse();  // Método abstracto: cómo se mueve un vehículo
    void detenerse(); // Método abstracto: cómo se detiene un vehículo
}
```

Luego definimos unas clases que usaran esta interfaz con distintos propósitos:

```java
class Coche implements Vehiculo {
    // Implementación del método moverse
    public void moverse() {
        System.out.println("El coche está conduciendo.");
    }

    // Implementación del método detenerse
    public void detenerse() {
        System.out.println("El coche se ha detenido.");
    }
}

class Barco implements Vehiculo {
    // Implementación del método moverse
    public void moverse() {
        System.out.println("El barco está navegando.");
    }

    // Implementación del método detenerse
    public void detenerse() {
        System.out.println("El barco ha detenido su marcha.");
    }
}
```

Y por último usaremos las clases implementadas: 

```java
public class Main {
    public static void main(String[] args) {
        Vehiculo miCoche = new Coche();
        miCoche.moverse();  // Salida: El coche está conduciendo.
        miCoche.detenerse(); // Salida: El coche se ha detenido.

        Vehiculo miBarco = new Barco();
        miBarco.moverse();   // Salida: El barco está navegando.
        miBarco.detenerse(); // Salida: El barco ha detenido su marcha.
    }
}
```

### Tabla comparativa entre Clase Abstracta e Interfaz:

![Pasted image 20250101143549.png](src/site/img/user/Recursos/Fotos/Pasted image 20250101143549.png)

---
## **4. Encapsulamiento** 🔒

El encapsulamiento oculta los datos internos de un objeto y permitir el acceso a ellos solo a través de **métodos públicos** específicos. Su propósito es proteger los datos y controlar cómo se accede a ellos.

```java
class Persona {
    // Atributo privado
    private String nombre;
	
	// Getter para nombre
    public String getNombre() {
        return nombre;
    }
	
    // Setter para nombre
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    
    // Constructor
    public Persona(String nombre) {
        this.nombre = nombre;
    }
}
```

En este caso, el atributo `nombre` está protegido, así que el **constructor** solo puede acceder a él mediante los métodos `getNombre` y `setNombre`.

> [!faq] ¿Qué son los Getters y Setters?
> - **Getters:** **Obtienen el valor** de un atributo privado. Se utilizan para leer datos sin acceder directamente a ellos.
>>
>- **Setters:** **Modifican el valor** de un atributo privado. Suelen incluir validaciones para garantizar la integridad de los datos.

> [!faq] ¿Que es un Constructor? 
> Un **constructor** es un método especial que se utiliza para crear e inicializar objetos de una clase. Tiene el mismo nombre que la clase y no retorna ningún valor. 
> 
> Su propósito principal es asignar valores iniciales a los atributos del objeto cuando este se crea. En el ejemplo, el constructor de la clase `Persona` recibe el parámetro `nombre` y lo asigna al atributo correspondiente mediante la palabra clave `this`.

---
## **5. Polimorfismo** 🛠️:

El **polimorfismo** permite que un objeto adopte diferentes formas. Esto facilita el uso de métodos con el mismo nombre pero comportamientos distintos.

### **A. Sobrecarga (Overloading) 🔄:**

Este tipo de polimorfismo ocurre cuando **varios métodos en la misma clase tienen el mismo nombre pero diferentes parámetros** (diferente número o tipo de parámetros). Se decide cuál método usar **en tiempo de compilación**.

```java
class Calculadora {
    // Método para sumar dos números
    int sumar(int a, int b) {
        return a + b;
    }
	
    // Método para sumar tres números (mismo nombre, pero más parámetros)
    int sumar(int a, int b, int c) {
        return a + b + c;
    }
	
    // Sumamos números decimales (mismo nombre, diferente tipo de parámetro)
    double sumar(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculadora calc = new Calculadora();
        System.out.println(calc.sumar(2, 3));       // 5
        System.out.println(calc.sumar(1, 2, 3));   // 6
        System.out.println(calc.sumar(2.5, 3.5));  // 6.0
    }
}

```

### **B. Sobrescritura (Overriding)** 📝:

Este tipo de polimorfismo ocurre cuando **una subclase redefine un método heredado de la clase padre**. Se decide cuál método ejecutar **en tiempo de ejecución**, dependiendo del tipo real del objeto.

```java
class Animal {
    void hacerSonido() {
        System.out.println("Sonido genérico");
    }
}

class Perro extends Animal {
    @Override // Sobrescribe el método de la clase padre
    void hacerSonido() {
        System.out.println("Guau");
    }
}

class Gato extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("Miau");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal miPerro = new Perro(); // Polimorfismo
        Animal miGato = new Gato();

        miPerro.hacerSonido(); // Guau
        miGato.hacerSonido();  // Miau
    }
}
```

---
