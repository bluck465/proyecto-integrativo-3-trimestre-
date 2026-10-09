# Mano Ya — Documentación

<aside>
🚀

**Mano Ya** conecta trabajadores de distintos oficios con clientes de su zona local para facilitar oportunidades de empleo rápidas, accesibles y verificables.

</aside>

## Visión del producto y descripción general

### Resumen ejecutivo

Mano Ya es un MVP de marketplace local de servicios. Permite que un cliente encuentre trabajadores por oficio y zona, revise su perfil y disponibilidad, solicite un servicio, reciba un presupuesto y confirme el pago dentro de la aplicación. El trabajador puede registrar su especialidad barbería, manicura, estilismo, costura, electricidad, albañilería, ingeniería, entre otras, gestionar su disponibilidad y marcar un servicio como pagado una vez verificado el abono.

### Propuesta de valor

- **Para clientes:** encontrar rápidamente talento local, filtrar por oficio y zona, solicitar trabajos con contexto suficiente y contar con un flujo claro de pago.
- **Para trabajadores:** mostrar sus capacidades, recibir oportunidades cercanas, controlar cuándo están disponibles y tener trazabilidad básica del servicio y el cobro.
- **Para la comunidad:** impulsar el empleo local y reducir la fricción entre la necesidad de un servicio y la persona capaz de ejecutarlo.

### Alcance delimitado del MVP — 3 semanas

**Incluido:**

- Registro y perfil de trabajador multi-oficio.
- Catálogo y búsqueda por oficio y zona.
- Perfil con datos de contacto y disponibilidad.
- Solicitud de servicio con descripción, fecha y presupuesto.
- Envío de datos de cobro/pago dentro de la app.
- Confirmación por el cliente y botón del trabajador: **“Pago Recibido / Trabajo Pagado”**.
- Pago por cuotas o hitos para presupuestos superiores a **$800**.
- Aplicación híbrida: experiencia Web y compilación/pruebas en Android Studio.
- Persistencia en Firebase o Supabase y autenticación inicial.

**Fuera de alcance para este MVP:**

- Pasarela de pago bancaria integrada o custodia de fondos.
- Chat en tiempo real, calificaciones, reseñas y geolocalización avanzada.
- Notificaciones push, facturación fiscal y panel administrativo completo.
- Algoritmo de recomendación, verificación legal de identidad y expansión multi-ciudad.

### Objetivo de producto al cierre de la tercera semana

Entregar un flujo demostrable de extremo a extremo: un trabajador se registra, publica su oficio y disponibilidad; un cliente lo encuentra por zona, solicita un servicio y consulta el presupuesto; ambas partes intercambian los datos de pago; el trabajador confirma el pago y, si el monto supera $800, puede gestionar cuotas o hitos.

### Indicadores de éxito del MVP

- Un usuario puede completar el flujo principal sin bloqueos críticos.
- El catálogo devuelve resultados filtrables por oficio y zona.
- El estado de disponibilidad se refleja de forma consistente en Web y Móvil.
- Un servicio pagado cambia a **Finalizado** solo después de la confirmación del trabajador.
- El equipo puede presentar una demo funcional y reproducible en la tercera semana.

## Historias de usuario — Backlog del producto

> **Definition of Done global:** código integrado en la rama acordada, revisión por otro integrante, validación en Web y/o Android según corresponda, criterios de aceptación probados, manejo de errores y estados vacíos, documentación mínima actualizada y evidencia de prueba adjunta en la tarea del tablero.
> 

| ID | Historia de usuario | Prioridad | Estimación inicial |
| --- | --- | --- | --- |
| HU-01 | **Como trabajador**, quiero registrarme y crear un perfil multi-oficio, para mostrar mis capacidades, zona y datos de contacto a clientes cercanos. | Must | 5 |
| HU-02 | **Como cliente**, quiero buscar trabajadores por oficio y zona, para encontrar rápidamente opciones cercanas y relevantes. | Must | 5 |
| HU-03 | **Como cliente**, quiero enviar una solicitud con detalles del trabajo, fecha y presupuesto, para acordar el servicio con el trabajador. | Must | 5 |
| HU-04 | **Como cliente y trabajador**, quiero intercambiar los datos de cobro y confirmar el pago dentro de la app, para cerrar el servicio con trazabilidad básica. | Must | 5 |
| HU-05 | **Como cliente y trabajador**, quiero configurar cuotas o hitos cuando el presupuesto supera $800, para administrar obras grandes por avances. | Should | 5 |
| HU-06 | **Como trabajador**, quiero cambiar mi estado entre disponible y en descanso/ocupado, para controlar cuándo puedo aceptar nuevos trabajos. | Must | 3 |

