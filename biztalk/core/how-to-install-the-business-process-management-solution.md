---
title: Cómo instalar la solución de administración de procesos empresariales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, examples
- process management solution tutorial, installing
- process management solution tutorial, deployment prerequisites
ms.assetid: 930f3bb1-05e6-4b02-852d-6139aaf341f0
caps.latest.revision: 61
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb067c206018996bc48641bcd8211921b0294dd
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752525"
---
# <a name="how-to-install-the-business-process-management-solution"></a>Cómo instalar la solución de administración de procesos empresariales
Los pasos siguientes describen cómo preparar el equipo para instalar la solución Administración de procesos empresariales (BPM) y cómo realizar la instalación.  
  
-   [Preparar el equipo para instalar la solución de administración de procesos empresariales](#step1)  
  
     En la fase de preparación, se crean las carpetas, las colas y la base de datos SQL que utilizarán los puertos de envío y recepción. También se crean los dos directorios virtuales para la aplicación cliente, CSRWebApp y el servicio Web de proxy OrderBroker.  
  
-   [Configurar el equipo para instalar la solución de administración de procesos empresariales](#step3)  
  
-   [Instalar la solución de administración de procesos empresariales](#step5)  
  
> [!NOTE]
>  Ejecutará algunos archivos por lotes para implementar la solución. Se recomienda redirigir el resultado de los archivos de procesamiento por lotes a un archivo de texto para comprobar que la secuencia de comandos se ha completado correctamente.  
  
##  <a name="step1"></a> Preparar el equipo para instalar la solución de administración de procesos empresariales  
  
#### <a name="to-prepare-the-computer-for-installing-the-business-process-management-solution"></a>Para preparar el equipo para instalar la solución de administración de procesos empresariales  
  
1.  Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **herramientas administrativas**y, a continuación, haga clic en **servicios**. Mediante el **servicios** de consola, asegúrese de que se están ejecutando los siguientes servicios:  
  
    -   **Publicación FTP**  
  
    -   **Message Queue Server**  
  
    -   **Publicación en World Wide Web**  
  
2.  Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **herramientas administrativas**, haga clic en **administración de equipos** de consola y, a continuación, agregue el Cuenta de servicio de BizTalk al grupo de administradores local.  
  
3.  Si ha instalado Windows SharePoint Services, excluya (raíz) de la **sitio Web predeterminado** desde Windows SharePoint Services rutas de acceso administradas como sigue: haga clic en **iniciar**, apunte a **todos los programas** , apunte a **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint**.  
  
    1.  En **configuración del servidor Virtual**, seleccione **configurar servidor virtual**.  
  
    2.  En el **lista de servidores virtuales** página, haga clic en **sitio Web predeterminado**.  
  
    3.  En el **configuración del servidor Virtual** página, haga clic en **definir rutas administradas**.  
  
    4.  En el **rutas incluidas** sección de la **definir rutas administradas** página, seleccione **raíz** y, a continuación, haga clic en **quitar rutas seleccionadas**.  
  
    5.  En el símbolo del sistema, ejecute IISReset.  
  
##  <a name="step3"></a> Configurar el equipo para instalar la solución de administración de procesos empresariales  
  
#### <a name="to-configure-the-computer-for-installing-the-business-process-management-solution"></a>Para configurar el equipo para instalar la solución de administración de procesos empresariales  
  
1.  Cierre la sesión y, a continuación, inicie una sesión en el equipo con la cuenta de servicio de BizTalk.  
  
2.  Abra un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR para establecer la variable de entorno %BTSSolutionsPath% e indicar la carpeta base para las soluciones B2B. A continuación, cierre el símbolo del sistema.  
  
    -   `setx BTSSolutionsPath "%ProgramFiles%\Microsoft BizTalk Server 2009\SDK\Scenarios"`  
  
        > [!NOTE]
        >  Si está utilizando un equipo de 64 bits, escriba %ProgramFiles(x86)% en lugar de %ProgramFiles%.  
  
        > [!NOTE]
        >  Para obtener más información acerca del comando SETX, vea el sitio Web de Microsoft TechNet en [ http://go.microsoft.com/fwlink/?LinkId=67831 ](http://go.microsoft.com/fwlink/?LinkId=67831).  
  
3.  Abra un símbolo del sistema, cambie el directorio actual a la carpeta %BTSSolutionsPath%\BPM\HistoryDB, escriba `CreateDatabase.cmd`, y presione ENTRAR para crear la base de datos de historial.  
  
    > [!NOTE]
    >  El usuario que ejecuta el host especificado como controlador para el adaptador de envío SQL debe tener permisos para ejecutar procedimientos almacenados en la base de datos SouthridgeVideoHistory.  
  
4.  En un símbolo del sistema, ejecute el comando siguiente para cambiar el host predeterminado de secuencias de comandos a CScript.exe  
  
    -   `CScript /H:CScript`  
  
5.  En un símbolo del sistema, ejecute el comando siguiente para crear la aplicación Web CSRWebApp.  
  
    -   `iisvdir /create "Default Web Site" CSRWebApp "%BTSSolutionsPath%\BPM\CSRWebApp"`  
  
        > [!NOTE]
        >  Para obtener más información acerca de iisvdir.vbs, vea el sitio Web de Microsoft TechNet en [ http://go.microsoft.com/fwlink/?LinkId=67830 ](http://go.microsoft.com/fwlink/?LinkId=67830).  
  
6.  En un símbolo del sistema, ejecute el comando siguiente para crear un nuevo directorio virtual de IIS para OrderBroker_Proxy.  
  
    -   `iisvdir /create "Default Web Site" BTSScn.BPM.OrderBroker_Proxy "%BTSSolutionsPath%\BPM\OrderBroker_Proxy"`  
  
    > [!NOTE]
    >  Puede usar el Administrador de Internet Information Services (IIS) para crear la aplicación web. Para obtener más información sobre cómo crear aplicaciones en IIS 7.0, vea la documentación de IIS 7.0 en [ http://go.microsoft.com/fwlink/?LinkId=59263 ](http://go.microsoft.com/fwlink/?LinkId=59263).  
  
7.  Cree un nuevo grupo de aplicaciones de IIS y configure su identidad como usuario miembro de los grupos Usuarios de hosts aislados de BizTalk y IIS_WPG como se muestra a continuación:  
  
    1.  En el Administrador de Internet Information Services (IIS), haga clic en **grupos de aplicaciones**, seleccione **New**y, a continuación, seleccione **AppPool**.  
  
    2.  Tipo de la **Id. de grupo de aplicación** (cualquier valor) y, a continuación, haga clic en **Aceptar**.  
  
    3.  Haga clic en el grupo de aplicaciones que ha creado y, a continuación, seleccione **configuración avanzada**.  
  
    4.  Expanda **modelo de proceso**, haga clic en la columna derecha de la **identidad** establecer y, a continuación, haga clic en **...**  
  
    5.  Seleccione una cuenta de usuario (ya sea un **cuenta integrada** o **cuenta personalizada** ) que tiene permisos para crear y ejecutar archivos en el directorio Windows\Temp. Al configurar BizTalk, el proceso de configuración ya estableció estos permisos para el usuario que agregó al grupo fue a agregar al grupo Usuarios de hosts aislados de BizTalk. Especificar el mismo usuario es una buena elección.  
  
8.  En el Administrador de Internet Information Services (IIS), expanda **sitios Web**, expanda **sitio Web predeterminado**, haga clic en **BTSScn.BPM.OrderBroker_Proxy**, apunte a **Administrar aplicación**y, a continuación, haga clic en **configuración avanzada**.  
  
9. Establecer **AppPool** al grupo de aplicaciones que ha creado en el paso anterior.  
  
10. Repita los dos pasos anteriores para el **CSRWebApp** aplicación.  
  
11. Restablezca IIS para asegurarse de que todos estos cambios surten efecto inmediatamente. Para ello, ejecute **iisreset** en un símbolo del sistema.  
  
12. En un símbolo del sistema, cambie la carpeta actual a % BTSSolutionsPath%\BPM\Scripts, escriba `CreateQueues.vbs`, y, a continuación, presione ENTRAR para crear las colas privadas siguientes.  
  
    |Nombre|Transaccional|Protocolo de transacciones|  
    |----------|-------------------|--------------------------|  
    |ToFacilitiesQ|Sí|Nativa|  
    |FromFacilitiesQ|Sí|Nativa|  
    |FromFixedOrdersQ|Sí|Nativa|  
    |ToServicingSystemQ|Sí|Nativa|  
    |ToCSRSystemQ|no|HTTP|  
    |ToVendorSystemQ|no|HTTP|  
  
    > [!NOTE]
    >  Puede usar **administración de equipos** complemento para crear las colas. Para obtener más información sobre cómo crear una cola privada, consulte la documentación de Message Queue Server en [ http://go.microsoft.com/fwlink/?LinkId=59264 ](http://go.microsoft.com/fwlink/?LinkId=59264). Para obtener más información sobre cómo instalar MSMQ 3.0, consulte la documentación de Message Queue Server en [ http://go.microsoft.com/fwlink/?LinkId=59265 ](http://go.microsoft.com/fwlink/?LinkId=59265).  
  
13. En un símbolo del sistema, cambie la carpeta actual a % BTSSolutionsPath%\BPM\Scripts, escriba `CreateTestDirectories.cmd`, y, a continuación, presione ENTRAR.  
  
    -   En la carpeta %SystemDrive%\BPMTest, se crean las carpetas siguientes:  
  
         CSRResponse-DSP  
  
         VendorResponse-DSP  
  
         OrderErrors-SP  
  
         ErrorResponse-RP-TestRL  
  
         Facilities-SP  
  
         Facilities-RP-TestRL  
  
         HistoryInsert-SP  
  
         HistoryUpdate-SP  
  
         Order-RP-TestRL  
  
         ServicingSystem-SP  
  
         Vendor-RP-TestRL  
  
         BizTalkErrors-SP  
  
    -   La carpeta FromVendor se crea en la carpeta %SystemDrive%\Inetpub\ftproot.  
  
        > [!NOTE]
        >  Si el sistema Windows no está instalado en la unidad C, debería sustituir %SystemDrive% por C:. Los nombres de las carpetas tienen que coincidir con la dirección de los archivos de enlace que proporciona la solución BPM.  
  
        > [!NOTE]
        >  La cuenta de servicio de BizTalk debe tener permiso de lectura/escritura en la carpeta FromVendor.  
  
##  <a name="step5"></a> Instalar la solución de administración de procesos empresariales  
  
#### <a name="to-install-the-business-process-management-solution"></a>Para instalar la solución de administración de procesos empresariales  
  
1. En un símbolo del sistema, cambie la carpeta actual a % BTSSolutionsPath%\BPM, escriba `SetupBPM.bat`, y, a continuación, presione ENTRAR.  
  
   > [!NOTE]
   >  Antes de ejecutar SetupBPM.bat, en los archivos **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.WSDL** y **%BTSInstallPath%/SDK/ Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**, reemplace todas las instancias de 8f8bbebbb3fb375a por XXXXXXXXXXXXXXXX.  
  
    El archivo SetupBPM.bat realiza las tareas siguientes:  
  
   1.  Crea una clave de nombre seguro único (SNK) para firmar los ensamblados de la solución BPM  
  
   2.  Extrae el símbolo de clave pública del SNK.  
  
   3.  Actualiza los archivos de enlace con el símbolo público.  
  
   4.  Genera la solución BPM e instala OpsAdapter.  
  
   5.  Genera SSOApplicationConfig en la carpeta %BTSSolutionsPath%\Common.  
  
2. Implementar reglas de negocios de Southridge Video utilizando el Asistente para implementar el motor de reglas de negocios.  
  
   1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Asistente para implementación de motor de reglas de negocios**.  
  
      > [!NOTE]
      >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
   2. En el **bienvenida** página, haga clic en **siguiente**.  
  
   3. En el **tarea de implementación** página, seleccione **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, haga clic en **siguiente**.  
  
   4. En el **directiva Store** página, mantenga todos los demás valores predeterminados y, a continuación, haga clic en **siguiente**.  
  
   5. En el **archivo de directiva o vocabulario del motor de reglas importación** página, haga clic en **examinar**, seleccione el archivo DecodeAndValidateOrderRules.xml en la carpeta %BTSSolutionsPath%\BPM\Rules y, a continuación, haga clic en **Siguiente**.  
  
   6. En el **listo** página, haga clic en **siguiente**y, a continuación, en el **Importando directiva o vocabulario** página, haga clic en **siguiente**  
  
   7. En la página Finalización, seleccione **vuelva a ejecutar el asistente** para abrir el Asistente para nuevo y, a continuación, haga clic en **finalizar**.  
  
   8. En el **bienvenida** página, haga clic en **siguiente**.  
  
   9. En el **tarea de implementación** página, seleccione **directiva de implementación**y, a continuación, haga clic en **siguiente**.  
  
   10. En el **directiva Store** página, mantenga todos los demás valores predeterminados y, a continuación, haga clic en **siguiente**.  
  
   11. En el **implementar Directiva** página, seleccione **DecodeAndValidateOrder 1.0** en el **directiva del motor de reglas** lista desplegable y, a continuación, haga clic en **siguiente** .  
  
   12. En el **listo** página, haga clic en **siguiente**y, a continuación, en el **implementando directiva** página, haga clic en **siguiente**.  
  
   13. En la página Finalización, haga clic en **finalizar**.  
  
3. Si instala la solución BPM en un equipo de 64 bits, a continuación  
  
   1.  Abra un símbolo del sistema de 32 bits como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `%SYSTEMROOT%\SYSWOW64\CMD.EXE`, y, a continuación, presione ENTRAR.  
  
   2.  En un símbolo de sistema de 32 bits, cambie el directorio a la carpeta %BTSSolutionsPath%\BPM\Scripts.  
  
   3.  Abra CreateSouthridgeVideoApplication.cmd con el Bloc de notas y, a continuación, sustituya "%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe" por "%SystemDrive%\Archivos de programa\Archivos comunes\Enterprise Single Sign-On\ssomanage.exe".  
  
       > [!NOTE]
       >  En un símbolo de sistema de 32 bits, cambie la variable %CommonProgramFiles% a "%ProgramFiles(x86)%\Common Files". Como la utilidad administrativa SSO está instalada en %ProgramFiles%, incluso en los equipos de 64 bits, deberá corregir la ruta. DeployBPM.cmd llama a CreateSouthridgeVideoApplication.cmd.  
  
   4.  En el símbolo del sistema de 32 bits, escriba `DeployBPM.cmd`, y, a continuación, presione ENTRAR.  
  
       > [!NOTE]
       >  DeployBPM.cmd debe ejecutarse en un símbolo de sistema de 32 bits porque incluye objetos x86 de acceso a VBScript que requieren la versión x86 de cscript.exe.  
  
4. En un símbolo del sistema, cambie la carpeta actual a % BTSSolutionsPath%\BPM\Scripts, escriba `DeployBPM.cmd`, y, a continuación, presione ENTRAR. DeployBPM.cmd realiza las tareas siguientes:  
  
   1.  Crea aplicaciones de BizTalk para la solución BPM.  
  
   2.  Agrega referencias entre las aplicaciones.  
  
   3.  Importa los archivos de enlace.  
  
   4.  Implementa los archivos de definición BAM.  
  
   5.  Registra el origen de eventos de SouthridgeVideo.  
  
   6.  Crea una aplicación afiliada de inicio de sesión único y guarda los valores de configuración en la aplicación SSO.  
  
5. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
   1.  En el **consola de administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BTSScn.BPM.OrderBrokerApp**, expanda **ubicaciones de recepción**, haga clic en **Vendor-RP-RL**y, a continuación, haga clic en Propiedades.  
  
   2.  En el **propiedades** cuadro de diálogo, haga clic en **configurar**y, a continuación, escriba los valores como en la tabla siguiente el **propiedades de transporte** cuadro de diálogo:  
  
       |Nombre de propiedad|Valor|  
       |-------------------|-----------|  
       |**Server**|`localhost`|  
       |**Nombre de usuario**|\<*Nombre de cuenta de servicio de BizTalk*\>|  
       |**Contraseña**|\<*Contraseña de cuenta de servicio de BizTalk*\>|  
  
6. Ejecute la solución BPM Para obtener más información sobre la ejecución de la solución, vea [cómo ejecutar la solución de administración de procesos empresariales](../core/how-to-run-the-business-process-management-solution.md).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Compruebe cómo funciona la solución de administración empresarial [cómo ejecutar la solución de administración de procesos empresariales](../core/how-to-run-the-business-process-management-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Antes de instalar la solución de administración de procesos empresariales](../core/before-installing-the-business-process-management-solution.md)   
 [Configurar el equipo del desarrollador para la solución de administración de procesos empresariales](../core/developer-machine-setup-for-the-business-process-management-solution.md)
