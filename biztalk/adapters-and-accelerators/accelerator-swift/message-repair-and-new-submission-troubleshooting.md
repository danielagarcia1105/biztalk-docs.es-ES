---
title: "Reparación y la nueva solución de problemas de envío de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, Message Repair and New Submission
- Message Repair and New Submission, troubleshooting
ms.assetid: bb07a286-6f02-4639-b5fa-a3647e356ac8
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d341a7f03c70e1ddcd242d7804b162338798e94
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="message-repair-and-new-submission-troubleshooting"></a>Reparación de mensajes y solución de problemas de envío nuevo
## <a name="a-repaired-message-cannot-be-submitted-if-the-envelope-schema-is-not-deployed"></a>No se puede enviar un mensaje reparado si no se ha implementado el esquema de sobres  
  
### <a name="symptom"></a>Síntoma  
 Al intentar enviar un mensaje que se reparó, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] envía el mensaje siguiente:  
  
 "El adaptador no pudo transmitir el mensaje destinado para el puerto de envío" http://mrsrtest:80/StsWebReceive/default.aspx?PartnerId=Unparsed & FolderType = MessagesInbox ". Se retransmitirá después del intervalo de reintentos especificado para este puerto de envío. Details:"80131600". Para obtener más información, consulte Ayuda y soporte técnico en [http://go.microsoft.com/fwlink/?LinkId=142493](http://go.microsoft.com/fwlink/?LinkId=142493).  
  
### <a name="possible-cause"></a>Causa posible  
 No se ha implementado el esquema de sobre. Esto es cierto para cualquier MT*xxx* mensaje o cualquier mensaje que no se pudo analizar.  
  
### <a name="solution"></a>Solución  
 Implementar un esquema de sobre para cada esquema de mensaje que está usando (\<unidad\>: \Program Acelerador de BizTalk para SWIFT \<versión\> paquete de mensajes \SWIFT Messages\ A4SWIFT-SRG\<versión\>\Category n\MTxxx.xsd) y para esquema de sobre sin analizar (\<unidad\>: \Program Acelerador de BizTalk para SWIFT \<versión\> paquete de mensajes \ SWIFT de mensajes de detención\ A4SWIFT SRG\<versión\>\ Message\EnvelopeUnparsedMessage.xsd sin analizar). Para obtener más información, consulte [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-other-than-unparsed"></a>No puede enviar un mensaje sin analizar fijo desde una biblioteca de sitio MRSR denominada distinto de "Unparsed"  
  
### <a name="symptom"></a>Síntoma  
 Al intentar enviar un mensaje sin analizar que haya corregido desde una biblioteca de documentos del sitio MRSR que no se denomina "Unparsed", se produce un error en la operación.  
  
### <a name="possible-cause"></a>Causa posible  
 A4SWIFT correctamente no se puede enviar un mensaje desde una biblioteca que no se denomina "Unparsed". Si tiene una biblioteca de documentos de "Unparsed" existente en el sitio MRSR antes de instalar la característica MRSR (reparación de mensajes), el programa de instalación de A4SWIFT creará una biblioteca para los mensajes sin analizar titulada "Unparsed" con un sufijo. Cuando recibe un mensaje que no se pudo analizar A4SWIFT, enrutará el mensaje para esa biblioteca que creó. Sin embargo, al intentar enviar un mensaje de dicha biblioteca, la operación se producirá un error.  
  
### <a name="solution"></a>Solución  
 Quitar la característica MRSR, eliminar la biblioteca sin analizar y, a continuación, vuelva a instalar la característica MRSR.  
  
## <a name="cannot-loop-back-a-message-in-a-two-stage-workflow"></a>No se puede crear un bucle vuelve un mensaje en un flujo de trabajo de dos fases  
  
### <a name="symptom"></a>Síntoma  
 Si se rechaza un mensaje en la fase de reparación de un flujo de trabajo que tiene solo una fase de creación y una fase de reparación, se produce un error en el envío. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]enruta el mensaje hacia el cuadro de mensajes y envía el mensaje de error siguiente:  
  
 "No se pudo restablecer a la primera fase del flujo de trabajo."  
  
### <a name="possible-cause"></a>Causa posible  
 Bucle invertido de mensaje no se admite para un flujo de trabajo que tiene solo una fase de creación y una etapa de reparación.  
  
### <a name="solution"></a>Solución  
 Agregue otra etapa para el flujo de trabajo de dos fases o cancelar el envío.  
  
## <a name="cannot-open-a-message-in-the-repair-inbox-in-mrsr"></a>No se puede abrir un mensaje en la Bandeja de entrada de reparación en MRSR  
  