### HU-01 — Registro y Perfil Multi-Oficio (Trabajador)

**Como trabajador**, quiero registrarme y crear un perfil multi-oficio con especialidad, zona y datos de contacto, **para** que los clientes puedan conocer mis servicios y contactarme.

**Criterios de aceptación / DoD:**

- [ ]  El usuario puede registrarse e iniciar sesión con correo y contraseña.
- [ ]  El perfil permite seleccionar al menos un oficio de un catálogo configurable: barbería, manicuría, estilismo, costura, electricidad, albañilería, ingeniería y otros.
- [ ]  El perfil permite registrar nombre visible, descripción breve, zona de atención y datos de contacto.
- [ ]  Se validan campos obligatorios y se muestran mensajes de error comprensibles.
- [ ]  El perfil se guarda en Firebase/Supabase y puede editarse posteriormente.
- [ ]  El perfil tiene estado inicial **Disponible para trabajar**.
- [ ]  Se probó el flujo en Web y Android Studio, con evidencia de creación y edición.

### HU-02 — Catálogo y Búsqueda por Oficio y Zona (Cliente)

**Como cliente**, quiero buscar trabajadores por oficio y zona, **para** encontrar opciones cercanas y relevantes.

**Criterios de aceptación / DoD:**

- [ ]  El catálogo muestra tarjetas con nombre, oficio, zona y disponibilidad.
- [ ]  El cliente puede filtrar por oficio.
- [ ]  El cliente puede filtrar por zona.
- [ ]  Los trabajadores no disponibles se identifican visualmente y no se presentan como disponibles.
- [ ]  Existe estado vacío cuando no hay coincidencias.
- [ ]  El cliente puede abrir el perfil del trabajador desde el catálogo.
- [ ]  La búsqueda funciona en Web y Móvil con datos persistidos.

### HU-03 — Solicitud de Servicio y Presupuesto

**Como cliente**, quiero enviar los detalles del trabajo, fecha y presupuesto, **para** solicitar formalmente un servicio.

**Criterios de aceptación / DoD:**

- [ ]  Desde el perfil del trabajador existe una acción **Solicitar servicio**.
- [ ]  El formulario solicita descripción, fecha deseada, ubicación/zona y presupuesto estimado.
- [ ]  El sistema valida descripción, fecha y presupuesto como datos obligatorios.
- [ ]  El trabajador puede consultar las solicitudes recibidas y su estado.
- [ ]  El cliente puede consultar las solicitudes enviadas y su estado.
- [ ]  La solicitud inicia en estado **Pendiente** y conserva fecha de creación.
- [ ]  Se contempla una respuesta visual para carga, éxito y error.

### HU-04 — Módulo de Cobro, Envío de Datos y Confirmación de Pago

**Como trabajador**, quiero enviar los datos de cobro y confirmar que recibí el pago, **para** cerrar el servicio de forma controlada.

**Criterios de aceptación / DoD:**

- [ ]  El trabajador puede registrar o seleccionar sus datos de cobro para una solicitud aceptada.
- [ ]  El cliente puede visualizar los datos de pago asociados al servicio.
- [ ]  El cliente puede registrar que realizó el pago y adjuntar una referencia o comprobante textual.
- [ ]  El servicio pasa a **Pago pendiente de verificación** después de la confirmación del cliente.
- [ ]  Solo el trabajador puede activar **Pago Recibido / Trabajo Pagado**.
- [ ]  Al activar el botón, el servicio pasa a **Finalizado** y guarda fecha/hora de confirmación.
- [ ]  El botón no aparece como confirmado antes de la verificación del trabajador.
- [ ]  Se validan permisos para impedir que un cliente finalice unilateralmente el servicio.

### HU-05 — Configuración de Pago en Cuotas/Hitos

**Como cliente y trabajador**, quiero dividir en cuotas o hitos un presupuesto superior a $800, **para** administrar obras grandes por avances quincenales, mensuales o entregables.

**Criterios de aceptación / DoD:**

