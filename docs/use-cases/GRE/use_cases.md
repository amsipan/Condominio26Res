# Módulo GRE - Check-in

## Índice

* [CU-01 Enviar Alerta](#cu-01-enviar-alerta)
* [CU-02 Programar Visita](#cu-02-programar-visita)
* [CU-03 Registrar Entrada](#cu-03-registrar-entrada)
* [CU-04 Notificar Entrada](#cu-04-notificar-entrada)
* [CU-05 Registrar Historial](#cu-05-registrar-historial)
* [CU-06 Registrar Ingreso Parqueadero](#cu-06-registrar-ingreso-parqueadero)

---

# CU-01 Enviar Alerta

## Descripción

Permite al Administrador o al Personal de Seguridad enviar una alerta a los residentes del condominio en situaciones de emergencia, simulacro o comunicación importante.

## Actor Principal

Administrador, Personal de Seguridad

## Precondiciones

* El actor ha iniciado sesión.
* El actor posee permisos para enviar alertas.
* Existen residentes registrados para recibir la alerta.

## Postcondiciones

* La alerta queda enviada a los residentes.
* La alerta queda registrada para su posterior consulta.

## Escenario Básico

1. El caso de uso comienza cuando el Administrador o el Personal de Seguridad solicita enviar una alerta.
2. El Módulo muestra el formulario para registrar la alerta.
3. El actor proporciona el tipo de alerta, el mensaje y los destinatarios.
4. El Módulo valida la información ingresada.
5. El actor confirma el envío de la alerta.
6. El Módulo envía la alerta a los residentes seleccionados.
7. El caso de uso termina cuando el Módulo muestra el mensaje "Alerta enviada exitosamente".

## Escenarios Alternos

### A1. Campos incompletos

1. El caso de uso comienza cuando el actor solicita enviar una alerta.
2. El actor proporciona la información de la alerta.
3. El Módulo detecta que uno o más campos obligatorios están vacíos.
4. El Módulo muestra el mensaje "Todos los campos son obligatorios".
5. El caso de uso finaliza sin enviar la alerta.

### A2. Destinatarios no disponibles

1. El caso de uso comienza cuando el actor solicita enviar una alerta.
2. El actor selecciona los destinatarios de la alerta.
3. El Módulo detecta que no existen residentes disponibles para recibir la alerta.
4. El Módulo muestra el mensaje "No existen destinatarios disponibles".
5. El caso de uso finaliza sin enviar la alerta.

---

# CU-02 Programar Visita

## Descripción

Permite al Residente programar una visita antes de que el visitante llegue al condominio. La información registrada sirve para facilitar el ingreso y permitir que el Personal de Seguridad pueda verificar la autorización.

## Actor Principal

Residente

## Precondiciones

* El Residente ha iniciado sesión.
* El Residente posee una cuenta activa.
* El visitante todavía no ha ingresado al condominio.

## Postcondiciones

* La visita queda programada.
* El Personal de Seguridad puede consultar la visita programada.

## Escenario Básico

1. El caso de uso comienza cuando el Residente solicita programar una visita.
2. El Módulo muestra el formulario de programación de visita.
3. El Residente proporciona los datos del visitante.
4. El Residente proporciona la fecha y hora estimada de llegada.
5. El Residente indica el motivo de la visita.
6. El Módulo valida la información ingresada.
7. El Residente confirma la programación de la visita.
8. El Módulo registra la visita programada.
9. El caso de uso termina cuando el Módulo muestra el mensaje "Visita programada exitosamente".

## Escenarios Alternos

### A1. Campos incompletos

1. El caso de uso comienza cuando el Residente programa una visita.
2. El Residente proporciona los datos del visitante.
3. El Módulo detecta que uno o más campos obligatorios están vacíos.
4. El Módulo muestra el mensaje "Todos los campos son obligatorios".
5. El caso de uso finaliza sin programar la visita.

### A2. Fecha u hora no válida

1. El caso de uso comienza cuando el Residente programa una visita.
2. El Residente proporciona la fecha y hora estimada de llegada.
3. El Módulo detecta que la fecha u hora ingresada no es válida.
4. El Módulo muestra el mensaje "La fecha u hora ingresada no es válida".
5. El caso de uso finaliza sin programar la visita.

### A3. Visitante ya programado

1. El caso de uso comienza cuando el Residente programa una visita.
2. El Residente proporciona los datos del visitante.
3. El Módulo detecta que el visitante ya tiene una visita programada para la misma fecha.
4. El Módulo muestra el mensaje "El visitante ya tiene una visita programada".
5. El caso de uso finaliza sin registrar una nueva programación.

---

# CU-03 Registrar Entrada

## Descripción

Permite al Personal de Seguridad registrar el ingreso de un visitante al condominio. Este caso de uso incluye la notificación al residente y el registro del historial de ingreso.

## Actor Principal

Personal de Seguridad

## Precondiciones

* El Personal de Seguridad ha iniciado sesión.
* El visitante se encuentra en el punto de ingreso del condominio.
* El Personal de Seguridad posee permisos para registrar entradas.

## Postcondiciones

* La entrada del visitante queda registrada.
* El residente recibe la notificación de entrada.
* El ingreso queda guardado en el historial.
* Si el visitante ingresa con vehículo, se puede registrar el ingreso al parqueadero.

## Escenario Básico

1. El caso de uso comienza cuando el visitante llega al condominio.
2. El Personal de Seguridad solicita registrar la entrada del visitante.
3. El Módulo muestra el formulario de registro de entrada.
4. El Personal de Seguridad proporciona los datos del visitante.
5. El Personal de Seguridad indica el residente al que visita.
6. El Personal de Seguridad registra la fecha, hora y motivo de la visita.
7. El Módulo valida la información ingresada.
8. El Módulo ejecuta el caso de uso "Notificar entrada".
9. El Módulo ejecuta el caso de uso "Registrar historial".
10. El caso de uso termina cuando el Módulo muestra el mensaje "Entrada registrada exitosamente".

## Escenarios Alternos

### A1. Visitante no autorizado

1. El caso de uso comienza cuando el visitante llega al condominio.
2. El Personal de Seguridad proporciona los datos del visitante.
3. El Módulo detecta que el visitante no tiene autorización de ingreso.
4. El Módulo muestra el mensaje "Visitante no autorizado".
5. El caso de uso finaliza sin registrar la entrada.

### A2. Residente no encontrado

1. El caso de uso comienza cuando el Personal de Seguridad registra la entrada del visitante.
2. El Personal de Seguridad indica el residente al que visita.
3. El Módulo detecta que el residente no se encuentra registrado.
4. El Módulo muestra el mensaje "Residente no encontrado".
5. El caso de uso finaliza sin registrar la entrada.

### A3. Campos incompletos

1. El caso de uso comienza cuando el Personal de Seguridad registra la entrada del visitante.
2. El Personal de Seguridad proporciona los datos del visitante.
3. El Módulo detecta que uno o más campos obligatorios están vacíos.
4. El Módulo muestra el mensaje "Todos los campos son obligatorios".
5. El caso de uso finaliza sin registrar la entrada.

---

# CU-04 Notificar Entrada

## Descripción

Permite notificar al Residente que su visitante ha llegado al condominio. Este caso de uso forma parte obligatoria del registro de entrada.

## Actor Principal

Módulo GRE

## Precondiciones

* Se ha iniciado el caso de uso "Registrar entrada".
* Los datos del visitante han sido validados.
* El residente se encuentra registrado.

## Postcondiciones

* El Residente recibe la notificación de llegada del visitante.

## Escenario Básico

1. El caso de uso comienza cuando el Módulo valida los datos del visitante.
2. El Módulo identifica al Residente relacionado con la visita.
3. El Módulo genera la notificación de entrada.
4. El Módulo envía la notificación al Residente.
5. El caso de uso termina cuando el Módulo muestra el mensaje "Notificación enviada exitosamente".

## Escenarios Alternos

### A1. No se puede enviar la notificación

1. El caso de uso comienza cuando el Módulo genera la notificación de entrada.
2. El Módulo intenta enviar la notificación al Residente.
3. El Módulo detecta un error durante el envío.
4. El Módulo muestra el mensaje "No se pudo enviar la notificación".
5. El caso de uso finaliza sin enviar la notificación.

### A2. Residente sin medio de contacto disponible

1. El caso de uso comienza cuando el Módulo identifica al Residente relacionado con la visita.
2. El Módulo detecta que el Residente no tiene un medio de contacto disponible.
3. El Módulo muestra el mensaje "El residente no tiene un medio de contacto registrado".
4. El caso de uso finaliza sin enviar la notificación.

---

# CU-05 Registrar Historial

## Descripción

Permite guardar la información del ingreso de un visitante en el historial del condominio. Este caso de uso forma parte obligatoria del registro de entrada.

## Actor Principal

Módulo GRE

## Precondiciones

* Se ha iniciado el caso de uso "Registrar entrada".
* Los datos del visitante han sido validados.
* La entrada del visitante ha sido aceptada.

## Postcondiciones

* El ingreso del visitante queda registrado en el historial.
* La información puede ser consultada posteriormente.

## Escenario Básico

1. El caso de uso comienza cuando el Módulo confirma el registro de entrada.
2. El Módulo recopila los datos del visitante, residente, fecha, hora y motivo de visita.
3. El Módulo organiza la información del ingreso.
4. El Módulo registra la información en el historial.
5. El caso de uso termina cuando el Módulo muestra el mensaje "Historial registrado exitosamente".

## Escenarios Alternos

### A1. Error al guardar el historial

1. El caso de uso comienza cuando el Módulo recopila los datos del ingreso.
2. El Módulo intenta registrar la información en el historial.
3. El Módulo detecta un error al guardar la información.
4. El Módulo muestra el mensaje "No se pudo registrar el historial".
5. El caso de uso finaliza sin guardar el historial.

### A2. Información incompleta del ingreso

1. El caso de uso comienza cuando el Módulo recopila los datos del ingreso.
2. El Módulo detecta que la información del visitante o del residente está incompleta.
3. El Módulo muestra el mensaje "La información del ingreso está incompleta".
4. El caso de uso finaliza sin registrar el historial.

---

# CU-06 Registrar Ingreso Parqueadero

## Descripción

Permite al Personal de Seguridad registrar el ingreso de un vehículo al parqueadero de visita. Este caso de uso extiende a "Registrar entrada", ya que solo se realiza cuando el visitante ingresa con vehículo.

## Actor Principal

Personal de Seguridad

## Precondiciones

* Se ha iniciado el caso de uso "Registrar entrada".
* El visitante ingresa con vehículo.
* Existe disponibilidad de parqueadero de visita.

## Postcondiciones

* El ingreso del vehículo queda registrado.
* El parqueadero asignado queda asociado a la visita.

## Escenario Básico

1. El caso de uso comienza cuando el visitante indica que ingresa con vehículo.
2. El Personal de Seguridad solicita registrar el ingreso al parqueadero.
3. El Módulo muestra el formulario de ingreso al parqueadero.
4. El Personal de Seguridad proporciona los datos del vehículo.
5. El Personal de Seguridad selecciona el parqueadero disponible.
6. El Módulo valida la información ingresada.
7. El Personal de Seguridad confirma el registro del parqueadero.
8. El Módulo registra el ingreso del vehículo.
9. El caso de uso termina cuando el Módulo muestra el mensaje "Ingreso al parqueadero registrado exitosamente".

## Escenarios Alternos

### A1. No existe parqueadero disponible

1. El caso de uso comienza cuando el visitante indica que ingresa con vehículo.
2. El Personal de Seguridad solicita registrar el ingreso al parqueadero.
3. El Módulo detecta que no existen parqueaderos disponibles.
4. El Módulo muestra el mensaje "No existen parqueaderos disponibles".
5. El caso de uso finaliza sin registrar el ingreso al parqueadero.

### A2. Datos del vehículo incompletos

1. El caso de uso comienza cuando el Personal de Seguridad registra el ingreso al parqueadero.
2. El Personal de Seguridad proporciona los datos del vehículo.
3. El Módulo detecta que uno o más campos obligatorios están vacíos.
4. El Módulo muestra el mensaje "Todos los campos son obligatorios".
5. El caso de uso finaliza sin registrar el ingreso al parqueadero.

### A3. Placa ya registrada en una visita activa

1. El caso de uso comienza cuando el Personal de Seguridad proporciona los datos del vehículo.
2. El Módulo valida la placa del vehículo.
3. El Módulo detecta que la placa ya se encuentra asociada a una visita activa.
4. El Módulo muestra el mensaje "La placa ya se encuentra registrada en una visita activa".
5. El caso de uso finaliza sin registrar el ingreso al parqueadero.
