---
title: Problemas conocidos del Acelerador para RosettaNet en BizTalk Server | Documentos de Microsoft
description: "Consulte los problemas conocidos y soluciones con 0A1 notificación de error, BAM, instalación y configuración y más en BTARN en BizTalk Server"
caps.latest.revision: "11"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 335eb3c9-b565-470f-b69c-2a771ef8b476
ms.author: mandia
ms.openlocfilehash: bbb7ddc2028383f8ac346e7876459f322d2dd96b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues"></a>Problemas conocidos
Esta sección contiene información útil que puede ayudar a evitar errores con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. Los problemas conocidos se agrupan en las siguientes áreas:  
  
-   0A1 notificación de error  
  
-   Supervisión de la actividad económica (SAE)  
  
-   Instalación y configuración  
  
-   Varios  
  
## <a name="0a1-notification-of-failure"></a>0A1 notificación de error  
  
### <a name="btarn-does-not-perform-cross-field-validation-for-the-cidx-process-configuration-property-and-the-0a1-agreement-property"></a>BTARN no realiza la validación de campos cruzados para las propiedades de configuración del proceso CIDX y el acuerdo 0A1  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]no podrá establecer la propiedad "Estándar" para un perfil de configuración de proceso para "CIDX", después de haber establecido la propiedad "0A1 acuerdo" para un acuerdo mediante ese perfil a "0A1", incluso aunque un CIDX no admite contratos 0A1.  
  
## <a name="business-activity-monitoring"></a>Supervisión de la actividad económica  
  
### <a name="duplicate-column-data-appears-in-the-business-activity-monitoring-reports"></a>Datos de columna duplicados aparecen en los informes de supervisión de la actividad de negocio  
 Las columnas ActivityID y PIPInstanceID de las actividades de BAM informes Web contienen el mismo contenido. Estos datos reflejan con exactitud el identificador de la instancia de proceso de interfaz de socio (PIP). ActivityID usa este valor para la correlación interno. Puede ignorar este mensaje.  
  
### <a name="empty-data-columns-in-the-business-activity-monitoring-web-reports"></a>Columnas de datos vacíos en los informes Web de supervisión de actividad de negocio  
 Los informes Web de supervisión de la actividad económica (BAM) no contiene ningún dato para procesos de mensajes de 0A1. Las columnas de mensaje 0A1 en los informes de Web están codificados con "Inició 0A1".  
  
## <a name="installation-and-configuration"></a>Instalación y configuración  
  
### <a name="groups-and-users-in-either-the-biztalk-application-users-group-and-the-biztalk-server-administrators-group-must-be-in-the-same-domain"></a>Grupos y usuarios en el grupo de usuarios de la aplicación de BizTalk y el grupo de administradores de BizTalk Server deben estar en el mismo dominio  
 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]admite la adición de un grupo para el grupo de usuarios de la aplicación de BizTalk o un grupo de administradores de BizTalk Server. Sin embargo, las cuentas de usuario individuales y grupos que pertenecen al grupo usuarios de aplicación de BizTalk o el grupo de administradores de BizTalk Server deben ser una parte del mismo dominio.  
  
### <a name="uninstallation-of-btarn-fails-if-biztalk-server-is-removed-first"></a>Se produce un error en la desinstalación de BTARN si BizTalk Server se quita primero  
 Si quita el servidor BizTalk Server antes de quitar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] se produce un error en el proceso de eliminación sin errores. Para resolver este problema, vuelva a instalar y volver a configurar el servidor BizTalk Server y, a continuación, quitar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].  
  
### <a name="distributed-deployment-requires-a-domain-controller"></a>Implementación distribuida requiere un controlador de dominio  
 Implementar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] en un entorno multiservidor requiere un controlador de dominio, por ejemplo, cuando haya instalado [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] en un servidor y el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] utilizados para la configuración en otro servidor de bases de datos.  
  
### <a name="custom-pip-configurations-are-not-supported"></a>No se admiten configuraciones personalizadas de PIP  
 La versión actual de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no permite configurar PIP con los elementos personalizados u otra información estándar de no es de RosettaNet.  
  
### <a name="btarn-automatically-starts-the-single-sign-on-service"></a>BTARN inicia automáticamente el servicio de inicio de sesión único  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]inicia automáticamente el Single Sign-On (SSO) en un evento cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] requiere y el servicio SSO no se está ejecutando.  
  
