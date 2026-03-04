# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

### RF-02 Código De Estudiante

El código del estudiante debe:

* Tener exactamente 8 caracteres.
* Iniciar con la letra “E”.
* Los 7 caracteres restantes deben ser numéricos.

## 3. Tecnicas de Prueba Aplicadas

### RF-02 Código De Estudiante

La técnica de caja negra para las pruebas más adecuada en este caso, es la de partición de equivalencia, ya que, como hay 3 criterios diferentes, se consideran equivalentes porque esperamos el mismo comportamiento.

## 4. Casos de Prueba Diseñados
### RF-02 Código De Estudiante
| ID | Descripción | Precondiciones | Datos de prueba | Pasos | Resultado Esperado | Estado | 
|----|-------------|----------------|-----------------|-------|--------------------|--------|
|CP-03| Verificar que el sistestema acepte un codigo de estudiante valido | El usuario esta autenticado y el formulario disponible | E1234567 | 1. Ingresar el codigo 2. enviar formulario |El sistema acepta el código de estudiante y permite continuar | Paso
|CP-04| Verificar que el sistema rechace un código que no cumple el formato requerido | El usuario está autenticado y el formulario disponible | A1234567 | 1. Ingresar el codigo 2. Enviar formulario | El sistema muestra error indicando que el código debe iniciar con la letra “E” |  Fallo 

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
