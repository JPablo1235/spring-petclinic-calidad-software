# Registro de triage de defectos
## Spring PetClinic - Actividad de Calidad de Software II

**Proyecto:** Spring PetClinic
**Rama:** lab/defectos-simulados
**Clasificacion:** Escenarios controlados de laboratorio. No son defectos confirmados del proyecto original.

## Criterios de clasificacion

- Severidad: impacto tecnico o funcional del escenario.
- Prioridad: urgencia propuesta para su correccion.
- Estado: pendiente de reproduccion y validacion.

## DEF-LAB-01 - Registro de mascotas sin nombre

- Severidad propuesta: Alta.
- Prioridad propuesta: Alta.
- Modulo: Gestion de mascotas.
- Descripcion: escenario simulado en el que el sistema permite registrar una mascota sin nombre.
- Impacto: perdida de integridad de los datos y registros incompletos.
- Resultado esperado: el sistema debe rechazar el registro.
- Estado: pendiente de reproduccion.
- Evidencia: captura de la ejecucion de la prueba.

## DEF-LAB-02 - Registro de visitas con fecha pasada

- Severidad propuesta: Alta.
- Prioridad propuesta: Alta.
- Modulo: Gestion de visitas.
- Descripcion: escenario simulado en el que el sistema permite registrar visitas con fechas anteriores a la fecha actual.
- Impacto: inconsistencias en el historial clinico y en la cronologia de atencion.
- Resultado esperado: el sistema debe rechazar fechas que no esten en el futuro, conforme a la regla actual de PetClinic.
- Estado: pendiente de reproduccion.
- Evidencia: captura de la ejecucion de la prueba.

## DEF-LAB-03 - Descripcion de visita superior a 255 caracteres

- Severidad propuesta: Media.
- Prioridad propuesta: Alta.
- Modulo: Gestion de visitas.
- Descripcion: escenario simulado en el que el sistema acepta descripciones superiores al limite establecido.
- Impacto: inconsistencias de validacion y posibles problemas de almacenamiento o presentacion.
- Resultado esperado: rechazar descripciones superiores a 255 caracteres.
- Estado: pendiente de reproduccion.
- Evidencia: captura de la ejecucion de la prueba.

## Observacion

Estos tres escenarios son hipotesis de laboratorio. No deben reportarse como defectos reales de la version original mientras no se reproduzcan mediante pruebas controladas.
