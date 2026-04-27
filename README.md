# Proyecto de Estructuras de Datos

**Nombre:** Jonathan Juan David Osorio Pascual
**Carné:** 9941-24-14047
**Curso:** Programación 3

## ¿Qué hace el programa?

Este programa fue un proyecto para la clase de Programación 3. Básicamente recibe números del usuario y los guarda en diferentes estructuras dependiendo de si son pares, impares, negativos o cero. También guarda un historial de todo lo ingresado y puede construir un árbol BST con los números positivos, pero solo cuando el usuario lo pide, no automáticamente.

## Las estructuras que usé

Usé varias estructuras implementadas desde cero (sin usar las de C++ como vector o stack):

- **Pila:** Para los números impares positivos. Funciona como LIFO (el último en entrar es el primero en salir).
- **Cola:** Para los números pares positivos. Funciona como FIFO (primero en entrar, primero en salir).
- **Lista simple:** Para los números negativos.
- **Lista doble:** Para el historial, guarda todos los números válidos en orden de ingreso.
- **Árbol BST:** Para los números positivos, pero solo se construye si el usuario lo pide desde el menú.

## ¿Cómo funciona la lógica?

Cuando ingresas un número, el programa hace esto:

- Si es 0 → lo rechaza y no lo guarda en ningún lado.
- Si es par y positivo → va a la cola.
- Si es impar y positivo → va a la pila.
- Si es negativo → va a la lista simple.

Todo número válido también se guarda en el historial (lista doble).

El árbol BST no se construye cuando ingresas los números. Tienes que ir al menú y elegir la opción de construirlo. Ahí el programa toma todos los números positivos del historial y forma el árbol.

Con los números negativos de la lista simple, puedes eliminar aquellos cuyo valor absoluto sea menor a 10 (por ejemplo, -5, -2, -8 se eliminan; -15, -20 se quedan).

También hay una opción de "reorganizar" que vacía toda la pila y toda la cola, las convierte en listas simples, y luego reconstruye el BST con esos datos.

## Estadísticas que muestra

El programa te dice:
- Cuántos pares positivos ingresaste
- Cuántos impares positivos
- Cuántos negativos
- Cuántos ceros rechazaste
- El total de números válidos
- El número más grande y el más pequeño de todos los ingresados

## Cómo ejecutarlo

Usé Dev-C++ 5.11 para hacerlo. Para compilarlo solo abrís el archivo, le das a compilar (Ctrl+F9) y después a ejecutar (Ctrl+F10).

El menú tiene estas opciones:

1. Ingresar N números
2. Mostrar historial
3. Mostrar estadísticas
4. Construir BST
5. Mostrar recorridos del BST (InOrden, PreOrden, PostOrden)
6. Procesar lista simple (eliminar menores a 10)
7. Mostrar lista simple original
8. Eliminar |n|<10 de lista simple
9. Mostrar lista simple resultante
10. Reorganizar estructuras
11. Mostrar pila
12. Mostrar cola
13. Buscar en BST
0. Salir

## Ejemplo rápido

Si ingresás 15, 22, -8, 0 y 7:
- 15 va a la pila
- 22 va a la cola
- -8 va a la lista simple
- 0 es rechazado
- 7 va a la pila

Si después elegís construir el BST, el árbol se hace con 7, 15 y 22. Los recorridos serían:
- InOrden: 7 15 22
- PreOrden: 15 7 22
- PostOrden: 7 22 15

## Cosas técnicas

- Todo está hecho con struct y punteros.
- Uso new y delete para la memoria dinámica.
- No usé nada de STL (nada de vector, stack, queue, etc.).
- El programa libera toda la memoria cuando salís.
- Valida que ingreses opciones correctas y que N sea mayor a 0.
