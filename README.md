# Matrix10

=============================================================

El objetivo era resolver el reto 9, el cual consistia en
realizar algoritmos con arreglos de listas
A continuacion adjunto la imagen del repo del profe Felipe:

============================================================

![image](https://github.com/user-attachments/assets/da2e82a1-84ba-48ee-8b12-dbc4db10dbca)

============================================================

 >-Asi que adjuntare capturas mostrando como estan
 >diseñados los codigos para cumplir con cada punto del reto,
 >los realice en visual studio code, a su vez adjuntaré
 >los codigos para que puedan ser copiados y probados.

============================================================

# Punto-1

``` python

# Sin tener la matriz base
def añadir_numeros(filas, columnas ) -> list:
    matriz = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            n = int(input(""))
            fila.append(n)
        matriz.append(fila)
    return matriz
# Imprime la matriz, fila por fila
def imprimir_matriz(matriz):
    for i in range(len(matriz)):
        print(matriz[i])
#Esta es la suma de matrices
def sumar_matrices(matriz1, matriz2):
    filas = len(matriz1) #en esta parte se valida que sean matrices de misma longitud, es decir, si las filas son de igual longitud
    columnas = len(matriz1[0])
    resultado = []
    
    for i in range(filas):
        fila_resultado = []
        for j in range(columnas):
            fila_resultado.append(matriz1[i][j] + matriz2[i][j]) # aqui en la suma dce matrices, pues va sumando, la misma coordenada en las dos matrices, ademas mantiene la longitad de la fila, que seria a su vez la cantidad de columnas y crea la fila despues
        resultado.append(fila_resultado)
    
    return resultado

#Esta es la resta de matrices
def restar_matrices(matriz1, matriz2):
    filas = len(matriz1)
    columnas = len(matriz1[0])
    resultado = []
    
    for i in range(filas):
        fila_resultado = []
        for j in range(columnas):
            fila_resultado.append(matriz1[i][j] - matriz2[i][j])# aqui en la resta dce matrices,resta en la misma coordenada en las dos matrices, ademas mantiene la longitad de la fila, que seria a su vez la cantidad de columnas y crea la fila despues, si resultan numeros negativos lo pone sin ningun problema
        resultado.append(fila_resultado)
    
    return resultado


if __name__ == "__main__":
    # Numero de filas y columnas, debe ser igual
    filas = int(input("Ingrese el número de filas: "))
    columnas = int(input("Ingrese el número de columnas: "))
    
    # Hacer las matrices
    matriz_a = añadir_numeros(filas, columnas, "A")
    matriz_b = añadir_numeros(filas, columnas, "B")
    
    print("Matriz A:")
    imprimir_matriz(matriz_a)
    print("Matriz B:")
    imprimir_matriz(matriz_b)
    
    # Menú de operaciones
    while True:
        print("Operaciones disponibles:")
        print("1. Sumar matrices")
        print("2. Restar matrices (A - B)")
        print("3. Restar matrices (B - A)")
        print("4. Salir")
        
        opcion = input("Seleccione una operación (1-4): ")
        
        if opcion == "1":
            resultado = sumar_matrices(matriz_a, matriz_b)
            print("Resultado de A + B:")
            imprimir_matriz(resultado)
        
        elif opcion == "2":
            resultado = restar_matrices(matriz_a, matriz_b)
            print("Resultado de A - B:")
            imprimir_matriz(resultado)
        
        elif opcion == "3":
            resultado = restar_matrices(matriz_b, matriz_a)
            print("Resultado de B - A:")
            imprimir_matriz(resultado)
        
        elif opcion == "4":
            print("Programa finalizado.")
            break
        
        else:
            print("Opción no válida. Intente nuevamente.")

```
============================================================

# Punto-2

``` python

# Sin tener la matriz base
def añadir_numeros(filas, columnas ) -> list:
    matriz = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            n = int(input("Ingrese los elementos de su matriz"))
            fila.append(n)
        matriz.append(fila)
    return matriz

# Imprime la matriz, fila por fila
def imprimir_matriz(matriz):
    for i in range(len(matriz)):
        print(matriz[i])
#Esta es la suma de matrices

def multiplicar_matrices(matriz1, matriz2):
    if len(matriz1[0]) != len(matriz2):
        return None  # Las matrices no se pueden multiplicar
        
    filas_m1 = len(matriz1)
    columnas_m2 = len(matriz2[0])
    resultado = []
    
    for i in range(filas_m1):
        fila_resultado = []
        for j in range(columnas_m2):
            elemento = 0
            for k in range(len(matriz2)):
                elemento += matriz1[i][k] * matriz2[k][j]
            fila_resultado.append(elemento)
        resultado.append(fila_resultado)
    
    return resultado

if __name__ == "__main__":
    filas_a = int(input("Ingrese el número de filas para matriz A: "))
    columnas_a = int(input("Ingrese el número de columnas para matriz A: "))
    
    filas_b = int(input("Ingrese el número de filas para matriz B: "))
    columnas_b = int(input("Ingrese el número de columnas para matriz B: "))
    
    # Hacer las matrices
    matriz_a = añadir_numeros(filas_a, columnas_a, "A")
    matriz_b = añadir_numeros(filas_b, columnas_b, "B")
    # menu para ver que operacion se quiere realizar
    while True:
        print("1. Multiplicar matrices (A x B)")
        print("2. Multiplicar matrices (B x A)")
        print("3. Salir")
        
        opcion = input("Seleccione una operación (1-6): ")
                        
        if opcion == "1":
            if columnas_a == filas_b:
                resultado = multiplicar_matrices(matriz_a, matriz_b)
                print("\nResultado de A x B:")
                imprimir_matriz(resultado)
            else:
                print("\nError: El número de columnas de A debe ser igual al número de filas de B")
        
        elif opcion == "2":
            if columnas_b == filas_a:
                resultado = multiplicar_matrices(matriz_b, matriz_a)
                print("Resultado de B x A:")
                imprimir_matriz(resultado)
            else:
                print("Error: El número de columnas de B debe ser igual al número de filas de A")
        
        elif opcion == "3":
            print("Programa finalizado.")


```

============================================================

# Punto-3

``` python
# Sin tener la matriz base
def añadir_numeros(filas, columnas ) -> list:
    matriz = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            n = int(input("Ingrese los elementos de su matriz"))
            fila.append(n)
        matriz.append(fila)
    return matriz

# Imprime la matriz, fila por fila
def imprimir_matriz(matriz):
    for i in range(len(matriz)):
        print(matriz[i])

def transponer_matriz(matriz):
    filas = len(matriz)
    columnas = len(matriz[0])
    
    # Crear matriz transpuesta con dimensiones invertidas
    transpuesta = []
    for i in range(columnas):
        fila = []
        for j in range(filas):
            fila.append(matriz[j][i])
        transpuesta.append(fila)
    
    return transpuesta

```
