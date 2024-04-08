# Procesamiento de datos de Chequeado

En esta carpeta se procesaran manualmente las noticias recopiladas de Chequeado, pagina de fact-checking. Se procesaran las noticias para armar un dataset de noticias fasas, los procedimientos se detallan a continuación

### Eliminación de doble negación

 - Entrada: Falso | No, es mentira que Messi voto Schiaretti
 - Salida: Falso | Messi voto a Schiaretti

### Eliminación de negaciones

 - Entrada: Falso | Es falso que el café es cura para el COVID
 - Salida: Falso | El café es cura para el COVID

### Tranformación en Negaciones Verdaderas

 - Entrada: Falso | Es falso que el café es cura para el COVID
 - Salida: Verdadero | El café no es cura para el COVID

### Tranformación de Etiquetas mal clasificadas

 - Entrada: Verdadero | Es falso que el ministro dijo: "Hay que robarle a la gente"
 - Salida: Falso | El ministro dijo: "Hay que robarle a la gente"

### Tranformación de Noticias Falsas con Texto Verdaderos

 - Entrada: Falso | Durante el 2021 la Argentina fue el pais que mas exporto a China, a diferencia de lo que dijo el candidato en el debate
 - Salida: Verdadero | Durante el 2021 la Argentina fue el pais que mas exporto a China

### Tranformación de Citas precisas a Noticias

 - Entrada: Falso | Alberto: "En el 2021, en la Argentina la inflacion fue del 30%"
 - Salida: Falso | En el 2021, en la Argentina la inflacion fue del 30%

### Eliminacion de Citas no precisas
Si bien las citas pueden ser chequeables, al no tener contexto del dia o la fecha estas afirmaciones no tienen sentido. Hoy puede ser cierto, mañana no 

 - Entrada: Falso | Cafiero:"La industria hoy por hoy funciona en un 90% de su capacidad"
 - Entrada: Falso | Larreta:"La ciudad es la mas limpia del pais"

### Eliminacion de Textos no aportan informacion

 - Entrada: Falso | Es mentira lo que aparece en esa foto
 - Entrada: Falso | No es verdad lo que dice esta placa

### Eliminacion de Textos repetidos

Si bien realice un dropduplicates() en el procesamiento aparecen muchas noticias que dicen lo mismo escrito de manera diferente.
 - Entrada: Falso | No, los barbijos no causan hiploxia
 - Entrada: Falso | Es mentira que los barbijos causan hiploxia

### Agregado de Noticias Verdaderas para una mejor comprensión del Modelo. 
Dado que la gran mayoria de noticias suelen ser falsas, cada tanto esta bueno agregar noticias verdaderas para que el modelo entienda mejor el concepto. Por ejemplo existen gran variedad de noticias falsas sobre el COVID y las vacunas, por lo que es desable agregar informacion verdadera sobre estos temas.

 - Salida: Verdadero | El covid es una enfermedad originada en China, sus sintomas son la tos y la fiebre.
 - Salida: Verdadero | Las vacunas ayudan a combatir enfermedades

### Agregado de Informacion Nacional para una mejor comprensión del Modelo
Al igual que el caso anterior, hay gran variedad de noticias falsas sobre politicos, por lo que es desable agregar informacion verdadera sobre estas personas.

 - Salida: Verdadero | CFK es abogada recibida en la plata y fue presidenta en dos ocasiones
 - Salida: Verdadero | Macri fue presidente de Boca, gobernador de CABA y presidente de la Nacion

