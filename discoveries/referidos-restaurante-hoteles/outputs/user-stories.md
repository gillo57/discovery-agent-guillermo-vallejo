# User Stories — Sistema de referidos hoteles-restaurante

Historias priorizadas por núcleo de valor: primero lo que cierra el ciclo
mínimo (registro → comisión → reporte), luego lo que habilita al hotel.

---

## Ciclo mínimo: registro y trazabilidad en restaurante

- **[US-01]** Como cajero / personal operativo, quiero seleccionar el hotel
  aliado de una lista al momento de cerrar una cuenta para registrar el referido
  en menos de 30 segundos sin escribir nada manualmente.
  - Criterios de aceptación:
    - Dado que hay una cuenta abierta, cuando el cajero inicia el registro del
      referido, entonces el sistema muestra la lista completa de hoteles aliados
      con su código sin requerir texto libre.
    - Dado que el cajero selecciona un hotel, cuando confirma la selección,
      entonces el sistema asocia ese hotel a la cuenta actual y registra el valor
      consumido.
    - Dado que el proceso completo toma más de 30 segundos, entonces se considera
      que el flujo falla el criterio de rendimiento.
  - Fuente: `cajero-restaurante.md`

- **[US-02]** Como cajero / personal operativo, quiero ver una confirmación
  visual inmediata después de registrar el referido para saber que el dato quedó
  guardado correctamente y no quedarme con dudas al cierre.
  - Criterios de aceptación:
    - Dado que el cajero completó el registro del referido, cuando el sistema lo
      guarda, entonces muestra un mensaje de confirmación con el nombre del hotel,
      el valor de la cuenta y la fecha.
    - Dado que el registro falla, cuando ocurre el error, entonces el sistema
      muestra un mensaje de error claro y no cierra el formulario.
  - Fuente: `cajero-restaurante.md`

- **[US-03]** Como cajero / personal operativo, quiero ver al cierre del día una
  lista de todos los referidos registrados en la jornada para revisar si falta
  alguno antes de terminar el turno.
  - Criterios de aceptación:
    - Dado que es el cierre del día, cuando el cajero consulta el reporte diario,
      entonces el sistema muestra: hotel, mesa/cuenta, valor consumido y comisión
      estimada para cada referido del día.
    - Dado que no hay referidos registrados en el día, cuando el cajero consulta
      el reporte, entonces el sistema lo indica claramente (no una pantalla vacía
      sin contexto).
  - Fuente: `cajero-restaurante.md`

---

## Administración: comisiones y visibilidad de alianzas

- **[US-04]** Como administrador del restaurante, quiero que el sistema calcule
  automáticamente la comisión de cada referido usando el porcentaje acordado con
  cada hotel para eliminar el cálculo manual y evitar errores o reclamos.
  - Criterios de aceptación:
    - Dado que se registra un referido con hotel y valor consumido, cuando el
      sistema guarda el registro, entonces calcula y muestra la comisión aplicando
      el porcentaje configurado para ese hotel.
    - Dado que el porcentaje de comisión de un hotel cambia, cuando el
      administrador lo actualiza en el sistema, entonces los registros futuros
      usan el nuevo porcentaje (los anteriores no se modifican).
  - Fuente: `administrador-restaurante.md`

- **[US-05]** Como administrador del restaurante, quiero ver un reporte mensual
  consolidado por hotel con número de referidos, ventas totales, ticket promedio,
  comisión acumulada y estado de actividad para liquidar cuentas con evidencia
  real y detectar alianzas inactivas.
  - Criterios de aceptación:
    - Dado que el administrador abre el reporte mensual, cuando selecciona el
      período, entonces el sistema muestra por cada hotel aliado: cantidad de
      referidos, ventas totales, ticket promedio y comisión total del período.
    - Dado que un hotel no generó ningún referido en el período, cuando aparece
      en el reporte, entonces se marca como "sin actividad" para que el
      administrador pueda tomar acción.
  - Fuente: `administrador-restaurante.md`

---

## Canal del hotel: código/QR y consulta de resultados

- **[US-06]** Como recepcionista de hotel, quiero contar con un código fijo o
  QR descargable de mi hotel para entregarlo al huésped en menos de un minuto
  sin tener que entrar a ninguna plataforma en cada recomendación.
  - Criterios de aceptación:
    - Dado que el administrador configura un hotel aliado, cuando genera el
      código del hotel, entonces el sistema produce un QR o código alfanumérico
      único e imprimible sin requerir login del recepcionista.
    - Dado que el recepcionista tiene el QR o código impreso, cuando se lo da
      al huésped, entonces el huésped puede mostrarlo en el restaurante sin dar
      ningún dato personal.
  - Fuente: `recepcionista-hotel.md`

- **[US-07]** Como recepcionista de hotel, quiero consultar un reporte simple
  de visitas confirmadas y beneficio acumulado de mi hotel para saber si la
  alianza está generando resultados y si vale la pena seguir recomendando.
  - Criterios de aceptación:
    - Dado que el recepcionista accede al reporte del hotel, cuando lo consulta,
      entonces ve: número de huéspedes que fueron al restaurante, consumo total
      y comisión/beneficio acumulado a favor del hotel.
    - Dado que no hay visitas registradas aún, cuando el recepcionista consulta
      el reporte, entonces ve un estado "sin visitas registradas" y no una
      pantalla de error.
  - Fuente: `recepcionista-hotel.md`
