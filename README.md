
# OOP Cheatsheet - C#

# 1. Estructura de una Clase

```csharp
class MiClase
{
    // Atributo de Clase (Estático)
    public static string atributoDeClase = "Soy un atributo de clase";

    // Atributo de Instancia
    private string atributoDeInstancia;

    // Constructor
    public MiClase(string atributoDeInstancia)
    {
        this.atributoDeInstancia = atributoDeInstancia;
    }

    // Método de Instancia
    public void MetodoDeInstancia()
    {
        Console.WriteLine($"Este es un método de instancia con el atributo: {this.atributoDeInstancia}");
    }

    // Método de Clase (Estático)
    public static void MetodoDeClase()
    {
        Console.WriteLine($"Este es un método de clase: {atributoDeClase}");
    }
}
```

# 2. Encapsulamiento
## En C#, se usan modificadores de acceso para el encapsulamiento:

## Public: Accesible desde cualquier parte.
## Private: Accesible solo dentro de la clase.
## Protected: Accesible dentro de la clase y las clases derivadas.
## Internal: Accesible dentro del mismo ensamblado.

```csharp

class EjemploEncapsulamiento
{
    public string publico = "Soy público";
    protected string protegido = "Soy protegido";
    private string privado = "Soy privado";

    public string GetPrivado()
    {
        return privado;
    }
}
```

# 3. Herencia
## C# soporta herencia simple, y se usa la palabra clave :.

```csharp

class Padre
{
    public void MetodoPadre()
    {
        Console.WriteLine("Este es el método del padre");
    }
}

class Hijo : Padre  // Hereda de Padre
{
    public void MetodoHijo()
    {
        Console.WriteLine("Este es el método del hijo");
    }
}
```

# 4. Propiedades (Getters y Setters)
## En C#, las propiedades encapsulan la lógica de acceso a los campos. Usan get y set

```csharp

class Persona
{
    private string _nombre;

    public string Nombre
    {
        get { return _nombre; }
        set
        {
            if (!string.IsNullOrEmpty(value))
                _nombre = value;
            else
                throw new ArgumentException("El nombre no puede estar vacío");
        }
    }
}
```

# 5. Métodos Estáticos y de Clase
## Métodos Estáticos
## Un método estático en C# es un método que pertenece a la clase en lugar de a una instancia específica de esa clase. 
## Esto significa que puedes llamar a un método estático sin tener que crear un objeto o una instancia de la clase.

```csharp
class OperacionesMatematicas
{
    public static int Sumar(int x, int y)
    {
        return x + y;
    }
}
```

# 6. Sobrecarga de Métodos
## C# soporta la sobrecarga de métodos nativamente mediante diferentes firmas (parámetros).

```csharp

class EjemploSobrecarga
{
    public void Metodo(int a)
    {
        Console.WriteLine("Un parámetro: " + a);
    }

    public void Metodo(int a, int b)
    {
        Console.WriteLine("Dos parámetros: " + a + ", " + b);
    }
}
```

# 7. Sobreescritura de Métodos (Override)
## En C#, se usa la palabra clave virtual en la clase base y override en la clase derivada para sobrescribir un método.

```csharp

class Padre
{
    public virtual void Metodo()
    {
        Console.WriteLine("Método del padre");
    }
}

class Hijo : Padre
{
    public override void Metodo()
    {
        Console.WriteLine("Método sobrescrito en el hijo");
    }
}
```


# 8. Métodos Abstractos y Clases Abstractas
## Para definir métodos abstractos, una clase debe ser abstracta, y los métodos deben ser implementados por las clases derivadas.

```csharp

abstract class ClaseAbstracta
{
    public abstract void MetodoAbstracto();
}

class ClaseConcreta : ClaseAbstracta
{
    public override void MetodoAbstracto()
    {
        Console.WriteLine("Implementación del método abstracto");
    }
}
```
