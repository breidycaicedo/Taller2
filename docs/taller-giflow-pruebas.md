# Documento de Pruebas

## 1. Descripcion del Sistema

Plataforma de Gestión de Eventos Universitarios

La plataforma permite:

* Registro de estudiantes.
* Validación de código estudiantil.
* Inscripción a eventos.

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

### Ramas creadas

Para el desarrollo del documento de pruebas se utilizó el modelo **GitFlow**, creando las siguientes ramas:

- **main**  
  Contiene la versión final y estable del documento de pruebas aprobada.

- **develop**  
  Rama principal de integración donde se consolidaron todos los requerimientos y casos de prueba antes de pasar a producción.

- **feature/RF-01-edad**  
  Creada para el desarrollo de los casos de prueba correspondientes al registro de estudiantes por edad.

- **feature/RF-02-codigo-estudiante**  
  Utilizada para diseñar y documentar los casos de prueba asociados al código del estudiante.

- **feature/RF-03-inscripcion-evento**  
  Rama destinada a la construcción de la tabla de decisión y casos de prueba para la inscripción a eventos.
 **feature/gitflow**
  Rama destinada al control de versiones y flujo de procesos.
---

### Flujo seguido

El flujo de trabajo aplicado fue el siguiente:

1. Se creó inicialmente la rama **develop** a partir de **main**.
2. Cada integrante del equipo creó una rama **feature** correspondiente al requerimiento asignado.
3. En cada rama feature se desarrollaron:
   - Técnicas de prueba.
   - Casos de prueba.
   - Tablas correspondientes.
4. Una vez finalizado el desarrollo, los cambios fueron enviados mediante *pull requests* hacia la rama **develop**.
5. Después de validar que toda la información estuviera correcta, la rama **develop** fue integrada en **main**, generando la versión final del documento.

---

### Integración de cambios

La integración se realizó mediante:

- Uso de **merge requests / pull requests**.
- Revisión previa de los cambios por parte del equipo.
- Validación de consistencia entre requerimientos, técnicas y casos de prueba antes de aceptar la integración.

Esto permitió evitar inconsistencias entre los distintos features desarrollados.

---

### Conflictos y resolución

Durante la integración se presentaron conflictos menores debido a:

- Edición simultánea del mismo documento.
- Modificaciones en tablas compartidas del informe.

Los conflictos fueron resueltos mediante:

- Comparación manual de versiones.
- Conservación de la información más actualizada.
- Revisión conjunta del equipo antes de confirmar el *merge*.

Una vez solucionados, se verificó que el documento final mantuviera coherencia y trazabilidad entre todos los requerimientos evaluados.
