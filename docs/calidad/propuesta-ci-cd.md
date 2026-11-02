# Propuesta de integracion continua y control de calidad
## Spring PetClinic

**Proyecto:** Spring PetClinic
**Herramienta:** GitHub Actions
**Construccion:** Maven Wrapper
**Lenguaje:** Java 17
**Rama principal:** main

## 1. Objetivo

Establecer un proceso automatizado de integracion continua que permita verificar la compilacion, ejecutar pruebas automatizadas y controlar metricas de cobertura antes de integrar cambios al proyecto.

## 2. Herramientas utilizadas

| Herramienta | Funcion |
|---|---|
| Git y GitHub | Control de versiones y colaboracion |
| GitHub Actions | Automatizacion del pipeline CI |
| Maven Wrapper | Construccion y gestion del proyecto |
| JUnit | Ejecucion de pruebas automatizadas |
| JaCoCo | Medicion y control de cobertura |
| Checkstyle / NoHTTP | Verificaciones estaticas configuradas en el proyecto |

## 3. Flujo de integracion continua

El workflow Java CI with Maven se ejecuta ante:

- Push a la rama main.
- Pull requests dirigidos a main.
- Ejecucion manual mediante workflow_dispatch.

### Etapas

1. Checkout: obtiene el codigo fuente del repositorio.
2. Configuracion de Java: prepara el entorno con Java 17.
3. Configuracion de Maven: utiliza Maven Wrapper y cache de dependencias.
4. Verificaciones: ejecuta los controles configurados durante el ciclo Maven.
5. Pruebas y compilacion: ejecuta `./mvnw -B verify`.
6. Resultado: GitHub Actions informa si el proceso finaliza correctamente.

## 4. Controles de calidad

Se establecieron los siguientes umbrales academicos de cobertura mediante JaCoCo:

| Metrica | Umbral minimo | Resultado local |
|---|---:|---:|
| Lineas | 90% | 93.99% |
| Instrucciones | 85% | 89.69% |
| Ramas | 80% | 81.97% |

Los umbrales se verifican durante la fase verify. Si no se cumplen, la compilacion debe fallar.

Adicionalmente, el proyecto ejecuta las verificaciones estaticas configuradas mediante Checkstyle y NoHTTP.

## 5. Resultados de validacion

En la ejecucion local de `mvn clean verify` se obtuvo:

- 79 pruebas ejecutadas.
- 0 fallidas.
- 0 errores.
- 2 omitidas.
- Quality Gate de JaCoCo superado.
- BUILD SUCCESS.

En GitHub Actions se verifico una ejecucion exitosa del workflow Java CI with Maven, con todos los pasos del trabajo build en verde.

## 6. Estrategia fail-fast

El pipeline debe detener el proceso cuando se presente alguna de estas condiciones:

- Error de compilacion.
- Pruebas automatizadas fallidas.
- Incumplimiento de los umbrales de cobertura.
- Fallo de las verificaciones estaticas configuradas.

Esto evita integrar cambios que no cumplan los controles definidos.

## 7. Limitaciones

La ejecucion exitosa demuestra que el workflow funciona y que los controles configurados fueron superados en esa ejecucion. No demuestra por si sola ausencia de defectos funcionales, seguridad completa ni cumplimiento de todos los requisitos no automatizados.

Las pruebas de integracion MySQL registraron dos pruebas omitidas en la ejecucion local. Por tanto, no se debe afirmar que esas pruebas validaron exitosamente la integracion con MySQL.

## 8. Conclusion

La integracion de Maven, GitHub Actions, pruebas automatizadas y JaCoCo permite establecer un control reproducible de calidad para los cambios del proyecto. La automatizacion facilita detectar regresiones y evita integrar cambios que incumplan los controles establecidos.