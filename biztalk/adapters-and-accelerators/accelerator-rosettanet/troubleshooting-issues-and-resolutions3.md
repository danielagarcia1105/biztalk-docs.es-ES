---
title: "Solución de problemas: Problemas y Resolutions3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: 40f59f54-183e-43db-afb5-0a45b437697f
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed990dd60ab65c7b85284a9eeadd4b27de3136f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-issues-and-resolutions"></a>Solución de problemas: Problemas y soluciones
Este tema tratan los problemas relacionados con la ejecución [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. La persona emite detalle un síntoma específico, una posible causa y una solución.  
  
## <a name="error-publishing-a-batch-of-n-messages"></a>Error al publicar un lote de mensajes "n"  
  
### <a name="symptom"></a>Síntoma  
 Recibe el error siguiente o uno similar en el registro de eventos:  
  
 El motor de mensajería detectó un error al publicar un lote de mensajes "n" en la base de datos de cuadro de mensaje para el adaptador de transporte "Receptor HTTP de BizTalk". Consulte herramienta de seguimiento de estado y actividad para obtener más información sobre este error y compruebe que los enlaces de extremo están configurados correctamente.  
  
### <a name="possible-cause"></a>Causa posible  
 Este error podría deberse a uno de los siguientes motivos:  
  
-   Falta el certificado de descifrado  
  
-   Mensaje cifrado incorrectamente  
  
-   Mensaje no autorizado (origen no se reconoce como un socio válido)  
  
-   Errores de validación de cualquier parte del encabezado de mensaje: preámbulo, encabezado de entrega o encabezado de servicio.  
  
 Este mensaje puede ir precedido de otro mensaje de error que detalla a la causa.  
  
### <a name="solution"></a>Solución  
 Revise los detalles proporcionados con el mensaje de error para obtener ayuda adicional. Reiniciar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ puede resolver este problema.  
  
## <a name="you-cannot-unenlist-all-artifacts"></a>No se puede dar de baja todos los artefactos  
  
### <a name="symptom"></a>Síntoma  
 Ejecuta el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]utilidad limpia no dar de baja todos los artefactos.  
  
### <a name="possible-cause"></a>Causa posible  
 Si ejecuta el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]limpiar utilidad antes de eliminar acuerdos y socios de la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Management Console (MMC), la utilidad BtarnClean no podrá dar de baja todos los artefactos porque todavía se usan.  
  
### <a name="solution"></a>Solución  
  
##### <a name="to-remove-artifacts-using-the-loopback-utility"></a>Para quitar artefactos mediante la utilidad de bucle invertido  
  
1.  En el símbolo del sistema, escriba:  
  
    ```  
    lookback.exe /disable <home org or partner>  
    ```  
  
2.  Ejecute el archivo BtarnClean.exe.  
  
3.  En el Explorador de BizTalk, elimine las partes.  
  
## <a name="installing-btarn-on-a-computer-without-biztalk-server-causes-missing-files"></a>Instalación de BTARN en un equipo sin BizTalk Server hace que los archivos que faltan  
  
