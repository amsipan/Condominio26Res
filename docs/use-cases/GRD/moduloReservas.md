# Módulo GRD - Reservas

## Índice

- [CU-01 Reservar Área Común](#cu-01-reservar-área-común)
- [CU-02 Reservar Salón de Eventos](#cu-02-reservar-salón-de-eventos)
- [CU-03 Reservar Área Recreacional](#cu-03-reservar-área-recreacional)
- [CU-04 Visualizar Disponibilidad de Espacios](#cu-04-visualizar-disponibilidad-de-espacios)
- [CU-05 Cancelar Reserva](#cu-05-cancelar-reserva)
- [CU-06 Agregar Observaciones de Reserva](#cu-06-agregar-observaciones-de-reserva)

---

# CU-01 Reservar Área Común

## Descripción

Permite al Residente realizar la reserva de un área común disponible, seleccionando fecha, hora y espacio deseado.

## Actor Principal

Residente

## Precondiciones

- El Residente debe haber iniciado sesión en el sitema.
- Deben existir áreas comunes registradas en el sistema de gestión del condominio.
- El módulo de reservas debe encontrarse disponible.

## Flujo Principal

1. El Residente ingresa al módulo de reservas de areas comunes.
2. El sistema muestra las opciones de áreas comunes disponibles.
3. El Residente selecciona el área común que desea reservar.
4. El sistema consulta la disponibilidad del espacio seleccionado.
5. El Residente selecciona la fecha y horario de la reserva.
6. El sistema valida que la información ingresada sea correcta y que el espacio esté disponible.
7. El sistema registra la reserva del área común.
8. El sistema notifica al Residente la confirmación de la reserva.

## Postcondiciones

- La reserva queda registrada en el sistema.
- El espcio disponible queda no disponible en la fecha y horario seleccionado.
- El sistema conserva la fecha, hora y datos del Residente asociados en la reserva.

---

# CU-02 Reservar Salón de Eventos

## Descripción

Permite al Residente reservar la reserva de un salón de eventos del condominio, seleccionando fecha, hora y espacio deseado.

## Actor Principal
Residente

## Precondiciones

- El Residente debe haber iniciado sesión en el sistema.
- El salón de eventos debe encontrarse registrado dentro del sistema de gestión del condominio.
- El módulo reservas debe encontrarse disponible.

## Flujo Principal

1. El Residente ingresa al módulo de reservas de espacios comunes.
2. El sistema muestra las opciones de áreas comunes disponibles.
3. El Residente selecciona la opción de reservar salón de eventos.
4. El sistema consulta la disponibilidad del salón de eventos seleccionado.
5. El Residente selecciona la fecha y horario de la reserva.
6. El sistema valida que la información ingresada sea correcta y que el salón de eventos esté disponible.
7. El sistema registra la reserva del salón de eventos.
8. El sistema notifica al Residente la confirmación de la reserva.

## Postcondiciones

- La reserva queda registrada en el sistema.
- El espcio disponible queda no disponible en la fecha y horario seleccionado.
- El sistema conserva la fecha, hora y datos del Residente asociados en la reserva.

---

# CU-03 Reservar Área Recreacional

## Descripción

Permite al Residente realizar la reserva de un área recreacional, seleccionando fecha, hora y espacio deseado.

## Actor Principal

Residente

## Precondiciones

- El Residente debe haber iniciado sesión en el sitema.
- Deben existir áreas reaciacionales registradas en el sistema de gestión del condominio.
- El módulo de reservas debe encontrarse disponible.

## Flujo Principal

1. El Residente ingresa al módulo de reservas de espacios comunes.
2. El sistema muestra las opciones de áreas comunes disponibles.
3. El Residente selecciona la opción de reservar área recreacional.
4. El sistema consulta la disponibilidad del área recreacional seleccionada.
5. El Residente selecciona la fecha y horario de la reserva.
6. El sistema valida que la información ingresada sea correcta y que el salón de eventos esté disponible.
7. El sistema registra la reserva del área recreacional.
8. El sistema notifica al Residente la confirmación de la reserva.

## Postcondiciones

- La reserva queda registrada en el sistema.
- El espcio disponible queda no disponible en la fecha y horario seleccionado.
- El sistema conserva la fecha, hora y datos del Residente asociados en la reserva.

---

# CU-04 Visualizar Disponibilidad de Espacios

## Descripción

Permite al sistema mostrar la disponibilidad actual de los espacios comunes, salón de eventos y áreas recreacionales del condominio al momento de realizar una reserva.

## Actor Principal

Sistema

## Precondiciones

- Debe exitir almenos un área común, salón de eventos o área recreacional registrada.
- El módulo de reservas debe encontrarse disponible.

## Flujo Principal

1. El sistema recibe la solicitud de consulta de disponibilidad desde el proceso de reserva.
2. El sistema consulta los registros de reservas existentes para el espacio seleccionado.
3. El sistema identifica los horarios disponibles y no disponibles.
4. El sistema muestra al Residente la disponibilidad actualizada del espacio consultado.

## Postcondiciones

- La disponibilidad de los espacios queda visible para el Residente.
- El sistema mantiene actualziada la disponibilidad de espacios.
- La información de disponibilida refleja la información real de las reservas registradas.

# CU-05 Cancelar Reserva

## Descripción

Permite al Residente realizar la cancelación de una Reserva

## Actor Principal
Residente

## Precondiciones

- El Residente debe haber iniciado sesión en el sistema.
- Debe existir al menos una reserva activa registrada a nombre del Residente.
- El módulo de reservas debe encontrarse disponible.

## Flujo Principal

1. El Residente ingresa al módulo de reservas de espacios comunes.
2. El sistema muestra el listado de reservas activas del Residente.
3. El Residente selecciona la reserva que desea cancelar.
4. El sistema solicita confirmación antes de proceder con la cancelación.
5. El Residente confirma la cancelación.
6. El sistema cancela la reserva seleccionada.
7. El sistema actualiza la disponibilidad del espacio liberado.
8. El sistema notifica al Residente la confirmación de la cancelación.

## Postcondiciones

- La reserva queda cancelada dentro del sistema.
- El espacio liberado queda nuevamente disponible para el horario correspondiente.
- El sistema conserva un registro de la cancelación realizada.

---

# CU-06 Agregar Observaciones de Reserva

## Descripción

Permite al Residente o al Administrador registrar observaciones, comentarios o notas especiales asociadas a una reserva específica.

## Actor Principal

Residente, Administrador

## Precondiciones

- El usuario (Residente o Administrador) debe haber iniciado sesión en el sistema.
- Debe existir la reserva correspondiente registrada en el sistema.
- El módulo de reservas debe encontrarse disponible.

## Flujo Principal

1. El usuario ingresa al módulo de reservas de espacios comunes.
2. El sistema muestra el listado de reservas (reservas del Residente si es este actor, o todas las reservas si es Administrador).
3. El usuario selecciona la reserva a la cual desea agregar observaciones.
4. El usuario selecciona la opción de agregar observaciones.
5. El usuario ingresa el texto de la observación.
6. El sistema valida que la información ingresada sea correcta.
7. El sistema registra las observaciones y las asocia a la reserva.
8. El sistema notifica al usuario la confirmación del registro de observaciones.

## Postcondiciones

- Las observaciones quedan asociadas a la reserva dentro del sistema.
- El sistema conserva la fecha, hora y datos del usuario asociado en el registro de la observación.