📄 Informe Técnico del Taller parte 2
🔖 taller BPMN

Taller 1 parte 2 – Modelado de Proceso del Cliente con BPMN

🧠 Descripción general del trabajo

El objetivo de este taller fue modelar un proceso de negocio real utilizando la notación BPMN (Business Process Model and Notation), identificando los eventos, actividades, decisiones, actores involucrados y puntos críticos del flujo.

Inicialmente se trabajó con el caso base de la Clínica Salud Viva para comprender la estructura de modelado BPMN. Posteriormente, el equipo aplicó los conocimientos adquiridos al cliente real asignado, BRY Andina, seleccionando un proceso representativo de su operación comercial.

El proceso elegido fue Gestión de Cotización y Pedido de Cliente Industrial, debido a que constituye una actividad central del negocio B2B de la empresa, integrando áreas comerciales, operativas y financieras, así como la interacción con el ERP corporativo.

🔧 Proceso de desarrollo

Para el desarrollo del modelo BPMN se siguieron las siguientes etapas:

Comprensión del negocio del cliente:
Se analizó la información disponible sobre BRY Andina, su modelo operativo, estructura organizacional y relación con el corporativo.

Selección del proceso:
Se eligió el proceso de cotización y pedido porque involucra múltiples áreas y refleja la operación principal de la empresa.

Identificación de actores:
Se identificaron los participantes clave:

Cliente industrial

Ventas internas

Operaciones / logística

Finanzas

ERP corporativo

Construcción del flujo inicial:
Se definieron los eventos de inicio y fin, actividades principales y puntos de decisión (por ejemplo, disponibilidad de inventario).

Refinamiento del modelo:
Se agregaron compuertas BPMN, flujos alternos y validaciones hasta obtener un modelo coherente con la operación real.

La herramienta utilizada para el modelado fue Draw.io (diagrams.net), debido a su facilidad de uso y compatibilidad con BPMN.

🧩 Análisis del modelo propuesto

El modelo BPMN se estructura en varios carriles (swimlanes) que representan las áreas organizacionales involucradas: Cliente, Ventas, Operaciones y Finanzas. Esto permite visualizar claramente las responsabilidades y transferencias de información entre departamentos.

El flujo inicia con la solicitud de cotización del cliente y continúa con la validación de inventario en el ERP. Si el producto está disponible, se genera la cotización y posteriormente el pedido. En caso contrario, se crea una orden de compra al corporativo, lo que introduce un flujo alternativo. Finalmente, se realiza el despacho y la facturación electrónica al cliente.

El modelo representa adecuadamente las necesidades del cliente porque refleja:

La dependencia del inventario local

La interacción con el corporativo internacional

El uso del ERP como sistema central

La facturación conforme a normativa colombiana

Los principales supuestos tomados fueron:

El ERP LN gestiona inventario, pedidos y facturación.

La comunicación con el corporativo ocurre mediante órdenes de compra formales.

El cliente confirma el pedido después de recibir la cotización.


Ejemplo de flujo modelado:

Inicio → Solicitud de cotización → Validar inventario →
¿Hay inventario?
• Sí → Generar cotización → Confirmación cliente → Pedido → Despacho → Facturación → Fin
• No → Orden de compra al corporativo → Recepción → Cotización → Flujo normal → Fin

📋 Tabla de actores, entidades o componentes
Nombre del elemento	Tipo	Descripción	Responsable
Cliente Industrial	Actor	Empresa que solicita cotización y compra productos	Cliente
Ventas Internas	Actor	Área encargada de gestionar cotizaciones y pedidos	BRY Andina
Operaciones	Actor	Área responsable de inventario, compras e importaciones	BRY Andina
Finanzas	Actor	Área encargada de facturación y cobro	BRY Andina
ERP LN	Sistema	Sistema corporativo de gestión empresarial	Corporativo
Inventario	Entidad	Productos disponibles en bodega local	Operaciones
Orden de Compra	Documento	Solicitud de compra al corporativo	Operaciones
🔍 Investigación complementaria
Tema investigado: Buenas prácticas BPMN

Las buenas prácticas BPMN recomiendan mantener modelos simples, con eventos de inicio y fin claramente definidos, evitando cruces innecesarios de flujos y utilizando compuertas para representar decisiones de negocio. También se sugiere el uso de swimlanes para diferenciar responsabilidades organizacionales, facilitando la comprensión del proceso por parte de stakeholders técnicos y no técnicos.

Otra recomendación importante es modelar únicamente el nivel de detalle necesario para el objetivo del análisis. Un exceso de complejidad puede dificultar la interpretación del proceso. Asimismo, BPMN permite representar tanto procesos manuales como automatizados, lo cual resulta útil en organizaciones que integran sistemas ERP con actividades humanas, como es el caso de BRY Andina.

Estas buenas prácticas se relacionan con el taller porque permitieron estructurar el modelo de manera clara, diferenciando actores y decisiones clave como la disponibilidad de inventario y la interacción con el corporativo.

📚 Referencias

[1] Object Management Group (OMG). Business Process Model and Notation (BPMN) Version 2.0.
https://www.omg.org/spec/BPMN/

[2] Silver, Bruce. BPMN Method and Style. Cody-Cassidy Press, 2011.

[3] Dumas, Marlon; La Rosa, Marcello; Mendling, Jan; Reijers, Hajo. Fundamentals of Business Process Management. Springer, 2018.
