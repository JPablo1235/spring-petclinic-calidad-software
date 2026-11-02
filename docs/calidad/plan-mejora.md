# Plan de mejora de calidad - Spring PetClinic

**Proyecto:** Spring PetClinic
**Actividad:** Calidad de Software II
**Rama:** lab/defectos-simulados
**Clasificacion:** Plan academico basado en escenarios hipoteticos de laboratorio.

## 1. Objetivo

Definir acciones preventivas y correctivas para reducir los riesgos asociados a los tres escenarios simulados del registro de triage, fortaleciendo la validacion de datos, las pruebas automatizadas y la integracion continua.

## 2. Matriz de mejora

| ID | Accion | Prioridad | Responsable propuesto | Esfuerzo estimado | Indicador |
|---|---|---|---|---|---|
| DEF-LAB-01 | Verificar validacion obligatoria del nombre de mascota en servidor y cliente. | Alta | Desarrollador backend | 4 horas | 100% de pruebas de campos obligatorios superadas |
| DEF-LAB-02 | Verificar reglas de fechas y agregar pruebas de limites temporales. | Alta | Desarrollador backend y QA | 5 horas | 100% de pruebas de fechas pasadas, presentes y futuras conforme a la regla de negocio |
| DEF-LAB-03 | Verificar limite de 255 caracteres y agregar pruebas de frontera. | Media | Desarrollador backend y QA | 3 horas | Rechazo de entradas de 256 caracteres y aceptacion de entradas validas |

**Nota:** los esfuerzos son estimaciones academicas, no mediciones de trabajo ejecutado.

## 3. Acciones transversales

### Pruebas automatizadas
- Mantener pruebas unitarias y de integracion.
- Incluir escenarios positivos, negativos y de frontera.
- Evitar duplicidad de pruebas y mantener nombres descriptivos.
- Ejecutar las pruebas antes de integrar cambios.

### Integracion continua
- Ejecutar el workflow de Maven ante cada push a main y pull request.
- Mantener la compilacion y las pruebas automatizadas como condiciones obligatorias.
- Generar el reporte de cobertura JaCoCo.
- Aplicar umbrales minimos de cobertura configurados en el proyecto.

### Gestion de defectos
- Registrar cada hallazgo con evidencia reproducible.
- Separar defectos confirmados de hipotesis y escenarios simulados.
- Asignar severidad y prioridad con criterios consistentes.
- Verificar la correccion mediante pruebas de regresion.

## 4. Indicadores de seguimiento

| Indicador | Meta propuesta | Frecuencia |
|---|---|---|
| Pruebas automatizadas exitosas | 100% de las pruebas obligatorias | Cada ejecucion CI |
| Cobertura de lineas | >= 90% | Cada ejecucion CI |
| Cobertura de instrucciones | >= 85% | Cada ejecucion CI |
| Cobertura de ramas | >= 80% | Cada ejecucion CI |
| Defectos criticos abiertos | 0 antes de liberar | Cada version |
| Casos de prueba con evidencia | 100% de los casos reportados | Cada ciclo de pruebas |

Los umbrales de cobertura corresponden a la configuracion academica aplicada al proyecto y no deben interpretarse como estandares oficiales de Spring PetClinic.

## 5. Priorizacion

1. DEF-LAB-01: proteger la integridad de los registros de mascotas.
2. DEF-LAB-02: proteger la consistencia cronologica del historial de visitas.
3. DEF-LAB-03: garantizar el cumplimiento de los limites de longitud.

La priorizacion considera el impacto funcional potencial y la importancia de preservar la integridad de los datos.

## 6. Validacion del plan

Las acciones propuestas deben validarse mediante pruebas automatizadas y ejecuciones del workflow de GitHub Actions. Ninguna accion se considerara implementada hasta contar con evidencia verificable.

## 7. Conclusion

El plan propone fortalecer la calidad del sistema mediante validaciones en el servidor, pruebas de frontera, automatizacion y controles de integracion continua. Los tres escenarios son simulaciones academicas y no representan defectos confirmados de la version original.