# Sistema Académico

Aplicación de consola desarrollada en **Java** para la gestión básica de un sistema de evaluación académica. Permite registrar estudiantes, profesores y materias, así como asignar calificaciones y consultar los promedios por materia.

El programa funciona mediante un menú interactivo en la terminal y almacena la información en memoria durante la ejecución.

## Características

- Registro de **estudiantes** (nombre, documento y código estudiantil).
- Registro de **profesores** (nombre, documento y especialidad).
- Registro de **materias**, cada una asignada a un profesor.
- **Calificación de estudiantes**: se selecciona profesor → materia → estudiante, y se ingresa una nota de 1 a 5 junto con un comentario. Se pueden registrar varias notas seguidas.
- **Consulta de calificaciones** agrupadas por estudiante y por materia, mostrando cada nota, su comentario y el **promedio por materia**.
- Listados de estudiantes, profesores y materias registrados.

## Estructura del proyecto

| Archivo | Descripción |
| --- | --- |
| `Persona.java` | Clase abstracta base con los atributos comunes `nombre` y `documento`. Define el método abstracto `mostrarInformacion()`. |
| `Estudiante.java` | Hereda de `Persona`. Agrega el atributo `codigo` (código estudiantil). |
| `Profesor.java` | Hereda de `Persona`. Agrega el atributo `especialidad`. |
| `Materia.java` | Representa una materia y el profesor que la dicta. |
| `Calificacion.java` | Relaciona un profesor, un estudiante y una materia con una `nota` (entero) y un `comentario`. |
| `SistemaAcademico.java` | Clase principal. Contiene el menú, la lectura de datos por consola y la lógica de registro y consulta. |

## Conceptos de programación aplicados

- **Herencia**: `Estudiante` y `Profesor` extienden de `Persona`.
- **Abstracción**: `Persona` es una clase abstracta con un método abstracto.
- **Polimorfismo**: `mostrarInformacion()` se sobrescribe (`@Override`) en las subclases.
- **Encapsulamiento**: atributos privados con métodos getters y setters.
- **Colecciones**: uso de `ArrayList` para gestionar las listas de estudiantes, profesores, materias y calificaciones.

## Requisitos

- **Java JDK 8** o superior.

## Cómo compilar y ejecutar

Desde la carpeta raíz del proyecto:

```bash
# Compilar todos los archivos fuente
javac *.java

# Ejecutar el programa
java SistemaAcademico
```

## Uso

Al iniciar, se muestra el siguiente menú:

```
=================================
       SISTEMA ACADÉMICO
=================================
1. Registrar estudiante
2. Registrar profesor
3. Registrar materia
4. Calificar estudiante
5. Ver calificaciones
6. Ver estudiantes
7. Ver profesores
8. Ver materias
0. Salir
=================================
```

Se ingresa el número de la opción deseada y se siguen las instrucciones en pantalla.

> **Nota:** Para registrar una materia debe existir al menos un profesor, y para calificar deben existir estudiantes, profesores y materias.

## Notas

- La información se guarda **solo en memoria**, por lo que se pierde al cerrar el programa.
- Las notas válidas van de **1 a 5**.
