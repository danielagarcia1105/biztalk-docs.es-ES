# [Documentación del adaptador de Microsoft BizTalk para SQL Server](microsoft-biztalk-adapter-for-sql-server-documentation.md)
## [Introducción](get-started-with-the-biztalk-adapter-for-sql.md)
### [Instalar el adaptador de SQL](install-the-sql-adapter.md)
#### [Instalar el adaptador de SQL: 2016](install-microsoft-biztalk-adapter-for-sql-server-2016.md)
#### [Instalar el adaptador de SQL: 2013 R2 y 2013](install-microsoft-biztalk-adapter-for-sql-server-2013-r2-and-2013.md)
### [Descripción del adaptador de BizTalk para SQL Server](understand-biztalk-adapter-for-sql-server.md)
#### [Información general sobre el adaptador de BizTalk para SQL Server](overview-of-biztalk-adapter-for-sql-server.md)
##### [Conectarse a SQL Server mediante el adaptador](connect-to-sql-server-using-the-adapter.md)
##### [Explorar, buscar y obtener metadatos de SQL Server](browse-search-and-get-sql-server-metadata.md)
##### [Ver las operaciones admitidas](what-operations-are-supported-by-the-sql-adapter.md)
###### [Operaciones de inserción, actualización y eliminación en tablas y vistas](insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)
###### [Operaciones en tablas y vistas con tipos de datos de gran tamaño](supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)
###### [Operaciones en tablas y vistas con tipos definidos por el usuario](operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)
###### [Ejecutar procedimientos almacenados](execute-stored-procedures-in-sql-server-using-the-sql-adapter.md)
###### [Ejecutar funciones escalares](execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)
###### [Ejecutar funciones con valores de tabla](execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md)
###### [Operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar](executenonquery-executereader-and-executescalar-using-the-sql-adapter.md)
###### [Ejecutar operaciones compuestas](run-composite-operations-in-sql-server-using-the-sql-adapter.md)
###### [Sondeo de SQL](polling-in-sql-server-using-the-sql-adapter.md)
###### [Recibir notificaciones de consulta](receive-query-notifications-using-the-sql-adapter.md)
##### [Características para los clientes del adaptador](features-for-sql-adapter-clients.md)
#### [Características clave del adaptador](key-features-in-biztalk-adapter-for-sql-server.md)
#### [Limitaciones del adaptador](limitations-of-biztalk-adapter-for-sql-server.md)
### [Tutoriales del adaptador de SQL](sql-adapter-tutorials.md)
#### [Tutorial 1: Migrar proyectos de BizTalk](tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)
##### [Paso 1: Modificar el proyecto vPrev de BizTalk](step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)
##### [Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server](step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)
##### [Paso 3: Probar la aplicación migrada](step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)
#### [Tutorial 2: Empleado: proceso de pedido de compra](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)
##### [Lección 1: Generar esquemas y crear mensajes](lesson-1-generate-schemas-and-create-messages.md)
###### [Paso 1: Generar el esquema para las operaciones](step-1-generate-schema-for-operations.md)
###### [Paso 2: Crear mensajes para orquestaciones de BizTalk](step-2-create-messages-for-biztalk-orchestrations.md)
##### [Lección 2: Recibir y filtrar notificaciones](lesson-2-receive-and-filter-notifications.md)
###### [Paso 1: Agregar formas de orquestación para recibir una notificación](step-1-add-orchestration-shapes-to-receive-notification.md)
###### [Paso 2: Extraer el tipo de notificación del mensaje de notificación](step-2-extract-notification-type-from-notification-message.md)
###### [Paso 3: Agregar un filtro para las notificaciones de inserción](step-3-add-a-filter-for-insert-notifications.md)
##### [Lección 3: Ejecutar un procedimiento almacenado para seleccionar nuevos empleados agregados](lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)
###### [Paso 1: Crear el mensaje de solicitud para el procedimiento almacenado UPDATE_EMPLOYEE](step-1-create-the-request-message-for-update-employee-stored-procedure.md)
###### [Paso 2: Enviar el mensaje de solicitud a SQL Server y recibir la respuesta](step-2-send-the-request-message-to-sql-server-and-receive-response.md)
##### [Lección 4: Realizar una operación de inserción en la tabla de pedidos de compra](lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)
###### [Paso 1: Crear el mensaje de solicitud para la operación de inserción en la tabla Purchase_Order](step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)
###### [Paso 2: Asignar el mensaje de respuesta UPDATE_EMPLOYEE al mensaje de solicitud de operación de inserción](step-2-map-update_employee-response-to-insert-operation-request.md)
###### [Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta](step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)
###### [Paso 4: Generar el proyecto](step-4-build-the-project.md)
##### [Lección 5: Implementar la solución](lesson-5-deploy-the-solution.md)
###### [Paso 1: Implementar la orquestación](step-1-deploy-the-orchestration.md)
###### [Paso 2: Configurar los puertos](step-2-configure-the-ports.md)
###### [Paso 3: Configurar e iniciar la aplicación](step-3-configure-and-start-the-application.md)
###### [Paso 4: Probar la aplicación](step-4-test-the-application.md)
### [Preguntas más frecuentes sobre el adaptador de SQL](sql-adapter-faqs.md)
## [Introducción a la arquitectura del adaptador SQL](architecture-overview-of-biztalk-adapter-for-sql-server.md)
## [Proteger las aplicaciones SQL](secure-your-sql-applications.md)
### [Seguridad entre el servidor SQL Server y el adaptador](security-between-the-sql-server-and-the-adapter.md)
### [Seguridad con el adaptador de SQL y BizTalk Server](security-with-the-sql-adapter-and-biztalk-server.md)
### [Programación segura con el adaptador de SQL](secure-programming-with-the-sql-adapter.md)
### [Procedimientos recomendados de seguridad](best-practices-to-secure-the-sql-adapter.md)
## [Desarrollar las aplicaciones SQL](develop-your-sql-applications.md)
### [Crear una conexión a SQL Server](create-a-connection-to-sql-server.md)
#### [Crear el URI de conexión](create-the-sql-server-connection-uri.md)
#### [Conectarse mediante la autenticación de Windows](connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)
### [Obtener metadatos para operaciones de SQL Server en Visual Studio](get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)
#### [Conectarse a SQL Server en Visual Studio](connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)
##### [Conectarse mediante el complemento Consume Adapter Service](connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)
##### [Conectarse mediante el asistente Agregar metadatos de adaptador](connect-to-sql-server-in-visual-studio-using-add-adapter-metadata-wizard.md)
##### [Conectarse mediante el complemento Add Adapter Service Reference](connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference.md)
#### [Examinar, buscar y obtener metadatos para operaciones de SQL](browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)
### [Identificadores de nodo de metadatos](metadata-node-ids2.md)
### [Trabajar con las propiedades de enlace](read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)
### [Requisito previo: configurar MSDTC](configure-msdtc-on-sql-server-and-adapter-client.md)
### [Desarrollar aplicaciones de BizTalk con el adaptador de SQL](develop-biztalk-applications-using-the-sql-adapter.md)
#### [Crear el archivo de clave de nombre seguro y obtener información sobre las herramientas](prerequisites-to-create-sql-applications-using-the-sql-adapter.md)
#### [Bloques de creación para crear aplicaciones de BizTalk](building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)
##### [Agregar el adaptador a la administración de BizTalk Server](adding-the-sql-adapter-to-biztalk-server-administration-console.md)
##### [Escribir el URI de conexión](configure-the-connection-uri-for-the-sql-adapter.md)
##### [Escribir las credenciales de inicio de sesión](configure-the-sign-in-credentials-for-the-sql-adapter.md)
##### [Escribir las propiedades de enlace](configure-the-binding-properties-for-the-sql-adapter.md)
##### [Escribir la acción SOAP](configure-the-soap-action-for-the-sql-adapter.md)
##### [Crear manualmente un enlace de puerto físico al adaptador](manually-configure-a-physical-port-binding-to-the-sql-adapter.md)
###### [Configurar un puerto mediante el adaptador personalizado de WCF](configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)
###### [Configurar un puerto mediante el adaptador WCF de SQL](configure-a-port-using-the-wcf-sql-adapter.md)
##### [Configurar un enlace de puerto físico mediante un archivo de enlace de puerto](configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)
##### [Configurar puertos dinámicos](configure-dynamic-ports-in-the-sql-adapter.md)
##### [Reutilizar los enlaces del adaptador](reuse-sql-adapter-bindings.md)
#### [Operaciones de inserción, actualización, eliminación o selección](insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)
#### [Ejecutar operaciones en tablas y vistas con tipos de datos de gran tamaño](run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)
#### [Ejecutar procedimientos almacenados](execute-stored-procedures-in-sql-server-using-biztalk-server.md)
#### [Ejecutar procedimientos almacenados con un solo parámetro XML](execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)
#### [Ejecutar procedimientos almacenados con una cláusula FOR de XML](execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)
#### [Ejecutar operaciones compuestas](run-composite-operations-on-sql-server-using-biztalk-server.md)
#### [Invocar funciones escalares](invoke-scalar-functions-in-sql-server-using-biztalk-server.md)
#### [Invocar funciones con valores de tabla](invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)
#### [Operaciones ExecuteReader, ExecuteScalar o ExecuteNonQuery](executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)
#### [Sondear el servidor SQL Server mediante BizTalk Server](poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)
##### [Recibir mensajes de cambio de datos basados en sondeos](receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)
##### [Recibir mensajes de cambio de datos fuertemente tipados basados en sondeos](receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)
##### [Recibir mensajes de sondeo mediante las instrucciones SELECT con la cláusula FOR de XML](receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)
##### [Recibir mensajes de sondeo a través de varios puertos de recepción](receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)
#### [Recibir notificaciones de consulta](receive-sql-query-notifications-using-biztalk-server.md)
##### [Antes de empezar](considerations-for-receiving-query-notifications-using-the-sql-adapter.md)
##### [Procesar mensajes de notificación](process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)
##### [Recibir notificaciones de consulta de forma incremental](receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)
##### [Recibir notificaciones de consulta en varias ubicaciones de recepción](receive-query-notifications-on-receive-locations-from-sql-server-using-biztalk.md)
##### [Recibir notificaciones de consulta después de un desglose de las ubicaciones de recepción](receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)
### [Desarrollar aplicaciones con el modelo de servicio WCF](develop-sql-applications-using-the-wcf-service-model.md)
#### [Información general sobre el modelo de servicio WCF con el adaptador](overview-of-the-wcf-service-model-with-the-sql-adapter.md)
#### [Los metadatos y el modelo de servicio WCF](metadata-and-the-wcf-service-model-with-the-sql-adapter.md)
#### [Generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)
#### [Configurar un enlace de cliente](configure-a-client-binding-for-the-sql-adapter.md)
#### [Operaciones de inserción, actualización, eliminación o selección](insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model.md)
#### [Ejecutar operaciones en tablas y vistas con tipos de datos de gran tamaño](read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)
#### [Invocar procedimientos almacenados](invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)
##### [Invocar procedimientos almacenados con establecimiento flexible de tipos](invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)
##### [Invocar procedimientos almacenados fuertemente tipados](invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)
#### [Invocar funciones escalares](invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)
#### [Invocar funciones con valores de tabla](invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)
#### [Operaciones ExecuteReader, ExecuteScalar o ExecuteNonQuery](executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)
#### [Sondear el servidor SQL Server](poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)
##### [Recibir mensajes de cambio de datos basados en sondeos](receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-service.md)
##### [Recibir mensajes de cambio de datos fuertemente tipados basados en sondeos](receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)
#### [Recibir notificaciones de consulta](receive-query-notifications-from-sql-using-the-wcf-service-model.md)
### [Desarrollar aplicaciones con el modelo de canal WCF](develop-sql-applications-using-the-wcf-channel-model.md)
#### [Información general sobre el modelo de canal WCF con el adaptador](overview-of-the-wcf-channel-model-with-the-sql-adapter.md)
#### [Crear un canal](create-a-channel-using-the-sql-adapter.md)
#### [Ejecutar una operación de inserción en una tabla](run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)
#### [Recibir mensajes de cambio de datos basados en sondeos](receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)
### [Ejemplos](samples-for-the-sql-adapter.md)
### [Configurar el nivel de aislamiento de transacción y el tiempo de espera de la transacción](configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)
## [Mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)
### [Tipos de datos básicos de SQL Server](basic-sql-server-data-types.md)
### [Esquemas de mensaje para operaciones de inserción, actualización, eliminación y selección en tablas y vistas](message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)
### [Esquemas de mensaje para procedimientos y funciones](message-schemas-for-procedures-and-functions.md)
### [Esquemas de mensaje para las operaciones de Polling y TypedPolling](message-schemas-for-the-polling-and-typedpolling-operations.md)
### [Esquemas de mensaje de notificación de consulta](message-schemas-for-query-notification.md)
### [Esquemas de mensaje para operaciones compuestas](message-schemas-for-composite-operations.md)
### [Esquemas de mensaje para las operaciones ExecuteNonQuery, ExecuteReader y ExecuteScalar](executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)
## [Solucionar problemas](troubleshoot-the-sql-adapter.md)
### [Seguimiento de diagnósticos y registro de mensajes](diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)
### [Solucionar problemas de instalación](troubleshoot-installation-issues-with-the-sql-adapter.md)
### [Solucionar problemas de funcionamiento](troubleshoot-operational-issues-with-the-sql-adapter.md)
### [Usar contadores de rendimiento](use-performance-counters-with-the-sql-adapter.md)
## [Términos y definiciones](glossary4.md)