- [ ]  Si el presupuesto es mayor a $800, se ofrece configurar cuotas/hitos.
- [ ]  El usuario puede elegir modalidad: quincenal, mensual o por avance/hito.
- [ ]  Cada cuota/hito registra nombre, monto, fecha o condición y estado.
- [ ]  La suma de cuotas/hitos coincide con el presupuesto total, con validación visible.
- [ ]  Cada cuota/hito puede marcarse como pendiente, pagada o verificada.
- [ ]  El servicio no se considera totalmente finalizado mientras existan cuotas pendientes.
- [ ]  Para presupuestos de $800 o menos, la opción es opcional o no se muestra según la decisión del equipo.

### HU-06 — Control de Estado del Trabajador

**Como trabajador**, quiero cambiar mi estado entre **Disponible para trabajar** y **En descanso / Ocupado**, **para** controlar la recepción de nuevas solicitudes.

**Criterios de aceptación / DoD:**

- [ ]  Existe un toggle visible en el perfil del trabajador.
- [ ]  El estado solo puede ser uno de los dos valores definidos.
- [ ]  El cambio se persiste y se refleja en catálogo, perfil y solicitudes.
- [ ]  Un trabajador en descanso/ocupado no se muestra como disponible.
- [ ]  El trabajador puede volver a estar disponible sin perder sus datos.
- [ ]  Se valida el comportamiento en Web y Android Studio.

## Matriz de roles y responsabilidades

| Integrante | Rol principal | Responsabilidades | Entregables clave |
| --- | --- | --- | --- |
| Integrante 1 | UI/UX & Mobile Dev | Figma, wireframes, UI Kit, maquetación de vistas móviles y ejecución en Android Studio. | Prototipo navegable, componentes visuales, pantallas Móvil, build funcional. |
| Integrante 2 | Web Dev & Backend/DB | Modelo de datos Firebase/Supabase, API/backend, autenticación técnica y catálogo/búsqueda Web. | Esquema de datos, endpoints/servicios, catálogo Web, persistencia. |
| Integrante 3 | Fullstack Dev, QA & Scrum Master | Flujo de pagos/cuotas, toggle de disponibilidad, integración, gestión del tablero Notion y pruebas integrales. | Flujo de negocio, QA, evidencias, ceremonias, demo y control de alcance. |

### Acuerdos de trabajo del equipo

- [ ]  Daily de 10–15 minutos: ayer, hoy, bloqueos.
- [ ]  Revisión de tablero al inicio y cierre de cada jornada.
- [ ]  Ninguna tarea pasa a **Hecho** sin criterios de aceptación y evidencia.
- [ ]  Todo cambio de alcance se registra como decisión y se prioriza contra el MVP.
- [ ]  Integración frecuente; evitar acumular cambios sin revisión.
- [ ]  Si aparece un bloqueo de más de 4 horas, se escala al Scrum Master.

## Plan Scrum por Sprint

### Sprint 1 — Fundamentos, UI/UX y setup técnico (Semana 1)

**Objetivo:** prototipo navegable en Figma, esquema de base de datos, proyecto híbrido compilando en Android Studio/Web y autenticación inicial.

**Incremento esperado:** navegación base + login/registro funcional + estructura de datos inicial.

#### Integrante 1 — UI/UX & Mobile Dev

- [ ]  **S1-01 Wireframes del flujo principal** · **5 pts** · [Asignado a: Integrante 1]
    - Login/registro, perfil trabajador, catálogo, detalle, solicitud y pago.
- [ ]  **S1-02 UI Kit y prototipo navegable en Figma** · **5 pts** · [Asignado a: Integrante 1]
    - Colores, tipografía, botones, inputs, tarjetas, estados y navegación.
- [ ]  **S1-03 Setup de proyecto híbrido y navegación móvil** · **3 pts** · [Asignado a: Integrante 1]
    - Proyecto compilando en Android Studio y ruta equivalente para Web.

#### Integrante 2 — Web Dev & Backend/DB

- [ ]  **S1-04 Modelo de datos inicial** · **5 pts** · [Asignado a: Integrante 2]
    - Usuarios, perfiles, oficios, solicitudes, pagos y cuotas/hitos.
- [ ]  **S1-05 Configuración Firebase/Supabase y autenticación base** · **5 pts** · [Asignado a: Integrante 2]
    - Proyecto, variables de entorno, reglas mínimas y registro/login.
- [ ]  **S1-06 Shell Web y servicio de acceso a datos** · **3 pts** · [Asignado a: Integrante 2]
    - Layout base, rutas, cliente API/SDK y manejo inicial de errores.

