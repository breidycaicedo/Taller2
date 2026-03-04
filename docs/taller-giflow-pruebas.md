# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

## RF-03 Inscripción a Evento

Un estudiante podrá inscribirse a un evento solo si:

- Está registrado.
- El evento tiene cupos disponibles.
- No está previamente inscrito.

Si alguna condición no se cumple, el sistema no debe permitir la inscripción.
## 3. Tecnicas de Prueba Aplicadas
Escogimos la técnica de **tabla de decisión**, debido a que existen varias condiciones, como lo son:

- Estar registrado.
- Que el evento tenga cupos disponibles.
- Estar previamente inscrito.

Cada una de estas condiciones puede ser verdadera o falsa, y dependiendo de su combinación, afecta el resultado final, que en este caso sería que el sistema permita o no la inscripción.
## 4. Casos de Prueba Diseñados
# Tabla de decisión

| Condiciones                          | Caso1 | Caso2 | Caso3 | Caso4 | Caso5 | Caso6 | Caso7 | Caso8 |
|--------------------------------------|-------|-------|-------|-------|-------|-------|-------|-------|
| Está registrado                     | V     | V     | V     | F     | V     | F     | F     | F     |
| El evento tiene cupos disponibles   | V     | V     | F     | V     | F     | V     | F     | F     |
| Está previamente inscrito           | V     | F     | V     | V     | F     | F     | V     | F     |
| Motivo del rechazo                  | N/A   | No está previamente registrado | El evento no tiene cupos disponibles | El usuario no está registrado | El evento no tiene cupos disponibles y el usuario no está registrado | No está registrado y no está previamente inscrito | No está registrado y el evento no tiene cupos disponibles | No cumple las condiciones |

## 5. Trazabilidad
| Requerimiento | Técnica | Casos Asociados |
|--------------|---------|----------------|
| RF-01 | (Valor limite) | CP-01 (Justo debajo del minimo), CP-02 (Minimo válido),CP-03(Justo encima del minimo) , CP-04(Justo debajo del minimo) , CP-05 (Máximo válido) , CP-     06(Justo encima del máximo)|
| RF-02 | (Partición de equivalencias) | CP-01 (Verificar que el sistema acepte  un código de estudiante válido), CP-02 (Verificar que el sistema rechace un codigo que no cumple el formato requerido|
| RF-03 | (Tabla de decisión) | CP-01 (Está reistrado), CP-02(El evento tiene cupos disponibles), CP-03(Está previamente escrito)|

## 6. Gestion de Versiones (GitFlow)
