---
title: Instalación y solución de problemas de configuración | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, troubleshooting
- configuring, troubleshooting
- troubleshooting, configuring
- troubleshooting, installing
ms.assetid: 25a2f6c5-c049-4042-8e38-4f7a2556e066
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10c0816508d2efb05dbac14797f80ffef12765fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967181"
---
# <a name="installation-and-configuration-troubleshooting"></a>Instalación y solución de problemas de configuración
## <a name="setup-is-unable-to-deploy-the-runtimeschemas-assembly"></a>El programa de instalación no puede implementar el ensamblado RuntimeSchemas  
  
### <a name="symptom"></a>Síntoma  
 El programa de instalación de A4SWIFT no pudo implementar RuntimeSchemas.dll. Si el ensamblado no se implementa manualmente después de la instalación, se produce un error en el Asistente para configuración de A4SWIFT.  
  
### <a name="possible-cause"></a>Causa posible  
 Existe una de las condiciones siguientes:  
  
- Ya se ha implementado el ensamblado de esquemas en tiempo de ejecución cuando intentó realizar una instalación inicial de A4SWIFT.  
  
- Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] no se inició en el equipo en el que se intentó instalar A4SWIFT.  
  
- Ya se ha implementado el ensamblado de esquemas en tiempo de ejecución cuando se intentó actualizar A4SWIFT y hacía referencia otro ensamblado. Esta anulación impedía del ensamblado de esquemas en tiempo de ejecución por el A4SWIFT actualizar el programa.  
  
### <a name="solution"></a>Solución  
 Haga lo siguiente, según la naturaleza del problema:  
  
- Si ya se ha implementado el ensamblado de esquemas en tiempo de ejecución cuando se intentó ejecutar una instalación inicial de A4SWIFT, abra el Explorador de BizTalk en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)], haga clic en el ensamblado de Microsoft. Solutions.FinancialServices.SWIFT.RuntimeSchemas y, a continuación, haga clic en anular la implementación. Usar el Asistente para la implementación de BizTalk para implementar la versión más reciente de RuntimeSchemas.dll desde *% programfiles %* \Microsoft BizTalk Accelerator para SWIFT\Assemblies.  
  