#### Integrante 3 — Fullstack Dev, QA & Scrum Master

- [ ]  **S1-07 Backlog, tablero y Definition of Done** · **3 pts** · [Asignado a: Integrante 3]
    - Crear tareas, responsables, estados, criterios y acuerdos de trabajo.
- [ ]  **S1-08 Contratos de datos y estados de negocio** · **3 pts** · [Asignado a: Integrante 3]
    - Estados de solicitud, pago, disponibilidad y reglas de transición.
- [ ]  **S1-09 Smoke test de setup y riesgos iniciales** · **2 pts** · [Asignado a: Integrante 3]
    - Verificar build, login, persistencia mínima y registrar bloqueos.

**Criterio de cierre Sprint 1:** los tres integrantes pueden ejecutar el proyecto, navegar el flujo base y crear un usuario de prueba persistido.

### Sprint 2 — Catálogo multi-oficio, perfiles y solicitudes (Semana 2)

**Objetivo:** catálogo Web/Móvil, perfiles con toggle de disponibilidad y flujo de envío de solicitudes.

**Incremento esperado:** cliente encuentra un trabajador y registra una solicitud consultable por ambas partes.

#### Integrante 1 — UI/UX & Mobile Dev

- [ ]  **S2-01 Pantallas móviles de catálogo y filtros** · **5 pts** · [Asignado a: Integrante 1]
    - Lista, filtros por oficio/zona, estados vacío/carga/error.
- [ ]  **S2-02 Perfil de trabajador y toggle de disponibilidad** · **3 pts** · [Asignado a: Integrante 1]
    - Vista editable y estados visuales consistente.
- [ ]  **S2-03 Formulario móvil de solicitud de servicio** · **3 pts** · [Asignado a: Integrante 1]
    - Descripción, fecha, zona, presupuesto y confirmación.

#### Integrante 2 — Web Dev & Backend/DB

- [ ]  **S2-04 Catálogo Web con filtros por oficio y zona** · **5 pts** · [Asignado a: Integrante 2]
    - Consulta persistida, filtros combinables y paginación simple si aplica.
- [ ]  **S2-05 CRUD de perfil y disponibilidad** · **3 pts** · [Asignado a: Integrante 2]
    - Actualización segura y lectura consistente del estado.
- [ ]  **S2-06 API/servicio de solicitudes** · **5 pts** · [Asignado a: Integrante 2]
    - Crear, listar y actualizar solicitudes con permisos por rol.

#### Integrante 3 — Fullstack Dev, QA & Scrum Master

- [ ]  **S2-07 Integración del flujo cliente-trabajador** · **3 pts** · [Asignado a: Integrante 3]
    - Perfil → solicitud → bandeja de solicitudes en ambas vistas.
- [ ]  **S2-08 Reglas de disponibilidad y estados de solicitud** · **3 pts** · [Asignado a: Integrante 3]
    - Evitar nuevas solicitudes a perfiles no disponibles y documentar transiciones.
- [ ]  **S2-09 Pruebas funcionales de HU-01, HU-02, HU-03** · **5 pts** · [Asignado a: Integrante 3]
    - Matriz de casos, regresión y reporte de incidencias.

**Criterio de cierre Sprint 2:** un cliente puede encontrar un trabajador por oficio/zona, abrir su perfil y enviar una solicitud que el trabajador puede consultar.

### Sprint 3 — Pagos, cuotas, QA y presentación (Semana 3)

**Objetivo:** implementar datos de pago, confirmación de **Pago Recibido**, cuotas/hitos para presupuestos altos, pruebas finales y demo.

**Incremento esperado:** flujo completo de servicio solicitado → pago reportado → pago verificado → finalizado.

#### Integrante 1 — UI/UX & Mobile Dev

- [ ]  **S3-01 Pantallas móviles de cobro y confirmación** · **5 pts** · [Asignado a: Integrante 1]
    - Datos de pago, comprobante/referencia, estados y confirmación.
- [ ]  **S3-02 UI móvil de cuotas/hitos** · **3 pts** · [Asignado a: Integrante 1]
    - Alta, edición, resumen de montos y estados.
- [ ]  **S3-03 Preparación de build y guion visual de demo** · **2 pts** · [Asignado a: Integrante 1]
    - Build Android, capturas y recorrido de presentación.

#### Integrante 2 — Web Dev & Backend/DB

