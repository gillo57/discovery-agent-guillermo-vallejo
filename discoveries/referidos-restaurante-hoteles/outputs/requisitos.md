# Requisitos candidatos — Sistema de referidos hoteles-restaurante

---

## Requisitos funcionales

- **[R-01]** El sistema debe permitir registrar un referido asociando un hotel
  aliado (por código o selección de lista) a una cuenta en el momento del cobro.
  - Tipo: funcional
  - Origen: `cajero-restaurante.md` · Cajero / Personal operativo;
    `administrador-restaurante.md` · Administrador del restaurante

- **[R-02]** El sistema debe mostrar una lista de hoteles aliados con su código
  de referido para que el cajero pueda seleccionar rápidamente sin escribir
  manualmente.
  - Tipo: funcional
  - Origen: `cajero-restaurante.md` · Cajero / Personal operativo

- **[R-03]** El sistema debe asociar el referido registrado a la cuenta/mesa y
  al valor total consumido en esa transacción.
  - Tipo: funcional
  - Origen: `cajero-restaurante.md` · Cajero / Personal operativo;
    `administrador-restaurante.md` · Administrador del restaurante

- **[R-04]** El sistema debe calcular automáticamente la comisión correspondiente
  al hotel, aplicando el porcentaje o regla pactada con ese hotel.
  - Tipo: funcional
  - Origen: `administrador-restaurante.md` · Administrador del restaurante

- **[R-05]** El sistema debe mostrar una confirmación visual inmediata al cajero
  cuando el referido quede guardado correctamente.
  - Tipo: funcional
  - Origen: `cajero-restaurante.md` · Cajero / Personal operativo

- **[R-06]** El sistema debe generar un reporte diario de referidos por hotel,
  incluyendo mesa/cuenta, valor consumido y comisión estimada para revisión al
  cierre.
  - Tipo: funcional
  - Origen: `cajero-restaurante.md` · Cajero / Personal operativo;
    `administrador-restaurante.md` · Administrador del restaurante

- **[R-07]** El sistema debe generar un reporte semanal o mensual consolidado
  por hotel aliado que incluya: número de referidos, ventas totales, ticket
  promedio, comisión acumulada e indicador de hoteles inactivos (inscritos pero
  sin referidos en el período).
  - Tipo: funcional
  - Origen: `administrador-restaurante.md` · Administrador del restaurante

- **[R-08]** El sistema debe proveer al hotel un mecanismo de referido rápido
  (código fijo o QR descargable) que el recepcionista pueda entregar al huésped
  sin necesidad de ingresar a una plataforma en cada recomendación.
  - Tipo: funcional
  - Origen: `recepcionista-hotel.md` · Recepcionista de hotel

- **[R-09]** El sistema debe permitir al hotel consultar un reporte de visitas
  confirmadas y beneficios acumulados en su favor.
  - Tipo: funcional
  - Origen: `recepcionista-hotel.md` · Recepcionista de hotel

---

## Requisitos no funcionales

- **[R-10]** El registro del referido en caja debe completarse en menos de
  30 segundos desde que el cajero inicia el paso.
  - Tipo: no funcional (rendimiento / usabilidad)
  - Origen: `cajero-restaurante.md` · Cajero / Personal operativo

- **[R-11]** El mecanismo de referido del lado del hotel no debe tomar más de
  un minuto ni solicitar al huésped datos personales sensibles (cédula,
  pasaporte, correo electrónico u otro documento de identidad).
  - Tipo: no funcional (privacidad / usabilidad)
  - Origen: `recepcionista-hotel.md` · Recepcionista de hotel

- **[R-12]** La primera versión del sistema no debe requerir la creación de
  cuentas de usuario individuales por empleado del restaurante.
  - Tipo: no funcional (simplicidad operativa)
  - Origen: `cajero-restaurante.md` · Cajero / Personal operativo
