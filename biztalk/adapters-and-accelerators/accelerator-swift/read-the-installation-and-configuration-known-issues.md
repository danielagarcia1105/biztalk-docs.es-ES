---
title: "Leer la instalación y problemas conocidos de configuración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c58d9dcb-7835-4181-a6cb-203c5d138e6a
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83bbeec3430f479d28502e818b9ead402278f9b1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="read-the-installation-and-configuration-known-issues"></a>Leer la instalación y configuración que se describen los problemas conocidos
  
## <a name="installing-over-terminal-server-creates-log-files-in-a-different-folder"></a>La instalación a través de Terminal Server crea archivos de registro en una carpeta diferente  
 Cuando instala A4SWIFT sobre una conexión de Terminal Server, el programa de instalación de A4SWIFT crea los archivos de registro de instalación y configuración en el  *\<unidad\>*: \Documents and Settings\\  *\<nombre de usuario\>*carpeta de \Local Settings. Normalmente, el programa de instalación crea estos archivos en el  *\<unidad\>*: \Documents and Settings\\*\<nombre de usuario\>*\Local Carpeta Settings\temp. Puede revisar estos archivos de registro para asegurarse de que los equipos se instala y configura correctamente.  
  
## <a name="silent-installation-is-not-recommended"></a>No se recomienda la instalación silenciosa  
 Una instalación silenciosa es compatible con el programa de instalación de A4SWIFT, pero no se recomienda debido a la complejidad de los pasos de configuración adicionales que son necesarios.  
  
