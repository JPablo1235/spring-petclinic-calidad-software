# Analisis de causa raiz - Spring PetClinic

**Proyecto:** Spring PetClinic
**Rama:** lab/defectos-simulados
**Metodo:** Cinco porques e Ishikawa
**Naturaleza del analisis:** Hipotesis para escenarios simulados de laboratorio. No representan causas raiz verificadas en el proyecto original.

---

## DEF-LAB-01 - Registro de mascotas sin nombre

**Problema simulado:** el sistema permite guardar una mascota sin nombre.

### Analisis de los cinco porques

1. ¿Por que se guarda una mascota sin nombre?
   Porque la validacion de obligatoriedad no se ejecuta correctamente.

2. ¿Por que no se ejecuta la validacion?
   Porque la capa de presentacion o el servidor no aplica la regla requerida.

3. ¿Por que no se aplica la regla en ambas capas?
   Porque existe una posible falta de sincronizacion entre las validaciones.

4. ¿Por que existe esa falta de sincronizacion?
   Porque las reglas de validacion no se verifican de manera integral.

5. ¿Por que no se verifican integralmente?
   Porque el proceso de pruebas podria no contemplar entradas vacias en todos los niveles.

**Causa raiz hipotetica:** cobertura insuficiente de pruebas de validacion y posible ausencia de una regla obligatoria en el servidor.

### Diagrama de Ishikawa - categorias

- Metodo: ausencia de casos de prueba para campos vacios.
- Software: posible validacion incompleta.
- Personas: posible omision de la regla durante el desarrollo.
- Pruebas: insuficiente cobertura de entradas negativas.
- Datos: registros incompletos.
- Proceso: falta de verificacion de reglas de integridad.

**Accion propuesta:** asegurar la validacion del lado del servidor y agregar pruebas unitarias y de integracion.

---

## DEF-LAB-02 - Registro de visitas con fecha pasada

**Problema simulado:** el sistema permite registrar visitas con fechas anteriores a la fecha actual.

### Analisis de los cinco porques

1. ¿Por que se acepta una fecha pasada?
   Porque la validacion temporal no se ejecuta.

2. ¿Por que no se ejecuta?
   Porque la regla de fecha minima podria no estar implementada correctamente.

3. ¿Por que podria estar incompleta?
   Porque la validacion podria depender exclusivamente de la interfaz.

4. ¿Por que dependeria de la interfaz?
   Porque no se habria contemplado una validacion equivalente en el servidor.

5. ¿Por que no se habria contemplado?
   Porque los casos de prueba podrian no cubrir fechas anteriores al dia actual.

**Causa raiz hipotetica:** insuficiencia de pruebas de limites temporales y posible ausencia de validacion en el servidor.

### Diagrama de Ishikawa - categorias

- Metodo: reglas temporales no verificadas en todos los escenarios.
- Software: posible validacion incompleta de fechas.
- Personas: posible interpretacion incorrecta de la regla de negocio.
- Pruebas: ausencia de pruebas para fechas pasadas.
- Datos: fechas inconsistentes en el historial.
- Proceso: falta de pruebas de limites y regresion.

**Accion propuesta:** validar la fecha en el servidor y probar fechas pasadas, presentes y futuras.

---

## DEF-LAB-03 - Descripcion de visita superior a 255 caracteres

**Problema simulado:** el sistema acepta una descripcion que supera los 255 caracteres permitidos.

### Analisis de los cinco porques

1. ¿Por que se acepta una descripcion demasiado larga?
   Porque no se aplica el limite de longitud.

2. ¿Por que no se aplica el limite?
   Porque la validacion podria estar ausente o no ejecutarse.

3. ¿Por que podria estar ausente?
   Porque la restriccion de longitud no se habria configurado correctamente.

4. ¿Por que no se detecto?
   Porque las pruebas podrian utilizar solamente descripciones cortas.

5. ¿Por que las pruebas no contemplarian el limite?
   Porque no se habrian definido casos de prueba de frontera.

**Causa raiz hipotetica:** falta de pruebas de limites y posible configuracion incompleta de la validacion de longitud.

### Diagrama de Ishikawa - categorias

- Metodo: ausencia de pruebas de frontera.
- Software: posible restriccion de longitud incompleta.
- Personas: posible omision del requisito.
- Pruebas: falta de datos de prueba de 255 y 256 caracteres.
- Datos: entradas que exceden el limite establecido.
- Proceso: falta de revision de criterios de aceptacion.

**Accion propuesta:** aplicar validacion de longitud en el servidor y probar los limites de 255 y 256 caracteres.

---

## Conclusion del analisis

Los analisis anteriores presentan causas raiz hipoteticas asociadas a escenarios simulados. Para confirmar una causa raiz real se requiere reproducir el comportamiento, revisar el codigo involucrado y ejecutar pruebas controladas. No se atribuyen estos problemas a la version original de Spring PetClinic.