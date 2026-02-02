<!--
Posible prompt:
<prompt>
Tengo un cuestionario con preguntas sobre "Clases y Objetos". Debes tener en cuenta que los conocimientos previos que tengo (y por tanto tus respuestas deben ser adaptadas), son:
- C/C++ sin orientación a objetos.
- Temas de Java previos: ninguno.

Cada respuesta debe tener entre 2 - 4 párrafos de longitud (sin contar los trozos de código).

Por favor, escribe en impersonal las respuestas.

</prompt>
----
-->

# TEMA 1. Clases y objetos

## 1. ¿Cuáles son las cuatro características básicas de la programación orientada a objetos? Describe brevemente cada una

La encapsulación consiste en agrupar datos y operaciones que trabajan sobre esos datos dentro de una misma unidad, llamada objeto. Desde fuera del objeto no se accede directamente a su implementación interna, sino a través de una interfaz bien definida. Esto recuerda a ocultar detalles de implementación tras funciones en C, pero de forma más estructurada.

La abstracción permite centrarse en qué hace un objeto y no en cómo lo hace. Se modelan conceptos del problema real mediante clases, ignorando detalles irrelevantes. Gracias a esto, el código resulta más comprensible y cercano al dominio del problema.

La herencia permite crear nuevas clases a partir de otras ya existentes, reutilizando código y extendiendo su comportamiento. Una clase “hija” hereda atributos y métodos de una clase “padre”, evitando duplicaciones y favoreciendo jerarquías lógicas.

El polimorfismo permite que diferentes objetos respondan de manera distinta a la misma operación. Esto se traduce en poder tratar objetos distintos de forma uniforme, algo difícil de conseguir en C sin grandes estructuras de control y convenciones manuales.


## 2. Cita cuatro lenguajes populares que permitan la programación orientada a objetos

Java es uno de los lenguajes orientados a objetos más extendidos, diseñado desde el principio con la POO como paradigma central. Todo el código se organiza en clases y objetos, y la gestión de memoria está en gran parte automatizada.

C++ también soporta programación orientada a objetos, aunque no obliga a usarla. Permite mezclar programación estructurada, genérica y orientada a objetos, lo que lo hace muy flexible pero también más complejo.

Python es un lenguaje multiparadigma donde todo es un objeto. Aunque su sintaxis es más simple y dinámica, soporta plenamente clases, herencia y polimorfismo.

C# es un lenguaje moderno, fuertemente orientado a objetos, muy influenciado por Java. Se usa ampliamente en entornos .NET y comparte muchos conceptos fundamentales con Java.


## 3. Los paradigmas anteriores a la POO, ¿Qué es la **programación estructurada**? y, todavía mejor, ¿Qué es la **programación modular**?

La programación estructurada se basa en organizar el código mediante estructuras de control claras como secuencias, condicionales y bucles. Se evita el uso de saltos incontrolados como goto, favoreciendo un flujo de ejecución legible y predecible. C es un ejemplo clásico de este paradigma.

La programación modular es una evolución natural de la estructurada. Consiste en dividir un programa grande en módulos más pequeños e independientes, cada uno con una responsabilidad concreta. En C, esto suele lograrse mediante ficheros .c y .h.

Cada módulo expone una interfaz pública (funciones y tipos) y oculta su implementación interna. Esta idea es conceptualmente muy cercana a la encapsulación de la POO, aunque sin llegar al concepto completo de objeto.

## 4. ¿Qué tres elementos definen a un objeto en programación orientada a objetos?

 Un objeto se define en primer lugar por su estado, que corresponde a los valores de sus atributos o variables internas. Este estado representa la información que el objeto mantiene en un momento dado.

El segundo elemento es el comportamiento, que está formado por los métodos o funciones que el objeto puede ejecutar. Estos métodos suelen operar sobre el estado interno del propio objeto.

El tercer elemento es la identidad, que diferencia a un objeto de otro aunque tengan el mismo estado. Dos objetos con los mismos valores en sus atributos siguen siendo entidades distintas en memoria.

## 5. ¿Qué es una clase? ¿Es lo mismo que un objeto? ¿Qué es una instancia? ¿Todos los lenguajes orientados a objetos manejan el concepto de clase?

Una clase es una definición o plantilla que describe cómo serán los objetos: qué atributos tendrán y qué métodos podrán ejecutar. No ocupa memoria para datos concretos, sino que define la estructura y el comportamiento.

