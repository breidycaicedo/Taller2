# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar
RF-01 Registro de Estudiantes (Edad)
El sistema debe permitir el registro de estudiantes cuya edad esté entre 16 y 65 años inclusive.
## 3. Tecnicas de Prueba Aplicadas
RF-01: Valor limite, debido a que se quiere evaluar un rango de valores numéricos con un limite superior e inferior.
## 4. Casos de Prueba Diseñados
RF-01 Registro de Estudiantes (Edad)
| Caso | Edad (Valor de Entrada) | Otros requisitos (tipo de variable entero) | Resultado Esperado |
|----|------------|----------------|------------------|
| C1| 15 (Justo debajo del minimo) | Cumple otros requisitos | Edad rechazada (Valor por debajo del rango) |
| C2 | 16 (Minimo válido) | Cumple otros requisitos|Edad aprobada|
| C3 | 17 (Justo encima del minimo) | Cumple otros requisitos|Edad aprobada|
| C4 | 64 (Justo debajo del maximo)|Cumple otros requisitos |Edad aprobada|
| C5 | 65 (Maximo válido)o|Cumple otros requisitos|Edad aprobada|
| C6 | 66 (Justo encima del maximo)|Cumple otros requisitos |Edad rechazada (Valor por encima del rango)|


## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