- [ ]  **S3-04 Persistencia y permisos del flujo de pagos** · **5 pts** · [Asignado a: Integrante 2]
    - Datos de cobro, confirmación del cliente y verificación del trabajador.
- [ ]  **S3-05 Modelo y servicios de cuotas/hitos > $800** · **5 pts** · [Asignado a: Integrante 2]
    - Validación del total, modalidad, estados y reglas de cierre.
- [ ]  **S3-06 Vista Web de estados, pagos y cuotas** · **3 pts** · [Asignado a: Integrante 2]
    - Panel claro para consultar el avance del servicio.

#### Integrante 3 — Fullstack Dev, QA & Scrum Master

- [ ]  **S3-07 Integración end-to-end y cierre de estados** · **5 pts** · [Asignado a: Integrante 3]
    - Pago cliente → verificación trabajador → Finalizado; restricciones de permisos.
- [ ]  **S3-08 QA final, regresión y corrección de incidencias críticas** · **5 pts** · [Asignado a: Integrante 3]
    - Web, Android Studio, casos positivos/negativos y evidencia.
- [ ]  **S3-09 Demo, retrospectiva y documentación final** · **3 pts** · [Asignado a: Integrante 3]
    - Guion de demo, riesgos pendientes, decisiones y retrospectiva.

**Criterio de cierre Sprint 3:** el MVP tiene un flujo end-to-end demostrable, sin incidencias críticas abiertas, con evidencia de pruebas y documentación final.

## Definition of Ready y control del tablero

### Definition of Ready — una tarea puede entrar al Sprint si:

- [ ]  Tiene un resultado verificable y está vinculada a una HU o entregable.
- [ ]  Tiene responsable explícito mediante la etiqueta **[Asignado a: Integrante X]**.
- [ ]  Tiene estimación de **1, 2, 3 o 5 puntos**.
- [ ]  Se conocen sus dependencias y criterios de aceptación.
- [ ]  Puede completarse dentro de la semana del Sprint.

### Flujo de estados del tablero

**Pendiente → En curso → En revisión → Hecho**

- **Pendiente:** definida, estimada y lista para iniciar.
- **En curso:** el responsable está trabajando activamente.
- **En revisión:** implementación terminada; falta revisión, integración o evidencia.
- **Hecho:** cumple DoD y no tiene bloqueos de aceptación.

### Reglas de priorización

1. Primero desbloquear dependencias del flujo principal.
2. Priorizar Must del MVP antes de mejoras visuales.
3. No iniciar más de una tarea grande por integrante sin cerrar la anterior.
4. Las incidencias críticas tienen prioridad sobre tareas nuevas.
5. Cualquier trabajo fuera de alcance se registra como **Backlog futuro**.

## Riesgos, decisiones y pendientes

| Tipo | Elemento | Respuesta / responsable |
| --- | --- | --- |
| Riesgo | Tres semanas pueden ser insuficientes para una pasarela real. | Mantener pago manual con datos/referencia; Integrante 3 controla alcance. |
| Riesgo | Diferencias entre Web y Android. | Validación cruzada al cierre de cada Sprint; Integrantes 1 y 3. |
| Riesgo | Permisos incorrectos en pagos. | Reglas por rol y pruebas negativas; Integrantes 2 y 3. |
| Riesgo | Montos de cuotas no suman el total. | Validación de suma antes de guardar; Integrante 2. |
| Decisión | Usar Firebase o Supabase como backend del MVP. | Elegir una opción durante Sprint 1 y documentar la decisión. |
| Decisión | El trabajador es quien confirma **Pago Recibido / Trabajo Pagado**. | Regla funcional obligatoria del MVP. |
| Pendiente | Definir catálogo final de oficios y zonas iniciales. | Equipo completo, antes de cerrar Sprint 1. |
| Pendiente | Definir formato exacto de datos bancarios y comprobante. | Integrantes 2 y 3, antes de Sprint 3. |

## Checklist de entrega final

- [ ]  Demo Web ejecutable.
- [ ]  Build Android generado y probado.
- [ ]  HU-01 a HU-06 validadas o con excepción documentada.
- [ ]  No existen incidencias críticas abiertas.
- [ ]  Evidencias de pruebas adjuntas o enlazadas en el tablero.
- [ ]  Decisiones técnicas y limitaciones documentadas.
- [ ]  Backlog futuro separado del alcance del MVP.
- [ ]  Retrospectiva de equipo completada.

Mano Ya — Tablero Scrum