### <a name="symptom"></a>Síntoma  
 Cuando intenta abrir un mensaje en la Bandeja de entrada de reparación en MRSR, recibirá el mensaje de error siguiente en una ventana emergente:  
  
 "No se puede abrir la base de datos solicitada en el inicio de sesión 'A4SWIFT'. Se produce un error de inicio de sesión. Error de inicio de sesión para el usuario 'NT AUTHORITY\NETWORK SERVICE'.  
  
### <a name="possible-cause"></a>Causa posible  
 La cuenta de inicio de sesión para la aplicación web que se ejecuta el servicio web A4SWIFT_MRSR es servicio de red, no una variable local o cuenta de dominio que está en el grupo de usuarios de A4SWIFT.  
  
### <a name="solution"></a>Solución  
 Cambiar la cuenta de inicio de sesión para la aplicación web que se ejecuta el servicio web de A4SWIFT_MRSR.  
  
##### <a name="to-change-the-login-account-for-the-web-application-that-the-a4swiftmrsr-web-service-runs-under"></a>Para cambiar la cuenta de inicio de sesión para la aplicación web que se ejecuta el servicio web de A4SWIFT_MRSR  
  
1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  
  
2.  En el Administrador de IIS, expanda el  ***\<nombre del servidor\>*  (equipo local)** nodo, el **grupos de aplicaciones** nodo y el **Web Sitios** nodo. En el nodo sitios Web, expanda el **sitio Web predeterminado** nodo.  
  
3.  En el nodo sitio Web predeterminado, haga clic en **A4SWIFT_MRSR**y, a continuación, haga clic en **propiedades**.  
  
4.  En el cuadro de diálogo Propiedades de A4SWIFT_MRSR, tenga en cuenta el grupo de aplicaciones.  
  
5.  En el cuadro de diálogo Administrador de IIS, en el nodo grupos de aplicaciones, haga clic en el grupo de aplicaciones para A4SWIFT_MRSR y, a continuación, haga clic en **propiedades**.  
  
6.  En el \<nombre del grupo de aplicaciones\> cuadro de diálogo de propiedades, haga clic en el **identidad** nota. Si **predefinida** se hace clic en y **servicio de red** está seleccionado, haga clic en **Configurable**, escriba la cuenta local o de dominio y, a continuación, escriba la contraseña. Haga clic en **Aceptar**.  
  
## <a name="a-message-created-in-mrsr-site-on-a-localized-computer-is-not-processed"></a>No se procesa un mensaje creado en el sitio MRSR en un equipo localizado  
  
### <a name="symptom"></a>Síntoma  
 Cuando un usuario que trabaje en una versión en inglés de A4SWIFT que se ejecuta en una plataforma localizada crea un mensaje en un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formato en MRSR y envía el mensaje correctamente, aparece el mensaje a ser consumidos por la reparación de mensajes y nuevo envío orquestación, pero no se procesa correctamente. El mensaje se envía a la Bandeja de salida, pero no recoge el adaptador de BizTalk. Ningún error o advertencia se registra en el evento Visor, y no hay ningún registro de una instancia de orquestación ejecución en HAT.  
  
### <a name="possible-cause"></a>Causa posible  
 La ruta de acceso especificada como el URI para el STS. Bandeja de salida de recepción ubicación contiene el nombre inglés, no el nombre localizado.  
  
### <a name="solution"></a>Solución  
 Cambiar la dirección URI de STS. Bandeja de salida de ubicación de recepción como sigue:  
  
1.  En la consola de administración de BizTalk Server 2009, expanda la **grupo de BizTalk**, **aplicaciones**, y **BizTalk Application 1 nodos**.  
  
2.  Haga clic en **ubicaciones de recepción**.  
  
3.  Haga doble clic en **Sts.Outbox.Location**.  
  
4.  En el cuadro de diálogo Propiedades de la ubicación de recepción, haga clic en **configurar**.  
  
5.  En el cuadro de diálogo Propiedades de transporte, reemplace el valor de **SharePointSite URL** con su equivalente localizado.  
  
6.  Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="removing-a-role-while-it-is-processing-a-message-results-in-incomplete-removal-of-documents-and-artifacts"></a>Quitar un rol mientras se está procesando un mensaje da como resultado una eliminación incompleta de documentos y artefactos  
  
### <a name="symptom"></a>Síntoma  
 Cuando se quita un rol en el cliente Web de perfil, se registra un cuadro de diálogo que indica que se quitarán todos los documentos y artefactos asociados a la función. Sin embargo, no se eliminará el rol del departamento en la consola de administración de A4SWIFT y las carpetas de documentos del rol (Bandeja de entrada y elementos enviados) no se quitan de MRSR. La entidad, el puerto de envío y el acuerdo asociado con el rol se quitan y el perfil de la función no está implementado.  
  