### <a name="the-configuration-program-will-not-remove-btarn-virtual-directories-from-the-excluded-paths-list-when-webapps-is-not-configured-for-the-default-web-site"></a>El programa de configuración no quitará los directorios virtuales de BTARN desde la lista de rutas excluidas cuando aplicaciones Web no está configurado para el sitio Web predeterminado  
 Si quita la configuración de un [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] instalación en el que se ha configurado la carpeta virtual de aplicación Web para que sea el servidor de SharePoint, no sitio Web predeterminado, después la desconfiguración tendrá que quitar manualmente el btarnapp y btarnhttpreceive virtual directorios de la lista de rutas excluidas en el sitio de Administración Central de SharePoint. Esto sucede porque cuando se configura la carpeta virtual de aplicación Web para que sea el servidor de SharePoint, tiene que agregar manualmente btarnapp y btarnhttpreceive a la lista de rutas excluidas. El programa de configuración no podrá quitar automáticamente de la lista de rutas excluidas.  
  
## <a name="miscellaneous"></a>Varios  
  
### <a name="btarn-will-receive-messages-encrypted-in-either-encryption-algorithm"></a>BTARN recibirá mensajes cifrados en cualquier algoritmo de cifrado  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibir canalización recibe y descifra un mensaje, incluso si el protocolo que se utiliza para cifrar el mensaje y la configuración de codificación en este campo no coinciden. Por lo tanto, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibe los mensajes que están cifrados en RC2-40 o 3DES.  
  
### <a name="btarn-requires-a-signal-in-a-single-action-synchronous-scenario"></a>BTARN requiere una señal en un escenario sincrónico de acción única  
 En un escenario sincrónico de acción única, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] siempre espera y genera señales. Este comportamiento es diferente de la especificación de RosettaNet que una señal puede ser o no puede ser necesario en un escenario sincrónico de acción única. Si [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es un servicio de respuesta, siempre genera una señal en respuesta a un mensaje desde el iniciador. Si [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es un iniciador siempre espera una señal desde el servicio de respuesta. Si [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no recibe una señal, se agota el tiempo después del intervalo especificado en el `Time To Perform` propiedad en los valores de configuración de proceso y genera un mensaje 0A1.  
  
### <a name="btarn-supports-utf-16-in-received-messages"></a>BTARN admite UTF-16 en los mensajes recibidos  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]recibe y procesa los mensajes que tienen un juego de caracteres de UTF-16. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]envía los mensajes con un juego de caracteres de UTF-8.  
  
### <a name="namespaces-must-be-stripped-from-response-messages-mapped-from-request-messages"></a>Espacios de nombres deben eliminarse de los mensajes de respuesta asignados de mensajes de solicitud  
 Si utiliza al asignador de BizTalk en el proceso privado de un escenario de doble acción, el asignador de BizTalk agrega espacios de nombres a algunas etiquetas de elemento de las instancias de mensaje de respuesta asignados de mensajes de solicitud. Estos espacios de nombres provocan un error en la canalización de envío. Debe quitar estos espacios de nombres. Utilice el ejemplo HeaderHelper para hacer esto. Para obtener más información, vea [orquestación de PIPAutomation de doble acción &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md) y [paso 4: crear el proyecto HeaderHelper &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md).  
  
### <a name="changing-uri-settings-requires-iisreset"></a>Cambiar la configuración de URI requiere IISRESET  
 Mientras se ejecuta el programa de instalación, establezca la configuración de URI que usan las páginas .aspx de recepción y envío y la configuración de URI de la recepción y adaptadores de envío. Debe cambiar esta configuración si cambia el nombre del equipo que las páginas .aspx o los adaptadores instalados en. Puede cambiar esta configuración volviendo a ejecutar el proceso de configuración, pero esto requiere restablecer todos los valores de configuración. Puede cambiar la configuración de URI solo cambiando las claves del registro asociadas (`AsyncReceivePortURI`, `RNIFSenderURI`, y `SyncReceivePortURI`). Después de cambiar cualquiera de estos valores del registro, debe ejecutar IISRESET para que los cambios surtan efecto. Esto es porque [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] almacena en caché la configuración para su uso. Después de ejecutar IISRESET, también debe reiniciar los servicios de BizTalk.  
  
### <a name="btarn-does-not-enforce-restrictions-on-rnif-v11-enumerations"></a>BTARN no impone restricciones en las enumeraciones de RNIF v1.1  
 La especificación de RosettaNet Implementation Framework (RNIF) v1.1 especifica restricciones en algunas enumeraciones del esquema RNIF. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]no impone estas restricciones y no se valida con esas restricciones. Las restricciones no se aplican a v2.01 RNIF.  
  
 Esto es cierto para los elementos de encabezado de servicio siguientes:  
  
-   `GlobalBusinessActionCode`  
  
-   `GlobalPartnerClassificationCode`  
  
-   `GlobalBusinessServiceCode`  
  
-   `GlobalProcessCode`  
  
-   `GlobalProcessIndicatorCode`  
  
-   `VersionIdentifier`  
  
### <a name="performancecontrolrequest-parameters-will-not-override-default-process-configuration-settings"></a>PerformanceControlRequest parámetros no invalidará la configuración predeterminada de proceso  
 Los mensajes entrantes pueden contener `PerformanceControlRequest` parámetros en el encabezado de servicio. Estos parámetros incluyen valores para los parámetros de retraso de tiempo de tiempo de confirmación (recepción) y la hora en realizar, como se establece en los valores de configuración de procesos realizados en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]no establecer dinámicamente los retrasos de tiempo en función de la `PerformanceControlRequest` parámetros en el mensaje entrante. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]siempre tiene el retraso de los valores PIP predeterminados establecidos en los valores de configuración de proceso. Esto sigue la especificación de RosettaNet Implementation Framework (RNIF) v1.1.  
  