Un objeto es una entidad concreta creada a partir de una clase, con valores específicos para sus atributos. A este proceso de creación se le llama instanciación, y el objeto resultante se denomina instancia de la clase.

No todos los lenguajes orientados a objetos manejan clases de la misma forma. Algunos lenguajes, como Java o C++, se basan estrictamente en clases, mientras que otros, como JavaScript, utilizan modelos basados en prototipos en lugar de clases tradicionales.


## 6. ¿Dónde se almacenan en memoria los objetos? ¿Es igual en todos los lenguajes? ¿Qué es la **recolección de basura**? 

En Java, los objetos se almacenan en una zona de memoria llamada heap. Las variables no contienen el objeto en sí, sino una referencia al mismo. Esto difiere de C, donde las estructuras pueden almacenarse en pila o en memoria dinámica según cómo se declaren.

No todos los lenguajes gestionan la memoria de la misma forma. En C y C++, el programador suele ser responsable de reservar y liberar memoria, mientras que en Java esta tarea se delega al sistema de ejecución.

La recolección de basura es un mecanismo automático que detecta objetos que ya no son accesibles desde el programa y libera su memoria. Esto reduce errores como fugas de memoria o accesos inválidos, a costa de perder control directo sobre cuándo se libera la memoria.


## 7. ¿Qué es un método? ¿Qué es la **sobrecarga de métodos**? 

Un método es una función asociada a una clase u objeto. A diferencia de una función en C, un método suele operar sobre los atributos del objeto al que pertenece, accediendo implícitamente a su estado interno.

La sobrecarga de métodos consiste en definir varios métodos con el mismo nombre pero con distintos parámetros. El compilador decide cuál utilizar en función del número y tipo de argumentos proporcionados.

Este mecanismo permite usar nombres coherentes para operaciones similares, mejorando la legibilidad del código sin necesidad de inventar nombres artificiales para cada variante.


## 8. Ejemplo mínimo de clase en Java, que se llame Punto, con dos atributos, x e y, con un método que se llame `calculaDistanciaAOrigen`, que calcule la distancia a la posición 0,0. Por sencillez, los atributos deben tener visibilidad por defecto. Crea además un ejemplo de uso con una instancia y uso del método

Una clase en Java se define usando la palabra clave class. Los atributos representan el estado del objeto y los métodos su comportamiento. En este ejemplo se modela un punto en un plano cartesiano.

El método calcula la distancia al origen usando el teorema de Pitágoras. Para simplificar, los atributos tienen visibilidad por defecto (package-private).

class Punto {
    double x;
    double y;

    double calculaDistanciaAOrigen() {
        return Math.sqrt(x * x + y * y);
    }
}

class Prueba {
    public static void main(String[] args) {
        Punto p = new Punto();
        p.x = 3;
        p.y = 4;

        double d = p.calculaDistanciaAOrigen();
        System.out.println(d);
    }
}


## 9. ¿Cuál es el punto de entrada en un programa en Java? ¿Qué es `static` y para qué vale? ¿Sólo se emplea para ese método `main`? ¿Para qué se combina con `final`?

El punto de entrada de un programa en Java es el método main, cuya firma es fija. La máquina virtual comienza la ejecución del programa llamando a este método sin necesidad de crear ningún objeto previamente.

La palabra clave static indica que un método o atributo pertenece a la clase y no a una instancia concreta. Esto permite acceder a él sin crear objetos, como ocurre con main.

static no se limita al método main; también se usa para constantes, métodos de utilidad o contadores globales a la clase. Cuando se combina con final, se define una constante que no puede cambiar su valor.

## 10. Intenta ejecutar un poco de Java de forma básica, con los comandos `javac` y `java`. ¿Cómo podemos compilar el programa y ejecutarlo desde linea de comandos? ¿Java es compilado? ¿Qué es la **máquina virtual**? ¿Qué es el *byte-code* y los ficheros `.class`?

Un programa Java se compila con el comando javac, que transforma el código fuente .java en ficheros .class. Posteriormente, el programa se ejecuta con el comando java, indicando la clase que contiene el método main.

Java es un lenguaje compilado, pero no a código máquina nativo. El compilador genera byte-code, un código intermedio independiente de la plataforma.

La máquina virtual de Java (JVM) es el entorno que ejecuta ese byte-code. Gracias a la JVM, el mismo programa puede ejecutarse en distintos sistemas operativos sin recompilar.


## 11. En el código anterior de la clase `Punto` ¿Qué es `new`? ¿Qué es un **constructor**? Pon un ejemplo de constructor en una clase `Empleado` que tenga DNI, nombre y apellidos