- Si [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] no fue iniciado, inicie [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Service Manager. Usar el Asistente para la implementación de BizTalk para implementar la versión más reciente de RuntimeSchemas.dll desde *% programfiles %* \Microsoft BizTalk Accelerator para SWIFT\Assemblies.  
  
- Si ya se ha implementado el ensamblado de esquemas en tiempo de ejecución cuando se intentó actualizar A4SWIFT y hacía referencia otro ensamblado, anular la implementación del ensamblado que hace referencia en el Explorador de BizTalk y anular la implementación de RuntimeSchemas.dll en el Explorador de BizTalk. Usar el Asistente para la implementación de BizTalk para implementar la versión más reciente de RuntimeSchemas.dll desde *% programfiles %* \Microsoft BizTalk Accelerator para SWIFT\Assemblies.  
  
## <a name="after-the-web-components-feature-is-removed-message-repair-and-reconciliation-is-incorrectly-shown-as-uninstalled"></a>Después de quita la característica Web Components, reparación de mensajes y reconciliación se muestra incorrectamente como desinstalado  
  
### <a name="symptom"></a>Síntoma  
 Después de quitar los componentes Web para la característica de reparación de mensajes y nuevo envío de A4SWIFT, no se puede desinstalar, instalar o configurar la reparación de mensajes y la característica de conciliación (o los componentes de A4SWIFT). Si está instalada la reparación de mensajes y reconciliación, A4SWIFT no reconoce que se instala la característica. Si intenta instalar, modificar o quitar la reparación de mensajes y reconciliación desde dentro de agregar o quitar programas (se muestra en el Panel de Control de), agregar o quitar programas indicará que la característica no está instalada.  
  
### <a name="possible-cause"></a>Causa posible  
 Se quitaron los [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] después de que instaló los componentes Web para la característica de reparación de mensajes y nuevo envío y la característica de reparación de mensajes y reconciliación de grupo de administradores. Si después quita la característica Web Components (lo que puede hacer sin ser miembros de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores), el programa de instalación de A4SWIFT quitará los archivos que repare el mensaje y característica Conciliación tiene una dependencia en. Estos archivos incluyen ConfigFramework.exe.  
  
### <a name="solution"></a>Solución  
 Si se produce este problema, haga lo siguiente:  
  
1. En la ventana Administración de equipos, agregar usted mismo en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo administrador, cierre sesión en el equipo y, a continuación, vuelva a iniciar sesión.  
  
2. Vuelva a instalar los componentes Web para la característica de reparación de mensajes y nuevo envío.  
  
   > [!NOTE]
   >  Paso 2 agrega ConfigFramework.exe en la instalación de A4SWIFT.  
  
3. Vuelva a instalar la característica MRSR.  
  
4. Si no desea los componentes Web de reparación de mensajes y la característica de nuevo envío, quítelo.  
  
## <a name="repairing-a4swift-to-add-the-service-folder-can-result-in-improper-access-permissions-for-that-folder"></a>Reparación de A4SWIFT para agregar la carpeta del servicio puede dar lugar a permisos de acceso no es adecuada para esa carpeta  
  
### <a name="symptom"></a>Síntoma  
 Si elimina la carpeta *% programfiles %* \Microsoft BizTalk Accelerator para SWIFT\Service desde una instalación de A4SWIFT correctamente configurada y, a continuación, ejecute hacer una copia de la característica de reparación del programa de instalación de A4SWIFT para agregar la carpeta del servidor en el A4SWIFT instalación, los permisos de acceso para la carpeta del servicio no serán correctos. Los permisos correctos son Control total para los administradores de A4SWIFT y lectura y ejecución para los usuarios de A4SWIFT.  
  
 Esto también ocurre si se ejecuta la característica de reparación del programa de instalación de A4SWIFT cuando existe la carpeta del servicio. Los permisos de acceso, según lo establecido por el Asistente para configuración de A4SWIFT, se sobrescribirán con valores incorrectos.  
  
### <a name="possible-cause"></a>Causa posible  
 Instalar los componentes Web de reparación de mensajes y nuevo envío característica agrega la carpeta del servicio. Si elimina la carpeta y, a continuación, ejecute la opción de reparación del programa de instalación de A4SWIFT para agregar los componentes Web de reparación de mensajes y nuevo envío, el programa de instalación de A4SWIFT no ejecuta al Asistente para configuración (ConfigFramework.exe) para establecer los permisos para la carpeta. Dado que ya se ha ejecutado el Asistente para configuración, es muy difícil ejecutar el Asistente para nuevo para restablecer la configuración. Como resultado, la opción de reparación creará de nuevo todos los archivos y carpetas eliminados, pero no establecerá los permisos de acceso correctamente.  
  
 El proceso de reparación también sobrescribe los permisos para la carpeta del servicio si la carpeta no existe cuando se ejecute la reparación. Como con el caso de la eliminación de la carpeta del servicio antes de ejecutar la reparación, será muy difícil ejecutar el programa de configuración para establecer los permisos. En este caso, además, los permisos serán incorrectos y tendrá que establecerlos manualmente.  
  
### <a name="solution"></a>Solución  
 Si se produce este problema, establezca manualmente los siguientes permisos de acceso para la carpeta del servicio:  
  
|Nombre de usuario o grupo|Permiso|  
|------------------------|----------------|  
|Administradores de A4SWIFT|Control total|  
|Usuarios de A4SWIFT|Leer y ejecutar|  
  
 Para establecer estos permisos, haga lo siguiente:  
  
 En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, desplácese a *% programfiles %* \Microsoft BizTalk Accelerator para SWIFT\Service.  
  
1.  Haga clic en la carpeta del servicio, haga clic en **propiedades**y, a continuación, haga clic en el **seguridad** ficha.  
  
2.  En el panel de nombres de usuario o grupo del cuadro de diálogo Propiedades del servicio, haga clic en **agregar**, escriba ***\<nombre del servidor\>* administradores \A4SWIFT**y, a continuación, haga clic en **Aceptar** .  
  
    > [!NOTE]
    >  Si el grupo de administradores de A4SWIFT es un grupo de dominio, escriba ***\<nombre de dominio\>* administradores \A4SWIFT**.  
  
3.  Repita el paso 2 para ***\<nombre del servidor\>* \A4SWIFT usuarios**, o  **\< *nombre de dominio*\>\A4SWIFT usuarios** si el Grupo de usuarios de A4SWIFT es un grupo de dominio.  
  
4.  En el panel de nombres de usuario o grupo, seleccione **A4SWIFT administradores**. En el panel permisos, seleccione **permitir** para **Control total**.  
  
5.  En el panel de nombres de usuario o grupo, seleccione **los usuarios de A4SWIFT**. En el panel permisos, haga clic en **permitir** para **lectura y ejecución**, **mostrar contenido de carpetas**, y **lectura**.  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="upgrade-results-in-a-side-by-side-installation-of-two-versions-of-a4swift"></a>Resultados de la actualización en una instalación en paralelo de dos versiones de A4SWIFT  
  
### <a name="symptom"></a>Síntoma  
 Al intentar actualizar a [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], no se pueden quitar totalmente las versiones anteriores de A4SWIFT. Si ejecuta Agregar o quitar programas del Panel de Control, puede mostrar la lista de programas actualmente instalados actual y las versiones anteriores.  
  
### <a name="possible-cause"></a>Causa posible  
 Cualquiera de las siguientes condiciones pueden provocar que se produzca el anterior:  
  
- El usuario está intentando actualizar no es un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  
  
- El [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] se detiene el servicio (MSSQLSERVER).  
  
- Realiza un uso de actualización silenciosa la **setup.exe /addlocal** comando.  
  
### <a name="solution"></a>Solución  
 Para evitar la instalación en paralelo de [!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)] y [!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)] que se producen durante la actualización, asegúrese de que usted (el usuario ha iniciado sesión) es un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo de administradores y que la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] se inicia el servicio (MSSQLSERVER).  
  
 Si acaba con una instalación en paralelo de [!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)] o [!INCLUDE[btaA4SWIFT2.1abbrev](../../includes/btaa4swift2-1abbrev-md.md)] y [!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)], haga lo siguiente:  
  