### <a name="the-pip-name-and-pip-version-of-double-action-messages-are-case-sensitive"></a>El nombre PIP y la versión PIP de doble acción mensajes distinguen mayúsculas de minúsculas  
 Si el nombre PIP y la versión PIP de un mensaje de respuesta tienen mayúsculas o minúsculas de los valores correspondientes de la solicitud de doble acción original del mensaje, el iniciador [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] rechaza el mensaje de respuesta como no válido y devuelve una excepción para el servicio de respuesta.  
  
### <a name="btarn-does-not-support-changing-agreement-settings-while-there-are-active-processes"></a>BTARN no admite cambiar la configuración del acuerdo mientras hay procesos activos  
 Se aplicarán los cambios en las propiedades de acuerdo en cuanto haga clic en **aplicar** o **Aceptar** para aceptarlos. Después de cambiar un acuerdo, cualquier actividad nueva en un proceso ya se está ejecutando o cualquier proceso nuevo que implican dicho acuerdo utilizará las propiedades del acuerdo modificada. Si no hay un proceso que se ejecuta cuando cambia el acuerdo, pueden ya ha utilizado las propiedades del acuerdo anterior para un mensaje. Los mensajes nuevos para ese proceso usará la nueva configuración del acuerdo, lo que puede generar resultados imprevisibles. Se recomienda cambiar la configuración de acuerdo cuando no hay ningún proceso en ejecución.  
  
### <a name="btarn-will-not-perform-cross-field-validation-after-changes-to-a-process-configuration-profile"></a>BTARN no llevará a cabo la validación de campos cruzados después de realizar cambios en un perfil de configuración de proceso  
 Cuando se crea un perfil de configuración de proceso y, a continuación, cree un acuerdo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] realiza la validación de campos cruzados para asegurarse de que las propiedades del acuerdo y el perfil de son compatibles. Por ejemplo, comprueba que un perfil con la propiedad estándar establecida en "CIDX", la propiedad de acuerdo 0A1 del acuerdo se establece en "No 0A1". Sin embargo, si cambia un perfil de configuración de proceso después de haber creado un acuerdo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no realiza la validación de campos cruzados. Si cambia la propiedad estándar de "RosettaNet" a "CIDX" [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no comprueba que la propiedad de acuerdo 0A1 del acuerdo se establece en "No 0A1".  
  
### <a name="errors-will-result-if-all-orchestrations-are-not-started"></a>Se producirán errores si no se inician todas las orquestaciones  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala nueve orquestaciones. Para [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] para procesar los mensajes correctamente, debe enlazar, dar de alta e iniciar todos los nueve de estas orquestaciones antes de iniciar el procesamiento. Para obtener más información, vea los temas "Administración de orquestación en el Explorador de BizTalk" o "Administrar orquestaciones" en la Ayuda de BizTalk Server.  
  
### <a name="rnifreceiveaspx-does-not-remove-the-mime-bottom-boundary-from-a-message"></a>RNIFReceive.aspx no se quita el límite inferior MIME de un mensaje  
 Cuando la página de trabajo RNIFReceive.aspx recibe un mensaje desde una página de RNIFSend.aspx de un asociado, el mensaje incluye un encabezado MIME y una parte superior e inferior límite MIME, un número en base 64. RNIFSend.aspx agrega el encabezado y los límites para el mensaje para la transmisión de RNIF. RNIFReceive.aspx debe quitar el encabezado MIME y los límites de los mensajes antes de enviar el mensaje para el proceso público. RNIFReceive.aspx quita el encabezado MIME y el límite superior, pero no quita el límite inferior. La presencia del límite inferior no afecta el procesamiento del mensaje en el proceso público.  
  
### <a name="btarn-does-not-support-a-case-sensitive-configuration-of-sql-server-databases"></a>BTARN no admite una configuración entre mayúsculas y minúsculas de las bases de datos de SQL Server  
 Si realiza [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] bases de datos y objetos de base de datos distingue mayúsculas de minúsculas, la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración no se puede encontrar recursos de base de datos y se produce una excepción. El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] bases de datos y objetos de base de datos deben distinguir mayúsculas de minúsculas.  
  