### <a name="possible-cause"></a>Causa posible  
 Un mensaje está aún en la Bandeja de entrada del rol en MRSR y el mensaje está abierto en su [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario.  
  
### <a name="solution"></a>Solución  
 Elimine manualmente el mensaje de la Bandeja de entrada del sitio MRSR y, a continuación, elimine la biblioteca de documentos que está asociada con el rol que desea quitar. Cierre el formulario y quitar el rol de nuevo.  
  
## <a name="message-processing-fails-as-a-result-of-an-error-in-the-bic-master-policy"></a>Se produce un error de procesamiento de mensajes como resultado un error en la directiva de BIC Master  
  
### <a name="symptom"></a>Síntoma  
 Cuando se envía un mensaje para su procesamiento, recibirá el error siguiente:  
  
 "Se produjo un error al ejecutar el BicMasterPolicy. Comprobación de la directiva para los valores válidos."  
  
### <a name="possible-cause"></a>Causa posible  
 El nombre de SQL Server, el nombre de la base de datos BIC y el valor de la seguridad integrada en el archivo BIC_Master_Policy.xml  *\<unidad\>*: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión \> Mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base directivas incluidas entre comillas dobles. Para habilitar la validación BIC, escriba estas cadenas en el archivo de BIC_Master_Policy.xml predeterminado tal y como se describe en [habilitar la validación de Bank identificador códigos](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).  
  
### <a name="solution"></a>Solución  
 Para reparar la directiva principal BIC, haga lo siguiente:  
  
> [!NOTE]
>  Para obtener más información acerca de cómo implementar la directiva principal BIC, consulte [implementar reglas de BRE](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md).  
  
1.  En el Compositor de reglas de negocios, anular la implementación de la versión 1.0 de la BIC_Master_Policy y, a continuación, elimine la BIC_Master_Policy.  
  
2.  En un editor de texto, como el Bloc de notas, abra BIC_Master_Policy.xml en  *\<unidad\>*: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> Pack\SWIFT de mensaje SRG Messages\A4SWIFT\<versión\>\Base directivas. Quitar las comillas dobles alrededor del nombre de SQL Server, BIC nombre de la base de datos e integración de valor de seguridad.  
  
3.  En el Asistente de implementación motor de reglas empresariales, importar BIC_Master_Policy.xml y, a continuación, implemente BIC_Master_Policy.xml.  
  
4.  En el MMC de servicios, reinicie el servicio de actualización de motor de reglas y el servicio de Host de recepción de BizTalk.  
  
## <a name="a4swift-will-not-be-able-to-process-an-unparsed-message-without-proper-database-permissions"></a>A4SWIFT no podrá procesar un mensaje sin analizar sin permisos de base de datos correcta  
  
### <a name="symptom"></a>Síntoma  
 Cuando se quita un mensaje que no se puede analizar A4SWIFT, A4SWIFT no puede procesar el mensaje, pero se produce un error con una excepción no detectada.  
  
### <a name="possible-cause"></a>Causa posible  
 Hay un problema de permiso de base de datos. La cuenta de inicio de sesión para el servicio de BizTalk, cuyo valor predeterminado es HostSvc, no se incluye en los grupos Administradores de A4SWIFT y los usuarios de A4SWIFT.  
  
### <a name="solution"></a>Solución  
 Agregue la cuenta de inicio de sesión para el servicio de BizTalk a los grupos de usuarios de A4SWIFT y los administradores de A4SWIFT.  
  
## <a name="a-timeout-of-the-infopath-repair-form-can-result-in-two-copies-of-a-message-in-different-stages-of-the-repair-workflow"></a>Puede producir un tiempo de espera de la forma de reparación de InfoPath dos copias de un mensaje en distintas fases del flujo de trabajo de reparación  
  
### <a name="symptom"></a>Síntoma  
 Cuando se envía un mensaje desde un formulario de InfoPath (para cualquier fase de flujo de trabajo), si se produce un error en el envío del formulario, podría provocar el error dos copias del mensaje. Un mensaje aún está en la Bandeja de entrada para las fases actuales y el otro mensaje está en la Bandeja de entrada para la función siguiente en el flujo de trabajo. Intenta procesar estos mensajes se producirá en lo siguiente:  
  
-   Si se envía el mensaje de la Bandeja de entrada para la función siguiente del flujo de trabajo, el mensaje seguirá a través del flujo de trabajo.  
  
-   Si se envía el mensaje de la Bandeja de entrada para la fase actual después de que el mensaje enviado desde la Bandeja de entrada de la siguiente fase tiene finalizado el procesamiento, se suspenderá el mensaje enviado desde la Bandeja de entrada actual con un error de enrutamiento.  
  
-   Si envía el mensaje en la Bandeja de entrada durante la fase actual antes de que se ha completado el mensaje enviado desde la Bandeja de entrada de la siguiente fase de procesamiento, se devolverá el mensaje enviado desde la Bandeja de entrada para la fase actual a la Bandeja de entrada para esa fase, y que se van a recibe el error siguiente:  
    "Restablecer el flujo de trabajo debido a: el mensaje ha sido alterado o el usuario no es válido para esta fase."  
    Después de esto, si se envía el mensaje de la Bandeja de entrada para la fase siguiente, también se restablecerán el flujo de trabajo para él. Se devolverá a la Bandeja de entrada para la fase actual y recibirá el error anterior.  
  
### <a name="possible-cause"></a>Causa posible  
 El formulario de InfoPath ha enviado el mensaje a BizTalk Server a través de Microsoft Windows Sharepoint Services y un servicio Web personalizado que realiza validaciones. Enviar un mensaje se realiza en varios pasos y estos pasos no son transaccionales, ya que Windows Sharepoint Services no es transaccional. Para dar cabida a esta limitación, las orquestaciones de MRSR han creado en la lógica de recuperación para detectar y recuperarse de los errores que surgen de enviar el mensaje. Las orquestaciones de MRSR siempre evitar duplicados mensajes se envíen para SWIFT.  
  
### <a name="solution"></a>Solución  
 Si esto ocurre, debe elegir el mensaje que se encuentra más allá del flujo de trabajo y completar el flujo de trabajo antes de intentar procesar los otros mensajes que se encuentran en las fases anteriores del flujo de trabajo. Después de que el mensaje que se encuentra más allá del flujo de trabajo ha completado el procesamiento, puede eliminar el segundo mensaje (que se suspendió con un error de enrutamiento) como considere oportuno.  
  
 Si el mensaje que está más a lo largo del flujo de trabajo no completó antes de que se procese el segundo mensaje de procesamiento, debe reparar el mensaje que se encuentra más allá del flujo de trabajo en el formulario de InfoPath de reparación de una vez más y, a continuación, enviarla. Permitir que se complete el procesamiento y, a continuación, enviar el segundo mensaje. Después de que el segundo mensaje se ha suspendido, elimínelo.  
  
## <a name="a-new-submission-with-no-verify-stage-will-result-in-a-suspended-message"></a>Un nuevo envío con ninguna fase Compruebe dará como resultado un mensaje suspendido  
  
### <a name="symptom"></a>Síntoma  
 Cuando se envía un mensaje nuevo en un flujo de trabajo que no tiene ninguna fase de comprobación, se suspende el mensaje.  
  
### <a name="possible-cause"></a>Causa posible  
 La falta de una fase de comprobación se produce en un mensaje suspendido si A4SWIFT_MRSRLastStage no está establecida en crear.  
  
### <a name="solution"></a>Solución  
 Usar una suscripción de A4SWIFT_MRSRLastStage == crear para asegurarse de que el mensaje se enrute correctamente.  
  
## <a name="validation-of-message-results-a-parse-error-in-the-infopath-form-task-pane"></a>Resultados de validación del mensaje de un "error de análisis" en el panel de tareas del formulario de InfoPath  
  
### <a name="symptom"></a>Síntoma  
 Validar botón de mensaje en el panel de tareas de formulario muestra "error al analizar" sin ninguna descripción de InfoPath.  
  
### <a name="solution"></a>Solución  
 Reinicie el servicio web MRSR o no haga iisreset.  
  
## <a name="publishing-an-infopath-form-results-an-authorization-error"></a>Publicación de un formulario de InfoPath genera un error de autorización  
  
### <a name="symptom"></a>Síntoma  
 Publicar un formulario de InfoPath, produce el error de autorización.  
  
### <a name="solution"></a>Solución  
 Reemplace el nombre de la máquina localhost en la dirección URL del sitio MRSR.  
  
## <a name="infopath-form-task-pane-shows-html-source-code"></a>Panel de tareas del formulario de InfoPath muestra el código fuente HTML  
  
### <a name="symptom"></a>Síntoma  
 Panel de tareas del formulario de InfoPath muestra del código fuente HTML en lugar de controles Web.  
  
### <a name="solution"></a>Solución  
 Vaya a **herramientas**-> **ficha seguridad** -> **zona de Internet**y habilitar **archivo abierto basado en contenido no en la extensión** en varios.  
  
## <a name="profile-web-client-website-results-an-authentication-error"></a>Sitio Web de cliente Web de perfil produce un error de autenticación  
  
### <a name="symptom"></a>Síntoma  
 Sitio Web de cliente Web de perfil muestra el error de autenticación.  
  
### <a name="solution"></a>Solución  
 Ejecute el **BTSharePointAdapterWSAppPool** y **DefaultAppPoolApplication** -> y grupo en Internet información Services (IIS) en la cuenta de administrador.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas: problemas y soluciones](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)