## <a name="a4swift-setup-runs-with-the-installplatform-argument-that-overwrites-dlls-for-visualstudionet"></a>El programa de instalación de A4SWIFT se ejecuta con el argumento /InstallPlatform que sobrescribe los archivos DLL para VisualStudio.Net  
 El programa de instalación de A4SWIFT siempre se ejecuta con el argumento /InstallPlatform. Como resultado, el programa de instalación de A4SWIFT siempre instala msvcr71.dll, mfc71u.dll, msvcp71.dll y atl71.dll, que son necesarios para [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. El programa de instalación de A4SWIFT instala estos archivos DLL en la carpeta %WINDIR%\System32, si los archivos DLL instalados previamente o no.  
  
## <a name="canceling-a4swift-configuration-will-fail"></a>Cancelar A4SWIFT configuración se producirá un error  
 Haga clic en **cancelar** durante A4SWIFT configuración no cancelar la configuración. El proceso de configuración continuará hasta que finalice.  
  
## <a name="after-unconfiguring-a4swift-you-cannot-reconfigure-in-the-same-instance-of-the-configuration-console"></a>Después de quitar la configuración de A4SWIFT, no se vuelve a configurar en la misma instancia de la consola de configuración  
 Si quita la configuración de A4SWIFT, o un componente de A4SWIFT, no se puede volver a configurar A4SWIFT o su componente sin cerrar primero la consola de configuración de A4SWIFT y, a continuación, volver a abrirlo. Si no lo hace, algunos de los campos de la consola de configuración, aparecerá atenuadas y no podrá seleccionar valores para ellos.  
  
## <a name="configuration-of-a-web-components-only-installation-will-succeed-even-if-no-a4swift-database-exists"></a>Configuración de una instalación de solo componentes Web tendrá éxito aun cuando no exista ninguna base de datos de A4SWIFT  
 Si se realiza una instalación personalizada que se instala únicamente los componentes Web para la característica de reparación de mensajes y nuevo envío y, a continuación, ejecute el Acelerador de Microsoft BizTalk para SWIFT Asistente para la configuración, el programa de configuración se completará correctamente incluso Aunque no hay ninguna base de datos de A4SWIFT.  
  
 Una base de datos de A4SWIFT se mostrará en el **componentes Web de reparación de mensajes y nuevo envío** panel del cuadro de diálogo Configuración de A4SWIFT, incluso si esa base de datos no existe. Una advertencia será muestra para la A4SWIFT base de datos en los datos almacena panel, pero que advertencia no impedirá el proceso de configuración continuar.  
  
## <a name="upgrade-process-does-not-create-a-new-root-folder"></a>Proceso de actualización no crea una nueva carpeta de raíz  
 El proceso de actualización actualiza los archivos de A4SWIFT existente  *\<unidad\>*: \Program Acelerador de BizTalk para la carpeta de A4SWIFT 2.3/3.0. No crea una nueva carpeta para los archivos actualizados, ni tampoco cambia el nombre de la carpeta existente a  *\<unidad\>*: \Program Acelerador de BizTalk para SWIFT.  
  
## <a name="canceling-setup-during-an-upgrade-for-a4swift-may-leave-your-system-in-an-unknown-state"></a>Cancelar el programa de instalación durante la actualización de A4SWIFT puede dejar el sistema en un estado desconocido  
 En algunos escenarios, al hacer clic en el **cancelar** botón durante una actualización puede dejar archivos, los ensamblados, los artefactos de BizTalk Server y claves del registro intacto después de que el programa de instalación ha finalizado su restauración.  
  
 También puede quitar manualmente todos los elementos sin problemas.  
  
## <a name="download-the-a4swift-setup-exe-file-from-the-web-into-a-temp-folder"></a>Descargue el archivo exe de instalación de A4SWIFT desde el sitio Web en una carpeta temporal  
 Si va a instalar A4SWIFT desde un archivo ejecutable autoextraíble que descargó desde el sitio Web, asegúrese de descargar ese archivo en una carpeta temporal. Descargue el archivo en la carpeta raíz de BizTalk Server (BizTalk Server \Program \< *su versión*\>).  
  
 Si ejecuta el archivo exe desde la carpeta raíz de BizTalk Server, se ejecuta al servidor BizTalk Server Asistente para la instalación, no el Asistente de instalación de A4SWIFT.  
  
## <a name="installing-a4swift-in-a-location-other-than-the-default-requires-changes-to-the-bredeploymentexeconfig-file"></a>La instalación de A4SWIFT en una ubicación distinta de la predeterminada requiere cambios en el archivo BREDeployment.exe.config  
 Si instala BizTalk Accelerator para SWIFT en una ruta de acceso que no sea la ruta de acceso predeterminada de %programfiles%\Microsoft BizTalk Accelerator para SWIFT, debe editar el archivo BREDeployment.exe.config en el subdirectorio SDK\Tools del producto para reflejar las rutas de acceso correcta para los BasePoliciesDirectory, SchemasDirectory y VocabularyDirectory.  
  
 Debe realizar este cambio antes de intentar implementar cualquiera de las reglas asociadas con los esquemas SWIFT incluidos en los proyectos para implementar correctamente las reglas pertinentes y el vocabulario.  
  
## <a name="message-repair-is-not-supported-for-certain-batched-message-scenarios"></a>Reparación de mensajes no se admite en determinados escenarios de mensaje por lotes  
 A4SWIFT sólo admite la reparación de mensajes de fragmentación de escenarios de procesamiento por lotes. En estos casos, se puede reparar sólo la parte del intercambio de mensajes por lotes.  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-anything-other-than-unparsed"></a>No pueden enviar un mensaje sin analizar fijo desde una biblioteca de sitio MRSR denominada algo distinto de Unparsed  
 Al intentar enviar un mensaje sin analizar que haya corregido desde una biblioteca de documentos del sitio MRSR que no se denomina "Unparsed", se produce un error en la operación porque A4SWIFT correctamente no se puede enviar un mensaje desde una biblioteca que no se denomina "Unparsed."  
  
 Si tiene una biblioteca de documentos "Sin analizar" existente en el sitio MRSR antes de instalar la característica de conciliación y reparación de mensajes, el programa de instalación de A4SWIFT crea una biblioteca para los mensajes sin analizar titulada "Sin analizar" con un sufijo.  
  
 Cuando A4SWIFT recibe un mensaje que no pueden analizar, enruta el mensaje a la biblioteca creada por el programa de instalación. Sin embargo, al intentar enviar un mensaje de dicha biblioteca, se produce un error en la operación.  
  
 Este problema normalmente se produciría si uninstal A4SWIFT y no quite la biblioteca de documentos "Sin analizar" desde el sitio MRSR.  Al volver a instalar SWIFT en estas circunstancias, el programa de instalación crea una nueva biblioteca de documentos con el nombre "Unparsed" con un sufijo."  
  
 Para resolver este problema, siga este procedimiento:  
  
#### <a name="to-name-a-library-unparsed-in-order-to-submit-unparsed-messages"></a>Un nombre de una biblioteca "Unparsed" con el fin de enviar mensajes sin analizar  
  
1.  Quitar la característica de reparación de mensajes y reconciliación.  
  
2.  Elimine manualmente la biblioteca sin analizar. Esto no se eliminarán al desinstalar A4SWIFT.  
  
3.  Vuelva a instalar conciliación y reparación de mensajes. Durante la reinstalación, la biblioteca de documentos se creará con el nombre "Unparsed" y puede enviar los mensajes sin analizar fijos a través de esta biblioteca de documentos.  
  
## <a name="bredeployment-utility-cannot-deploy-or-undeploy-policies-if-a4swift-vocabularies-are-not-correctly-configured"></a>BREDeployment utilidad no se puede implementar o anular la implementación de directivas si vocabularios de A4SWIFT no están configurados correctamente  
 Si intenta anular la implementación de directivas del motor de reglas de negocios de A4SWIFT mediante la herramienta BREDeployment.exe y el archivo de configuración BREDeployment.exe no apunta a la ubicación del archivo vocabulario correcta, la herramienta puede notificar un error. Tendrá este problema si cambia la ubicación en el archivo de configuración de BREDeployment.exe y la nueva ubicación no contiene los archivos de vocabulario. El error indica que no se encontraron los vocabularios y deja de la configuración de directivas de implementar o anular la implementación.  
  
 Para resolver este problema, use el estándar **Asistente para implementación de motor de reglas de negocios**. Detalles de la interfaz de usuario son [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-swift/known-issues5.md)