### <a name="all-queries-in-database-maintenance-scripts-should-be-written-for-utc-time"></a>Todas las consultas de las secuencias de comandos de mantenimiento de base de datos deben escribirse en hora UTC  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] bases de datos utilizan la hora UTC (hora Universal coordinada), por lo que cualquier consulta que cree para mantener una de estas bases de datos debe escribirse en hora UTC. Por ejemplo, si la secuencia de comandos de mantenimiento usara el `GetDate()` comando, debe cambiarlo a `GetUTCDate()`.  
  
### <a name="a-publicresponder-orchestration-will-reject-a-duplicate-request-action-message"></a>Una orquestación PublicResponder rechazará un mensaje de acción de solicitud de duplicación  
 Cuando un `PublicResponder` (PublicResponderV11.odx) de la orquestación recibe un mensaje de acción de solicitud de duplicación, registrará una advertencia en el registro de eventos y, a continuación, se rechaza el mensaje. Si se recibe un mensaje duplicado una vez completada la orquestación de servicios de respuesta, BizTalk Server se detendrá el mensaje porque no hay ninguna suscripción.  
  
### <a name="transmission-errors-will-not-be-shown-in-bam-if-the-public-process-has-stopped"></a>Errores de transmisión no se mostrará en BAM si se ha detenido el proceso público  
 Si se produce un error de transmisión cuando una orquestación de proceso público procesa el mensaje final, el registro de eventos y HAT muestran el error, pero no BAM. BAM no puede mostrar el mensaje porque se ha detenido la orquestación.  
  
### <a name="the-pipelineexe-tool-cannot-be-used-to-debug-a-btarn-receive-pipeline"></a>No se puede usar la herramienta pipeline.exe para depurar un BTARN la canalización de recepción  
 Si desea depurar una canalización de recepción, tendrá que crear un puerto de hospedaje de la canalización. No puede depurar mediante la herramienta pipeline.exe que proporciona BizTalk Server.  
  
### <a name="an-error-may-be-generated-for-a-retried-message-that-is-successfully-processed-after-the-orchestration-finishes"></a>Puede generarse un error de un mensaje volverá a intentar que se procesa correctamente cuando finaliza la orquestación  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]utiliza orquestaciones para representar el flujo del proceso. En algunos casos, en el que se reintentan varios mensajes volverá a intentar, la orquestación puede finalizar correctamente antes de que llegue un mensaje volverá a intentar en BizTalk MessageBox. Cuando se produce este comportamiento, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] genera un mensaje de error correspondiente "se completó pero descarta". Debe considerar la aplicación de línea de negocio (LOB) para determinar si el proceso ha terminado o no. Si la aplicación de LOB indica la finalización correcta, puede ignorar el mensaje "completado pero descartado".  
  
### <a name="an-xml-file-exported-from-trackingxls-may-have-incorrect-fields"></a>Un archivo XML exportado desde tracking.xls puede tener campos incorrectos  
 Al definir nuevas vistas de seguimiento en un archivo XLS de seguimiento y exportar un archivo XML desde el archivo XLS de seguimiento, algunos de los nombres de campo se va a modificar ligeramente. Para corregir esto, compruebe los campos en el seguimiento personalizado de archivo XML en el campo tracking.xml estándar instala de forma [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] el programa de instalación.  
  
