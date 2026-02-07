# Informe técnico: Guía para el diagrama BPMN — Clínica Salud Viva

## Nombre del taller
Taller: Modelado BPMN para el proceso de agendamiento de citas — Clínica Salud Viva

## Integrantes
- Julián Barragán Pérez
- Juan David González Rubio
- Josue Sarmiento

## Resumen ejecutivo
El presente informe describe el modelado del proceso de agendamiento de citas médicas de la Clínica Salud Viva utilizando notación BPMN. Se identifican los actores involucrados, actividades principales, eventos, decisiones y flujos del proceso. El objetivo es representar de forma estructurada el funcionamiento actual del agendamiento, sirviendo como base para futuros análisis de mejora dentro del marco de Arquitectura Empresarial.

## Alcance
El modelo BPMN cubre desde la solicitud inicial de la cita por parte del paciente hasta la confirmación final mediante notificación electrónica. No se incluyen procesos clínicos posteriores ni gestión de pagos.

## Relación con Arquitectura Empresarial
Este modelado BPMN corresponde a la capa de negocio dentro de la Arquitectura Empresarial, permitiendo visualizar el flujo operativo del agendamiento de citas. El proceso sirve como insumo para decisiones posteriores en las capas de aplicaciones, datos e infraestructura, facilitando la alineación entre los objetivos del negocio y los sistemas de información.

## 1. Definición de roles (swimlanes)
Para Clínica Salud Viva se recomiendan cuatro swimlanes horizontales:

- Paciente
- Sistema de Citas
- Base de Datos
- Servicio de Notificaciones

Cada swimlane representa un actor responsable de las actividades ubicadas dentro de su carril.

## 2. Evento de inicio
El proceso debe comenzar con un evento que lo dispare. Propuesta:

- Evento de inicio: Paciente solicita agendar una cita médica (evento de inicio simple).

## 3. Actividades principales (por orden y por swimlane)
Coloque las actividades como tareas (rectángulos) dentro del carril del actor correspondiente:

Paciente:
- Seleccionar especialidad
- Seleccionar médico
- Seleccionar fecha
- Confirmar cita

Sistema de Citas:
- Mostrar disponibilidad
- Registrar cita

Base de Datos:
- Guardar información de la cita

Servicio de Notificaciones:
- Enviar correo o SMS de confirmación

### Artefactos de datos recomendados
Se recomienda incluir un objeto de datos "Cita médica" asociado a las tareas "Registrar cita" y "Guardar información", representando el intercambio de información entre el Sistema de Citas y la Base de Datos.

## 4. Decisiones (gateways)
Las decisiones se modelan mediante Exclusive Gateways (XOR), ya que solo una ruta puede ejecutarse a la vez. Se proponen al menos dos gateways clave:

-- Gateway 1 — ¿Hay disponibilidad?
	- Ubicación: después de "Mostrar disponibilidad" del Sistema de Citas.
	- Pregunta: ¿Hay cupos?
		- Sí: continuar con selección de fecha por parte del paciente.
		- No: mostrar alternativas o volver a seleccionar médico o especialidad.

- Gateway 2 — ¿Paciente confirma?
	- Ubicación: después de "Seleccionar fecha".
	- Pregunta: ¿Confirma la cita?
		- Sí: avanzar a registrar cita.
		- No: terminar el proceso sin registrar cita.

## 5. Eventos finales
Defina dos finales posibles:

- Fin exitoso: Cita confirmada y notificada al paciente.
- Fin alternativo: Proceso cancelado por el paciente (sin cita registrada).

## 6. Estructura completa del flujo (texto)
Vista lineal del proceso para replicar en el diagrama:

Inicio
↓
Paciente selecciona especialidad
↓
Paciente selecciona médico
↓
Sistema de Citas muestra disponibilidad
↓
Gateway: ¿Hay cupos?
	- No → mostrar alternativas o volver a seleccionar médico o especialidad
	- Sí → seguir
↓
Paciente selecciona fecha
↓
Gateway: ¿Confirma cita?
	- No → Fin cancelado
	- Sí →
↓
Sistema registra cita
↓
Base de Datos guarda información
↓
Servicio de Notificaciones envía correo/SMS
↓
Fin exitoso

## 7. Checklist para el diagrama final
Antes de entregar el diagrama, confirme que contiene:

- Evento de inicio claramente identificado.
- Uno o más eventos finales (éxito y alternativo) explícitos.
- Actividades modeladas como tareas (rectángulos) ubicadas en el swimlane correcto.
- Gateways (rombos) para decisiones importantes con rutas etiquetadas (sí/no, alternativas).
- Flechas que indiquen el flujo con dirección y sin ambigüedad.
- Swimlanes separados por rol para representar responsabilidades.
- Flujo lógico y validado con los stakeholders (p. ej. personal de la clínica).

## 8. Sugerencias adicionales
- En el diagrama final incluya anotaciones o comentarios donde se hayan asumido reglas de negocio (p. ej. política de reprogramación, tiempos de espera).
- Considere variantes del proceso (reagendamiento, incumplimiento del paciente, bloqueos por falta de información).

## Referencias y recursos
- Especificación BPMN: https://www.omg.org/spec/BPMN/
- Recomendación: usar herramientas como draw.io o diagrams.net para dibujar el diagrama y exportar PDF/PNG.

---

Este documento forma parte de la entrega del taller sobre Arquitectura Empresarial (AREM) — Clínica Salud Viva.