1. Realizar una copia de seguridad de los datos en la carpeta mensajes SWIFT.  
  
2. Inicie sesión en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como miembro de los administradores de BTS y asegúrese de que se está ejecutando el servicio MSSQLSERVER.  
  
3. Quite la versión anterior de A4SWIFT.  
  
4. Actualizar de nuevo a la versión más reciente de A4SWIFT. Esta vez funcionará la actualización y no se creará ninguna instalación en paralelo.  
  
5. Con la utilidad de implementación de BizTalk manualmente anular la implementación de Microsoft. Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll y, a continuación, volver a implementarla desde la carpeta de ensamblados de la ubicación de instalación de A4SWIFT. Para obtener más información sobre esta herramienta, consulte [utilidad de implementación de BRE](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md).  
  
## <a name="the-uninstall-or-upgrade-process-may-not-complete-correctly-if-you-do-not-restart-when-prompted"></a>El proceso de desinstalación o actualización no puede completarse correctamente si no reinicia cuando se le pida  
  
### <a name="symptom"></a>Síntoma  
 Desinstalar o procesos de actualización no se completan correctamente.  
  
### <a name="possible-cause"></a>Causa posible  
 Si no se ha anulado implementación de un proyecto que hace referencia a un ensamblado implementado existente, puede recibir un mensaje que indica que debe reiniciar el sistema para que surtan efecto los cambios de configuración de A4SWIFT. Si no hace clic en **Sí** para reiniciar inmediatamente, algunos ensamblados que se asignaron para su eliminación en la caché global de ensamblados no pueden quitarse, causando desinstalación adicional o procesos de actualización sin completarse correctamente.  
  
### <a name="solution"></a>Solución  
 Anular la implementación de cualquier proyecto que hace referencia a un ensamblado implementado existente y, a continuación, ejecute de nuevo el proceso de desinstalación o actualización.  
  
## <a name="if-the-iis-admin-service-is-stopped-during-setup-you-must-reconfigure-the-webservice-feature"></a>Si el servicio de administración de IIS se detiene durante la instalación, debe volver a configurar la característica de servicio Web  
  
### <a name="symptom"></a>Síntoma  
 El [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Asistente para configuración no configura la característica de servicio Web correctamente. Recibe el error siguiente:  
  
 "No se puede crear artefactos MRSR: no se puede conectar al servidor remoto."  
  
### <a name="possible-cause"></a>Causa posible  
 Se detuvo el servicio de administración de IIS cuando ejecutó el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Asistente para configuración.  
  
### <a name="solution"></a>Solución  
 Para completar correctamente el proceso de configuración, haga lo siguiente:  
  
1. Cerrar la [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] consola de configuración.  
  
2. Reinicie el servicio de administración IIS.  
  
3. Ejecutar *% programfiles %* \Microsoft BizTalk Accelerator para SWIFT\Configuration.exe.  
  
4. En el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] consola de configuración, seleccione **desconfigurar características** y, a continuación, seleccione **WebService**.  
  