### <a name="rnif-11-service-header-schema-for-signals-and-responses-may-need-modification"></a>Esquema de encabezado de servicio de RNIF 1.1 para señales y respuestas puede requerir la modificación  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]incluye todos los esquemas de encabezado de RosettaNet de fábrica. Algunas implementaciones utilizan los nodos de acción y el Control de señal de manera diferente que otros, tal y como se describe a continuación.  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]de fábrica incluye el elemento de Control de señal como sigue. Tenga en cuenta que el mismo puede ser true para el elemento de Control de la acción.  
  
```  
<!ELEMENT SignalControl (  
          InstanceIdentifier,  
          PartnerRoute,  
          SignalIdentity,  
          inResponseTo)>  
```  
  
 Si la solución requiere esta secuencia, no es necesario hacer nada.  
  
 Otras implementaciones, por otro lado, utilizan el código siguiente:  
  
```  
<!ELEMENT SignalControl (  
          inResponseTo,  
          InstanceIdentifier,  
          PartnerRoute,  
          SignalIdentity)>  
```  
  
 Si la solución requiere esta secuencia, consulte 889523 KB. Esta actualización de software cambiará el esquema XML correspondiente. Tenga en cuenta que esta actualización solo afecta a los procesos de RNIF 1.1.  
  
### <a name="pipautomationgetaction-sql-stored-procedure-needs-update"></a>Procedimiento almacenado de SQL de PipAutomationGetAction necesita la actualización  
 Debe actualizar el código SQL PipAutomationGetAction procedimiento almacenado para bloquear registros individuales. Elimine las líneas siguientes:  
  
```  
IF @@ERROR <> 0  
    UPDATE MessagesToLOB SET Delivered = -1 WHERE MessageID = @tempGUID  
```  
  
 El procedimiento almacenado de PipAutomationGetAction correcto es como sigue:  
  
```  
CREATE PROCEDURE PipAutomationGetAction  
AS  
 SET TRANSACTION ISOLATION LEVEL READ COMMITTED  
BEGIN TRANSACTION  
DECLARE @tempGUID nvarchar(36)  
SELECT TOP 1 @tempGUID = MessageID FROM MessagesToLOB WITH (READPAST,UPDLOCK,ROWLOCK)  
   WHERE Delivered = 0 AND MessageCategory = 10  
  ORDER BY TimeCreated  
  SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion, ServiceContent FROM MessagesToLOB  
   WHERE MessageID = @tempGUID  
For xml auto  
UPDATE MessagesToLOB SET Delivered = 1 WHERE MessageID = @tempGUID  
 COMMIT TRANSACTION  
GO  
```  
  
### <a name="you-can-customize-aspx-code-to-return-the-error-description"></a>Puede personalizar el código de aspx para devolver la descripción del error  
 Si tiene que iniciar sesión o enviar una descripción del error, puede personalizar el código de aspx para que tenga el texto real que se devuelve en la respuesta. Para ello, utilice HttpResponse.Status (que es el objeto de respuesta de la solicitud asp intrínsecos) o HttpWebResponse.StatusDescription (que es devuelto por la [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] llamada al método del objeto HttpWebRequest). Para devolver los valores devueltos de uno de los objetos de respuesta es aplicable, establezca el valor de Response.Status similar a cómo Response.StatusCode se establece en el código aspx que se suministra con [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].  
  
### <a name="rnif-11-messages-cannot-be-read-in-plain-text-from-non-repudiation-tables-if-the-encoding-method-is-set-to-base64"></a>Mensajes de RNIF 1.1 no se puede leer en texto sin formato de tablas sin repudio, si se establece el método de codificación en Base64  
 Esto sólo ocurre si se establece el método de codificación en Base64. Si el método de codificación se establece en Entrecomillado imprimible o de 8 bits, los mensajes pueden leerse en texto no cifrado de tablas sin repudio. Debe guardar el archivo de mensaje con la extensión *.eml y, a continuación, abrirlo con Outlook Express para leer el mensaje y Outlook Express descodifica el mensaje para usted. También puede usar el código siguiente para leer los mensajes con codificación Base64 de tablas sin repudio.  
  
```  
byte[] textBytes = Convert.FromBase64String(txtEncodedText.Text);  
string plainText = Encoding.UTF8.GetString(textBytes);  
txtOutput.Text = plainText;  
```  
  
## <a name="see-also"></a>Vea también  
[Solución de problemas y problemas conocidos](troubleshooting-and-known-issues-in-rosettanet.md)