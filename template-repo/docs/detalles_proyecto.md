# Título del archivo

Fecha: 22/02/2024

**Participantes**:

- Hely Salgado <email:heladia@ccg.unam.mx>

## Descripción del Problema

Este es un proyecto resuelve un problema común de procesamiento de datos: sumar una serie de números presentes en un archivo. La necesidad surge de requerimientos de análisis de datos donde a menudo es necesario sumar grandes cantidades de números rápidamente y de manera automatizada.

El problema enunciado implica leer los números de un archivo, sumar los números y luego mostrar el total. Los números pueden estar en formato decimal.


## Especificación de Requisitos

Requisitos funcionales

- Leer números de un archivo dado, tanto en formato de número entero como decimal.
- Calcular la suma de todos los números leídos del archivo.
- Desplegar los números sumados y la suma total en el formato: n1 + n2 + n3 + ... = suma
- Producir un mensaje de error si el archivo no existe.
- Producir un mensaje de error si los datos de entrada no son números en base 10.

Requisitos no funcionales

- El script deberá estar escrito en Python.
- El tiempo de respuesta debe ser rápido, incluso con archivos de gran tamaño.
- La entrada del archivo debe ser flexible (i.e. se acepta a través de la línea de comandos).




## Análisis y Diseño



Para resolver este problema, se utilizarán varias funciones incorporadas en Python, así como el manejo de excepciones para la validación de datos y archivo. A continuación, se muestra un pseudocódigo simple para ilustrar la lógica básica del script:

```
Función principal (Suma_Numero):
    Intentar:
        datos_archivo = Obtener_Datos_Archivo(ruta_archivo)
        numeros = Validar_Datos(datos_archivo)
        resultado = Calcular_Suma(numeros)
        Imprimir_Resultado(numeros, resultado)
    Atrapar cualquier excepción como error:
        Imprimir el error

Función Obtener_Datos_Archivo(ruta_archivo):
    Si la ruta del archivo no existe:
        Levantar un error de "archivo no encontrado"
    Leer y retornar las líneas del archivo

Función Validar_Datos(data):
    Intentar:
        Convertir todos los datos a formato flotante y retornar como una lista
    Atrapar ValorError:
        Levanta un error de "¡Introducir solamente números de base 10!"

Función Calcular_Suma(numeros):
    Retornar la suma de los números

Función Imprimir_Resultado(numeros, resultado):
    Imprimir los números y su suma total en el formato especificado
```

El formato de los datos de entrada será simplemente un archivo, con un número por línea. Los números pueden estar en formato entero o decimal. La salida será una línea de texto que muestra los números sumados y la suma total, en el formato: n1 + n2 + n3 + ... = suma. Los mensajes de error se imprimirán en la consola.


#### Caso de uso: Sumar Números

```
         +---------------+
         |   Usuario     |
         +-------+-------+
                 |
                 | 1. Proporciona archivo de entrada
                 v
         +-------+-------+
         |   Sumador de  |
         |   Números en  |
         |   Archivo     |
         | (Sistema)     |
         +---------------+
```

- **Actor**: Usuario
- **Descripción**: El actor proporciona un archivo de entrada con números a sumar. El sistema valida el archivo y los datos de entrada, calcula la suma de los números y muestra el resultado.
- **Flujo principal**:

	1. El actor inicia el sistema proporcionando el archivo de entrada con los números a sumar.
	2. El sistema valida el archivo y los datos de entrada.
	3. El sistema calcula la suma de los números.
	4. El sistema muestra el resultado.
	
- **Flujos alternativos**:
	- Si el archivo proporcionado no existe
		1. El sistema muestra un mensaje de error diciendo que el archivo no se encuentra.
	- Si los datos de entrada no son números en base 10
		1. El sistema muestra un mensaje de error diciendo que se deben introducir números en base 10.
                

