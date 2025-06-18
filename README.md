# CTRL Z -  Alternativa 2 - Ahorcado
### Grupo 3
### Integrantes:
- Santiago Gelvez
- Sebastian Martinez
- Daniel Calderón

# Avance 1
### Introducción
- Nosotros elegimos la alternativa 2 que consiste en hacer una aplicacion que emule un ahorcado utilizando python y funcione completamente en la misma consola
### ¿Qué es un ahorcado?
- El juego del ahorcado es un juego de adivinanza en el que los jugadores deben adivinar una palabra o frase oculta proponiendo letras por turnos. Por cada letra correcta, se escribe en el lugar correspondiente, mientras que por cada letra incorrecta, se dibuja una parte del cuerpo de un muñeco que será ahorcado si no se resuelve el enigma a tiempo.

### Objetivos
- Aplicar estructuras de control como condicionales (if, else) y bucles (while, for) para controlar el flujo del programa.

- Implementar funciones para organizar el código en bloques reutilizables y mejorar su legibilidad.

- Utilizar estructuras de datos simples, como listas o diccionarios, para manejar información como palabras, letras usadas, o puntajes.

- Diseñar una interfaz de texto (consola) amigable que permita la interacción del usuario de forma clara e intuitiva.

- Incorporar validación de datos para asegurar que las entradas del usuario sean correctas (por ejemplo, que solo ingrese letras válidas).

- Implemetar las buenas practicas de codificacion (zen de python)

# Desglose del problema 
- para entender el problema decidimos desglosarlo con esto queremos plantear posibles soluciones ademas de tener claro cuales son los retos a los que tenemos que darles solucion:
### Funciones clave

- Cargar, seleccionar y mostrar palabras

- Validar letras

- Controlar intentos y dibujo

- Lógica de ganar/perder

### Mecánicas:
- Turnos por letra

- Condición de fin por victoria o fallos

- Entrada validada desde teclado

### Algoritmos:
Aleatoriedad

Iteración sobre letras

Estructuras condicionales

Validación de entradas

# Diagrma de flujo
  
``` mermaid
flowchart TD
    A[Inicio del juego] --> B[Definir palabra secreta: gato]
    B --> C[Crear lista palabra_mostrar con 4 espacios vacíos]
    C --> D[Intentos = 6]
    D --> E[palabra_adivinada = False]
    E --> F{¿Intentos > 0 y no se ha adivinado la palabra?}
    
    F -->|Sí| G[Mostrar palabra actual y número de intentos]
    G --> H[Pedir letra al jugador]
    H --> I[letra_correcta = False]

    I --> J{¿Letra está en palabra_secreta?}
    J -->|Sí| K[Actualizar palabra_mostrar con letra]
    K --> L[letra_correcta = True]
    L --> M[Mensaje: ¡Bien!]
    M --> Q

    J -->|No| O[Mensaje: No está]
    O --> P[Restar 1 intento]
    P --> Q

    Q{¿Palabra completada?}
    Q -->|Sí| R[palabra_adivinada = True]
    Q -->|No| F

    F -->|No| S{¿palabra_adivinada?}
    S -->|Sí| T[¡Felicidades! Mostrar palabra]
    S -->|No| U[Lo siento. Mostrar palabra correcta]

    T --> W[palabra_adivinada=True]
    U --> V[Fin]
    W --> V[Fin]


```

# Lista de pasos


1. Inicio del juego

2. Definir la palabra secreta.  ejemplo: "gato"

3. Crear la lista palabra_mostrar con n(numero de letras) espacios vacíos (["", "", "", ""])

4. Inicializar el número de intentos: intentos = 6

5. Inicializar el estado del juego: palabra_adivinada = False

6. Verificar condición del juego:  ¿intentos > 0 y palabra_adivinada == False?

### Mientras la condición sea verdadera:

7. Mostrar la palabra actual (letras adivinadas y guiones)

8. Mostrar los intentos restantes

9. Pedir al jugador que ingrese una letra

10. Inicializar letra_correcta = False

11. Comprobar si la letra ingresada está en la palabra secreta

### Evaluar letra:

12. Actualizar la lista palabra_mostrar con la letra correcta

13. Asignar letra_correcta = True

14. Mostrar mensaje positivo: "¡Bien!"

15. Verificar si la palabra está completamente adivinada

### La letra no esta en la palabra:
 
16. Mostrar mensaje negativo: "No está"

17. Restar 1 intento

18. Verificar si la palabra está completamente adivinada

### Palabra completa

19. Asignar palabra_adivinada = True

20. Volver a comprobar la condición principal del juego

### 0 Intentos

21. Evaluar: ¿palabra_adivinada == True?

### Condicion final

### Condicion verdadera

22. Si: mostrar mensaje de éxito: "¡Felicidades!  Asignar palabra_adivinada = True

### Condicion Falso

23. No: mostrar mensaje de derrota con la palabra correcta

24. Fin del juego
