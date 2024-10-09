# Conversos de monedas utilizando una Api "Exchange Rate"
## Descripción
Este proyecto es un conversor de divisas desarrollado en Java que permite a los usuarios convertir entre diferentes
monedas utilizando tasas de cambio obtenidas de una API. Los usuarios pueden seleccionar la moneda de origen, 
la moneda de destino y la cantidad que desean convertir, y el programa mostrará el resultado de la conversión.
La aplicacion forma parte del challenge del programa de Alura Latam.

### Motivación
La idea detrás de este proyecto es facilitar la conversión de divisas de manera rápida y sencilla, proporcionando 
a los usuarios una herramienta útil para gestionar sus finanzas y realizar transacciones internacionales.

## Características
- Conversión entre múltiples divisas.
- Interfaz de línea de comandos fácil de usar.
- Historial de conversiones guardado en formato JSON.
- Integración con una API para obtener tasas de cambio actualizadas.

-  ## Tecnologías Utilizadas
- **Java**: Lenguaje de programación principal.
- **Gson**: Biblioteca para manejar JSON.

## Clases Principales

### 1. `ConversorDeDivisas_ExChangerate`
La clase principal que inicia el programa y maneja la lógica de conversión de divisas. Se encarga de obtener tasas de cambio y gestionar el historial de conversiones.

### 2. `MenuDeOpciones`
Esta clase se encarga de la interacción con el usuario y proporciona métodos para:

- **ConsultaOpcion**: Permite al usuario seleccionar una opción de un menú, asegurándose de que la entrada esté dentro de un rango válido.
- **ConsultaMonto**: Solicita al usuario que ingrese un monto, asegurándose de que sea un número válido y no negativo.
- **MostrarConversion**: Muestra el resultado de la conversión en un formato legible.
- **ConsultaParaContinuar**: Pregunta al usuario si desea realizar otra conversión y devuelve un valor booleano en función de la respuesta.

### 3. `ConsultaApi`
Esta clase se encarga de interactuar con la API de tasas de cambio. Sus principales métodos son:

- **getExchangeRates(String baseCurrency)**: Realiza una solicitud HTTP a la API para obtener las tasas de cambio relativas a la moneda base 
especificada. Devuelve la respuesta en formato JSON. Si ocurre un error en la solicitud, lanza una excepción con un mensaje de error.

### 4. `GeneradorJson`
Esta clase se encarga de manejar el historial de conversiones y generar un archivo JSON. Sus principales métodos son:

- **agregarConversion(String fromCurrency, String toCurrency, double amount, double result)**: Agrega una conversión a la lista de conversiones.
- **generarJson()**: Genera un archivo `conversiones.json` que contiene el historial de conversiones en formato JSON.
- **parseExchangeRates(String jsonResponse)**: Toma una respuesta JSON de la API y extrae las tasas de conversión.

**Nota**: Asegúrate de reemplazar `API_KEY` con tu clave API real para que funcione correctamente.

## Instalación
-Para utilizar este proyecto, necesitarás tener Java instalado en tu máquina. Asegúrate de seguir estos pasos:
1. **Instalar Java**: [Instrucciones de instalación de Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. **Configurar el entorno**: 
   - **IntelliJ IDEA Community Edition**: Descárgalo [aquí](https://www.jetbrains.com/idea/download/).
   - **Gson version 2.11.0**: Puedes agregarlo a tu proyecto mediante Maven o descargarlo manualmente.

## Uso
- Ejecuta el programa y selecciona la moneda que posees.
- Luego selecciona la moneda a la que deseas convertir.
- Ingresa la cantidad que deseas convertir.
- El programa mostrará el resultado de la conversión y te preguntará si deseas realizar otra conversión.
- Al finalizar, el historial de conversiones se guardará en un archivo JSON.
##
** 1.Ejemplo de la ejecucion del programa**

<img width="284" alt="image" src="https://github.com/user-attachments/assets/ec52e659-2028-4d2e-9406-1c2ba1b8d016">

###
** Descripcion del menú
- Muestra las divisas disponibles para la conversion
- Pide que ingreses un número de la moneda que tienes
- Luego pide el numero de la moneda a la que quieres convertir
- Solicita la cantidad de dinero a convertir
- Muestra la conversion realizada
- Pregunta si deseas realizar otra conversion
- AL finalizar te muestra un historial de conversiones

** 2.Ejemplo de archivo json generado**

<img width="239" alt="image" src="https://github.com/user-attachments/assets/eb3a37cb-b49b-4e64-8c3f-5c6553155c3a">


** Descripción del Formato
- fromCurrency: Moneda de origen (código de la moneda).
- toCurrency: Moneda de destino (código de la moneda).
- amount: Monto que se ha convertido.
- result: Resultado de la conversión.
- timestamp: Fecha y hora en que se realizó la conversión.

- gh repo clone KennethOrtegaArrieta/Conversor-de-monedas

## Manejo de Errores
El programa maneja entradas no válidas y problemas de conexión a la API, mostrando mensajes apropiados al usuario.

## Contribuciones
Si deseas contribuir, por favor clona el repositorio y envía un pull request con tus cambios.

## Agradecimientos
Gracias a Alura Latam por brindar esta oportunidad de aprendizaje.