### <a name="symptom"></a>Síntoma  
 Ejecutar el archivo ConfigFramework.exe no produce ningún resultado en un equipo que no tiene [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] o [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] instalado. Sólo se puede utilizar esto [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuración como un cliente HTTP.  
  
### <a name="possible-cause"></a>Causa posible  
 Faltan dos archivos DLL de la instalación.  
  
### <a name="solution"></a>Solución  
 Instale SQLXML en el equipo y, a continuación, copie manualmente los archivos Msxml4.dll y Atl71.dll a la carpeta del sistema.  
  
## <a name="you-receive-an-access-error-when-attempting-to-change-the-btarn-configuration"></a>Recibirá un error de acceso al intentar cambiar la configuración de BTARN  
  
### <a name="symptom"></a>Síntoma  
 Recibirá el siguiente mensaje de error al importar un archivo de configuración mediante el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración:  
  
 No se pudo almacenar datos de tipo de transporte para principal transporte del puerto de envío ' RNSTT. Async' para el almacén de configuración. Acceso denegado.  
  
 También puede recibir este error al intentar cambiar la configuración, por ejemplo, mediante la creación de un asociado de nuevo.  
  
### <a name="possible-cause"></a>Causa posible  
 El usuario actual no es un miembro del grupo Administradores de BizTalk.  
  
### <a name="solution"></a>Solución  
 Asegúrese de que el usuario actual es un miembro del grupo Administradores de BizTalk.  
  
## <a name="you-receive-bam-errors"></a>Recibe errores BAM  
  
### <a name="symptom"></a>Síntoma  
 Recibir los mensajes de error siguientes en el Visor de eventos:  
  
 Se produjo un error en el seguimiento de la actividad de mensaje. Mensaje de error es almacenado no existe el procedimiento.  
  
 -O bien-  
  
 Error al terminar la actividad de BAM de mensajes con el identificador  *\<número de Id. >*.  
  
### <a name="possible-cause"></a>Causa posible  
 La herramienta de seguimiento de supervisión de la actividad económica (BAM) no está instalada.  
  
### <a name="solution"></a>Solución  
 Instalar la herramienta uso de seguimiento de BAM el **instalación personalizada** opción. Si no necesita funcionalidad BAM, puede omitir estos mensajes o deshabilitar el seguimiento mediante la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración. Después de deshabilitar el seguimiento, debe reiniciar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y en Internet y en Information Services (IIS).  
  
## <a name="your-xsd-schema-does-not-display-properly-in-biztalk-editor"></a>El esquema XSD no se muestren correctamente en el Editor de BizTalk  
  
### <a name="symptom"></a>Síntoma  
 No se puede ver el contenido de un esquema correctamente en el Editor de BizTalk.  
  
### <a name="possible-cause"></a>Causa posible  
 El esquema es falta el `displayroot_reference` de atributo para el `schemaInfo` elemento.  
  
### <a name="solution"></a>Solución  
 Abra el esquema en el Bloc de notas u otro editor de texto y agregue el `displayroot_reference` atribuir a la `schemaInfo` elemento. El valor de la `displayroot_reference` atributo debe ser el mismo que el `root_reference` atributo.  
  
 Por ejemplo:  
  
 \<schemaInfo document_type = "4A1" version = "V02_00" xmlns = "http://schemas.microsoft.com/BizTalk/2003" *displayroot_reference = "Pip4A1StrategicForecastNotification"* root_reference = " Pip4A1StrategicForecastNotification"/ >  
  
## <a name="404-not-found-error-when-sending-a-http-request"></a>404 no encontrado errores al enviar una solicitud HTTP  
  
### <a name="symptom"></a>Síntoma  
 Recibir los errores siguientes o similares al enviar una solicitud HTTP:  
  
 El servidor remoto devolvió un error: (404) no se encuentra.  
  
 No se puede enviar el mensaje a... / BTSHttpReceive.dll.  
  
### <a name="possible-cause"></a>Causa posible  
 El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (BTSHttpReceive.dll) de la DLL de extensión de Internet Server API (ISAPI) no se ha configurado en Internet Information Services (IIS). Esto ocurre si no se configura la extensión de servicio web de HwsMessages HttpReceive y si esta extensión de servicio web está configurada, pero no permitida.  
  
### <a name="solution"></a>Solución  
 Para determinar si se configura la extensión de servicio web de HwsMessages HttpReceive, y si lo no está configurado, para permitirlo, realice el procedimiento siguiente.  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a>Para configurar el archivo DLL de extensión ISAPI de BizTalk en IIS  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  Expanda  **\<nombre_equipo > (equipo local)**y, a continuación, haga clic en **extensiones de servicio Web**.  
  
3.  En el **extensión de servicio Web** panel, compruebe que se permite el estado de HwsMessages HttpReceive. Si no es así, haga clic en **HwsMessages HttpReceive**y, a continuación, haga clic en **permitir**.  
  
 Si no se configura la extensión de servicio web de HwsMessages HttpReceive (no se incluye en la lista de extensiones de servicio Web en el Administrador de IIS), realice el procedimiento siguiente.  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a>Para configurar el archivo DLL de extensión ISAPI de BizTalk en IIS  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  Expanda  **\<nombre_equipo > (equipo local)**, haga clic en **extensiones de servicio Web**y, a continuación, haga clic en **agregar una nueva extensión de servicio Web**.  
  
3.  En el **nueva extensión de servicio Web** cuadro de diálogo, en la **nombre de la extensión** , escriba **extensión de ISAPI de BizTalk**y, a continuación, haga clic en **agregar**.  
  
4.  En el **Add File** cuadro de diálogo, en la **ruta de acceso al archivo** , escriba  **\<unidad >: \Program BizTalk Server \<versión > \HttpReceive\ BTSHttpReceive.dll**y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **nueva extensión de servicio Web** cuadro de diálogo, seleccione **establecer el estado de extensión a permitido**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="an-access-violation-occurs-when-running-the-configuration-wizard"></a>Se produce una infracción de acceso cuando se ejecuta al Asistente para configuración  
  
### <a name="symptom"></a>Síntoma  
 Recibe el error siguiente o uno similar en el registro de eventos:  
  
 Una instancia de host aislado de BizTalk configurada con la cuenta de usuario '\HostSvc' no se estaba ejecutando o no existe en este equipo. Utilice la consola de administración de BizTalk para crear un nuevo host aislado o volver a configurar una existente para ejecutarse como '\hostsvc'.  
  
### <a name="possible-cause"></a>Causa posible  
 Para ejecutar el Asistente para configuración, el usuario debe estar configurado como\<*nombre de la máquina*> \hostsvc', no '\hostsvc'.  
  
### <a name="solution"></a>Solución  
 Abra la consola de administración de BizTalk y cambiar los hosts que se ejecutan en la cuenta '\hostsvc', por lo que se ejecutan en la cuenta '\<*nombre de la máquina*> \hostsvc'.  
  
## <a name="you-receive-an-error-when-importing-and-compiling-a-rosettanet-next-generation-pip-schema"></a>Recibirá un error al importar y compilar un esquema de PIP de RosettaNet siguiente generación  
  
### <a name="symptom"></a>Síntoma  
 Recibe el error siguiente o uno similar en el registro de eventos:  
  
 Error del CS0234: el nombre de tipo o espacio de nombres 'SerializableAttribute' no existe en la clase o espacio de nombres 'RosettaNet.Schemas.System' (¿falta una referencia de ensamblado?).  
  
### <a name="possible-cause"></a>Causa posible  
 Uno de los esquemas, por ejemplo, StandardDocumentHeader.xsd, tiene un [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] espacio de nombres de RosettaNet.Schemas.System.  
  
### <a name="solution"></a>Solución  
 Quitar el "sistema" de la [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] espacio de nombres para el esquema, por lo que el espacio de nombres es RosettaNet.Schemas.  
  
## <a name="you-receive-an-error-when-trying-to-manually-deploy-the-bam-package"></a>Recibe un error al intentar implementar manualmente el paquete de BAM  
  
### <a name="symptom"></a>Síntoma  
 Cuando manualmente intenta implementar el paquete BAM para [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], recibirá un error que indica que no se puede implementar el paquete.  
  
### <a name="possible-cause"></a>Causa posible  
 Los paquetes DTS BAM_DM_Process y BAM_DM_Message están instalados en el sistema, evitar la implementación del paquete BAM.  
  
### <a name="solution"></a>Solución  
  
##### <a name="to-recover-from-the-error-condition-and-deploy-the-bam-package"></a>Para recuperarse de la condición de error e implementar el paquete BAM  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server**y, a continuación, haga clic en **Enterprise Manager**.  
  
2.  En el Administrador corporativo, expanda **servidores Microsoft SQL Server**, **grupo de SQL Server**, **(local) (Windows NT)**, y **Data Transformation Services**.  
  
3.  Haga clic en **paquetes locales**, haga clic en **BAM_DM_Message**y, a continuación, haga clic en **eliminar**.  
  
4.  Haga clic en **BAM_DM_Process**y, a continuación, haga clic en **eliminar**.  
  
5.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
6.  En el símbolo del sistema, escriba el código siguiente para implementar el archivo de seguimiento y, a continuación, haga clic en **Aceptar**.  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server <version>\Tracking  
    bm deploy all  "%ProgramFiles%\Microsoft BizTalk <version> Accelerator for RosettaNet\BAMTracking\tracking.xml"  
    ```  
  
## <a name="you-receive-an-error-when-adding-a-new-pip"></a>Recibe un error al agregar un nuevo PIP  
  
### <a name="symptom"></a>Síntoma  
 Recibe el error siguiente o uno similar en el registro de eventos:  
  
 UNP. SCON. VALERR: Se produjo un error al validar el contenido del servicio.  
  
 Detalles: Encontrar la especificación de documento por tipo de mensaje de error. Compruebe que el esquema se implementa correctamente.  
  
### <a name="possible-cause"></a>Causa posible  
 El espacio de nombres del documento o la propiedad de nodo raíz del esquema implementado para la instancia Pip4A5NotifyofForecastReply es incorrecto.  
  
### <a name="solution"></a>Solución  
 Compruebe que el espacio de nombres de documento y la propiedad de nodo raíz para el esquema implementado para la instancia Pip4A5NotifyofForecastReply es correcta.  
  
## <a name="error-during-the-configuration-of-btarn-at-installation-time-caused-by-presumed-network-connectivity-issues"></a>Error durante la configuración de BTARN en el momento de la instalación causada por supone que problemas de conectividad de red  
  
### <a name="symptom"></a>Síntoma  
 Durante el proceso de configuración, recibirá un error en el cuadro de diálogo de error que indica que el equipo no está conectado correctamente a la red, cuando en realidad es.  
  
### <a name="possible-cause"></a>Causa posible  
 Este error puede deberse a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] malinterpreten IP el programa de configuración de direcciones. El archivo de hosts en C:\Windows\system32\drivers\etc contiene una entrada que asigna el nombre de host del host local a la dirección IP 127.0.0.1. El programa de configuración puede confundir este valor con la dirección de bucle invertido y se supone que el equipo no está conectado correctamente a la red.  
  
### <a name="solution"></a>Solución  
  
##### <a name="to-avoid-this-error-and-complete-the-configuration-process"></a>Para evitar este error y completar el proceso de configuración  
  
1.  En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, mover a C:\Windows\system32\drivers\etc y abra el archivo de hosts con el Bloc de notas.  
  
2.  Convierta en comentario la línea "127.0.0.1 localhost" colocando "#" al principio de la línea. Guarde el archivo de hosts modificada.  
  
3.  Haga clic en **vuelva a intentar** en el cuadro de diálogo de error.  
  
4.  Después de configuración se completó correctamente, vuelva a abrir el archivo de hosts en el Bloc de notas, quite la marca de comentario al principio del host local de asignación de línea y, a continuación, guarde el archivo de hosts.  
  
## <a name="you-receive-an-error-regarding-incorrect-signature-length"></a>Recibirá un error relacionado con la longitud de la firma incorrecta  
  
### <a name="symptom"></a>Síntoma  
 Recibe el error siguiente o uno similar en el registro de eventos:  
  
 Se produjo un error al ejecutar la canalización de recepción: "Microsoft.Solutions.BTARN.Pipelines.Receive" origen: "Descodificador de MIME/SMIME" ubicación de recepción: "/ BTARNHttpReceive/BTSHTTPReceive.dll?xRNResponseType=async" motivo: longitud de firma incorrecta valor = 1935897193.  
  
### <a name="possible-cause"></a>Causa posible  
 Este mensaje de error indica que la longitud de la firma es incorrecta. Además de la causa de la anterior, este error también podría debido a la longitud del contenido de encabezado incorrecto o incompleto que hace que los bytes incorrectos de lectura en la longitud de la firma.  
  
### <a name="solution"></a>Solución  
 Compruebe que tanto de la longitud de la firma y la longitud de contenido de encabezado es correcto.  
  
## <a name="you-receive-503-service-unavailable-from-internet-explorer-on-64-bit-machine"></a>Recibirá "503: servicio no disponible" de Internet Explorer en el equipo de 64 bits  
  
### <a name="symptom"></a>Síntoma  
 Después de [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] se completa la configuración, cuando se intenta acceder a [http://localhost](http://localhost/) o [http://localhost/BtarnApp/RnifSend.aspx](http://localhost/BtarnApp/RnifSend.aspx), recibirá el error siguiente o uno similar:  
  
 503: servicio no disponible  
  
### <a name="possible-cause"></a>Causa posible  
 Este error puede deberse al filtro ISAPI que se encuentran en C:\windows\system32\rpcproxy\rpcproxy.dll que se va a establecer en sitios Web de IIS.  
  
### <a name="solution"></a>Solución  
  
##### <a name="to-remove-rpcproxy-filter-entry-in-iis"></a>Para quitar la entrada de filtro de RpcProxy en IIS  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  Expanda  **\<nombre_equipo > (equipo local)**, haga clic en **sitios Web**y, a continuación, haga clic en **propiedades**.  
  
3.  Seleccione **filtros ISAPI** ficha.  
  
4.  Seleccione **RpcProxy filtro**y haga clic en **quitar**.  
  
5.  Haga clic en **Aceptar**.  
  
6.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
7.  En el símbolo del sistema, escriba el código siguiente para restablecer IIS.  
  
    ```  
    iisreset  
    ```  
  
> [!NOTE]
>  Si se intenta tener acceso a http://localhost o http://localhost/BtarnApp/RnifSend.aspx nuevo después de realizar los pasos anteriores, recibirá el mensaje de HTTP 400 desde Internet Explorer, lo que significa que IIS funcione correctamente.  
  
## <a name="the-hubscenario-sample-will-not-be-installed-correctly-if-the-assembly-key-files-are-not-entered-for-the-projects"></a>El ejemplo de HubScenario no se instalará correctamente si no se especifican los archivos de clave de ensamblado para los proyectos  
  
### <a name="symptom"></a>Síntoma  
 Cuando ejecute el archivo setup.bat  *\<unidad >*: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK\HubScenario configurar el ejemplo de HubScenario, el se produce un error en la operación.  
  
### <a name="possible-cause"></a>Causa posible  
 Los ensamblados HubScenario y HubHelper no se implementaron correctamente porque los archivos de clave de ensamblado no se establecieron en los proyectos.  
  
### <a name="solution"></a>Solución  
 Establece los archivos de clave de ensamblado para los proyectos HubScenario y HubHelper. Para obtener más información, consulte [ejemplo de HubScenario](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md).  
  
## <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample-on-sql-server-2008-r22008-sp1"></a>Ejecutar setupx64.bat para configurar el ejemplo de orquestación de PIPAutomation de doble acción en SQL Server 2008 R2 o 2008 SP1  
  
### <a name="symptom"></a>Síntoma  
 Cuando ejecute setup.bat para crear e inicializar el ejemplo de orquestación de PIPAutomation de doble acción, procedimiento el PipAutomationGetAction almacenado en el BTARNData no se crea la base de datos.  
  
### <a name="possible-cause"></a>Causa posible  
 La ejecución de setup.bat en un equipo de 64 bits o en un [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] instalación que se ejecuta en SQL Server 2008 R2 o 2008 SP1. Ambas instancias deberá ejecutar setupx64.bat.  
  
### <a name="solution"></a>Solución  
 Ejecutar setupx64.bat para crear el procedimiento almacenado. Para obtener más información, consulte [orquestación de PIPAutomation de doble acción](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).  
  
## <a name="enable-the-btarn-application-pools-for-32-bit-on-windows-server-2008-64-bit-windows-operating-system-os"></a>Habilitar los grupos de aplicaciones de BTARN de 32 bits en Windows Server 2008, sistema operativo de Windows de 64 bits (SO)  
 Para ejecutar el escenario de extremo a extremo BTARN en Windows Server 2008,64 bits Windows sistema operativo (SO), Internet Information Services Manager 7.5 o 7.0.  
  
 1. Habilitar los grupos de aplicaciones de BTARN de 32 bits.  
  
 2. Agregue un controlador HTTP para referencia *.dll los filtros IsapiModule.  
  
## <a name="see-also"></a>Vea también  
 [BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md)   
 [Bucle invertido](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)