La palabra clave new se utiliza para crear un objeto en memoria y devolver una referencia a él. Es el equivalente conceptual a reservar memoria dinámica y inicializar una estructura en C.

Un constructor es un método especial que se ejecuta al crear un objeto. Tiene el mismo nombre que la clase y se usa para inicializar sus atributos.

class Empleado {
    String dni;
    String nombre;
    String apellidos;

    Empleado(String dni, String nombre, String apellidos) {
        this.dni = dni;
        this.nombre = nombre;
        this.apellidos = apellidos;
    }
}


## 12. ¿Qué es la referencia `this`? ¿Se llama igual en todos los lenguajes? Pon un ejemplo del uso de `this` en la clase `Punto`

this es una referencia al objeto actual, es decir, al objeto sobre el que se está ejecutando el método. Permite acceder explícitamente a los atributos y métodos de esa instancia concreta.

No todos los lenguajes usan el nombre this. Por ejemplo, en C++ también se usa this, mientras que en Python se utiliza self.

class Punto {
    double x;
    double y;

    void setX(double x) {
        this.x = x;
    }
}


## 13. Añade ahora otro nuevo método que se llame `distanciaA`, que reciba un `Punto` como parámetro y calcule la distancia entre `this` y el punto proporcionado

Este método calcula la distancia entre dos puntos: el objeto actual (this) y otro punto recibido como parámetro. Se aplica nuevamente el teorema de Pitágoras.

El método demuestra cómo un objeto puede interactuar con otro objeto del mismo tipo, accediendo a sus atributos.

double distanciaA(Punto otro) {
    double dx = this.x - otro.x;
    double dy = this.y - otro.y;
    return Math.sqrt(dx * dx + dy * dy);
}


## 14. El paso del `Punto` como parámetro a un método, es **por copia** o **por referencia**, es decir, si se cambia el valor de algún atributo del punto pasado como parámetro, dichos cambios afectan al objeto fuera del método? ¿Qué ocurre si en vez de un `Punto`, se recibiese un entero (`int`) y dicho entero se modificase dentro de la función? 

En Java, los objetos se pasan por copia de la referencia. Esto significa que se copia la referencia al objeto, no el objeto en sí. Por tanto, modificar los atributos del objeto dentro del método afecta al objeto original.

Sin embargo, si dentro del método se asigna la referencia a otro objeto, ese cambio no se refleja fuera. Esto suele generar confusión al principio.

En cambio, los tipos primitivos como int se pasan por copia del valor. Si un entero se modifica dentro del método, el valor original fuera del método no cambia.


## 15. ¿Qué es el método `toString()` en Java? ¿Existe en otros lenguajes? Pon un ejemplo de `toString()` en la clase `Punto` en Java

toString() es un método que devuelve una representación textual de un objeto. Se utiliza automáticamente en contextos como System.out.println.

Este concepto existe en muchos lenguajes, aunque con distintos nombres, como __str__ en Python. Sirve principalmente para depuración y visualización.

@Override
public String toString() {
    return "(" + x + ", " + y + ")";
}


## 16. Reflexiona: ¿una clase es como un `struct` en C? ¿Qué le falta al `struct` para ser como una clase y las variables de ese tipo ser instancias?


Una clase se parece a un struct en el sentido de que ambos agrupan datos relacionados. Sin embargo, una clase también agrupa comportamiento y controla el acceso a sus miembros.

Al struct le falta encapsulación, métodos asociados de forma natural y mecanismos como constructores, herencia o polimorfismo. Todo esto debe simularse manualmente en C.

Además, en C no existe el concepto de instancia como entidad con identidad y comportamiento integrado, sino solo bloques de datos manipulados por funciones externas.


## 17. Quitemos un poco de magia a todo esto: ¿Como se podría “emular”, con `struct` en C, la clase `Punto`, con su función para calcular la distancia al origen? ¿Qué ha pasado con `this`?

En C, se puede emular una clase usando un struct para los datos y funciones que reciben un puntero a ese struct. Ese puntero cumple el papel de this.

typedef struct {
    double x;
    double y;
} Punto;

double distancia_origen(Punto *p) {
    return sqrt(p->x * p->x + p->y * p->y);
}

Aquí, this se sustituye explícitamente por el parámetro Punto *p. La POO automatiza y estandariza este patrón, reduciendo errores y mejorando la legibilidad del código.
