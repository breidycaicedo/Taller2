# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

### RF-01 Registro de Estudiantes (Edad)

El sistema debe permitir el registro de estudiantes cuya edad esté entre 16 y 65 años inclusive.

### RF-02 Código De Estudiante

El código del estudiante debe:

* Tener exactamente 8 caracteres.
* Iniciar con la letra “E”.
* Los 7 caracteres restantes deben ser numéricos.

### RF-03 Inscripción a Evento

Un estudiante podrá inscribirse a un evento solo si:

- Está registrado.
- El evento tiene cupos disponibles.
- No está previamente inscrito.

Si alguna condición no se cumple, el sistema no debe permitir la inscripción.

## 3. Tecnicas de Prueba Aplicadas

### RF-01 Registro De Estudiantes (Edad)

Escogimos valor limite, debido a que se quiere evaluar un rango de valores numéricos con un limite superior e inferior.

### RF-02 Código De Estudiante

La técnica de caja negra para las pruebas más adecuada en este caso, es la de partición de equivalencia, ya que, como hay 3 criterios diferentes, se consideran equivalentes porque esperamos el mismo comportamiento.

### RF-03 Inscripción a Evento

Escogimos la técnica de **tabla de decisión**, debido a que existen varias condiciones, como lo son:

- Estar registrado.
- Que el evento tenga cupos disponibles.
- Estar previamente inscrito.

Cada una de estas condiciones puede ser verdadera o falsa, y dependiendo de su combinación, afecta el resultado final, que en este caso sería que el sistema permita o no la inscripción.

## 4. Casos de Prueba Diseñados

### RF-01 Registro de Estudiantes (Edad) - Valores Límite

| Caso | Edad (Valor de Entrada) | Otros requisitos (tipo de variable entero) | Resultado Esperado |
|----|------------|----------------|------------------|
| C1| 15 (Justo debajo del minimo) | Cumple otros requisitos | Edad rechazada (Valor por debajo del rango) |
| C2 | 16 (Minimo válido) | Cumple otros requisitos|Edad aprobada|
| C3 | 17 (Justo encima del minimo) | Cumple otros requisitos|Edad aprobada|
| C4 | 64 (Justo debajo del maximo)|Cumple otros requisitos |Edad aprobada|
| C5 | 65 (Maximo válido)o|Cumple otros requisitos|Edad aprobada|
| C6 | 66 (Justo encima del maximo)|Cumple otros requisitos |Edad rechazada (Valor por encima del rango)|

### RF-02 Código De Estudiante - Partición De Equivalencia

| ID | Descripción | Precondiciones | Datos de prueba | Pasos | Resultado Esperado | Estado | 
|----|-------------|----------------|-----------------|-------|--------------------|--------|
|CP-03| Verificar que el sistestema acepte un codigo de estudiante valido | El usuario esta autenticado y el formulario disponible | E1234567 | 1. Ingresar el codigo 2. enviar formulario |El sistema acepta el código de estudiante y permite continuar | Paso
|CP-04| Verificar que el sistema rechace un código que no cumple el formato requerido | El usuario está autenticado y el formulario disponible | A1234567 | 1. Ingresar el codigo 2. Enviar formulario | El sistema muestra error indicando que el código debe iniciar con la letra “E” |  Fallo 

### RF-03 Inscripción a Evento - Tabla de decisión

| Condiciones                          | Caso1 | Caso2 | Caso3 | Caso4 | Caso5 | Caso6 | Caso7 | Caso8 |
|--------------------------------------|-------|-------|-------|-------|-------|-------|-------|-------|
| Está registrado                     | V     | V     | V     | F     | V     | F     | F     | F     |
| El evento tiene cupos disponibles   | V     | V     | F     | V     | F     | V     | F     | F     |
| Está previamente inscrito           | V     | F     | V     | V     | F     | F     | V     | F     |
| Motivo del rechazo                  | N/A   | No está previamente registrado | El evento no tiene cupos disponibles | El usuario no está registrado | El evento no tiene cupos disponibles y el usuario no está registrado | No está registrado y no está previamente inscrito | No está registrado y el evento no tiene cupos disponibles | No cumple las condiciones |

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