5. Asegúrese de que el estado de la característica de servicio Web en la consola de configuración se muestra como no configurada.  
  
6. Seleccione **aplicar configuración**.  
  
   > [!NOTE]
   >  El Asistente para configuración de A4SWIFT va a configurar la característica de servicio Web correctamente.  
  
## <a name="a4swift-configuration-will-fail-if-the-biztalkserverapplication-host-was-not-created-in-biztalk-server-configuration"></a>Configuración de A4SWIFT se producirá un error si no se creó el host BizTalkServerApplication en configuración de BizTalk Server  
  
### <a name="symptom"></a>Síntoma  
 El [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Asistente para configuración no configura la característica de servicio Web correctamente. Recibe el error siguiente:  
  
 "No se puede crear artefactos MRSR: referencia a objeto no establecida para una instancia de un objeto."  
  
### <a name="possible-cause"></a>Causa posible  
 Un Host In-Process y una instancia de Host no se crearon durante la configuración de tiempo de ejecución de BizTalk Server.  
  
### <a name="solution"></a>Solución  
 Para reparar la configuración de A4SWIFT, haga lo siguiente:  
  
- Crear un host de administración de BizTalk Server. No hay ninguna necesidad de tener ahora una instancia en ejecución.  
  
- Ejecute la herramienta RepairBAS en el *% programfiles %* \Microsoft BizTalk Accelerator for SWIFT\SDK\Tools carpeta de la instalación de A4SWIFT.  
  
  Para ello, haga lo siguiente:  
  
1.  Iniciar **administración de BizTalk Server** consola.  
  
2.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, a continuación, expanda **grupo de BizTalk**y, a continuación, expanda **configuración de plataforma.**  
  
3.  Haga clic en **Hosts**, apunte a **New**y, a continuación, seleccione **Host**.  
  
4.  En la pantalla de propiedades de Host, en el panel General, escriba lo siguiente:  
  
    -   Nombre de host: **BizTalkServerApplication**  
  
    -   Tipo: **en curso**  
  
    -   Grupo de Windows:  **\< *dominio*\>\BizTalk usuarios de la aplicación** (o la cuenta que configuró durante la configuración de BizTalk Server para ejecutar In-Process de BizTalk aplicaciones)  
  
    -   En la sección Opciones, seleccione ambos **Permitir seguimiento de Host** y **establecer este host como predeterminado en el grupo**.  
  
5.  Haga clic en **Aceptar**.  
  
6.  Haga clic en **iniciar** y, a continuación, haga clic en ejecutar. Tipo **cmd** y, a continuación, haga clic en **Aceptar**.  
  
7.  En el símbolo del sistema, vaya a * % programfiles % ***\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools**.  
  
8.  Tipo **RepairBAS.exe** y, a continuación, presione **ENTRAR**.  
  
## <a name="you-must-change-the-bre-deployment-configuration-file-when-running-the-bre-deployment-utility-on-a-64-bit-computer"></a>Debe cambiar el archivo de configuración de implementación de BRE cuando ejecute la utilidad de implementación de BRE en un equipo de 64 bits  
  
### <a name="symptom"></a>Síntoma  
 La utilidad de implementación de BRE no funciona correctamente cuando se ejecuta en un equipo de 64 bits o en un directorio no predeterminado (que no sea C:\Program Files\Microsoft BizTalk Accelerator para SWIFT) en un equipo de 32 bits.  
  
### <a name="possible-cause"></a>Causa posible  
 La utilidad de implementación de BRE no funcionará correctamente hasta que cambie las rutas de acceso del archivo bredeployment.exe.config que se encuentra en la \<unidad\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools carpeta.  
  
### <a name="solution"></a>Solución  
 Actualizar configuración de la utilidad abriendo BREDeployment.exe.config en el Bloc de notas, y cambiar las carpetas para las directivas de bases, esquemas y los directorios de vocabulario.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas: problemas y soluciones](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)