---
title: "Instalar el en línea y las versiones de adaptador del servicio en la solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6050cfe9-4e94-4a55-8b24-fbcc74d9e8f4
caps.latest.revision: "97"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbf374b4efb219f1221275819713787565a325b0
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution"></a>Cómo instalar las versiones de adaptador y en línea de la solución orientada a servicios
Los pasos siguientes describen cómo preparar el equipo para instalar las versiones de adaptador y en línea de la solución orientada a servicios y cómo realizar la instalación en el mismo.  
  
> [!NOTE]
>  - El servicio en la solución orientada a servicios se encuentra en la carpeta \< *carpeta de instalación de BizTalk Server*> \SDK\Scenarios\SO.  
>  - Si la solución no requiere un gran sistema, puede modificar el enlace de puertos para utilizar el servicio Web de código auxiliar para las transacciones pendientes. El servicio Web genera transacciones localmente para emular las transacciones de gran sistema.  
  
##  <a name="step1"></a>Preparar el equipo para instalar las versiones de adaptador y en línea de la solución orientada a servicios  
  
1.  Si ha instalado Windows SharePoint Services, excluya (raíz) del sitio Web predeterminado de rutas administradas de Windows SharePoint Services como sigue: haga clic en **iniciar**, seleccione **todos los programas**, seleccione  **Herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint**.  
  
    1.  En **configuración del servidor Virtual**, seleccione **configurar el servidor virtual**.  
  
    2.  En el **lista de servidores virtuales** página, haga clic en **sitio Web predeterminado**.  
  
    3.  En el **configuración del servidor Virtual** página, haga clic en **definir rutas administradas**.  
  
    4.  En el **rutas incluidas** sección de la **definir rutas administradas** página, seleccione **raíz** y, a continuación, haga clic en **quitar rutas seleccionadas**.  
  
    5.  En el símbolo del sistema, ejecute IISReset.  
  
2.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**, haga clic en **administración de equipos** consola y, a continuación, agregue el Cuenta de servicio de BizTalk al grupo de administradores local.  
  
3.  Cierre la sesión y, a continuación, inicie una sesión en el equipo con la cuenta de servicio de BizTalk.  
  
4.  En un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR para establecer la variable de entorno %BTSSolutionsPath%. A continuación, cierre el símbolo del sistema.  
  
    -   setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  
  
        > [!NOTE]
        >  Si está utilizando un equipo de 64 bits, escriba %ProgramFiles(x86)% en lugar de %ProgramFiles%.  
  
        > [!NOTE]
        >  Para obtener más información acerca del comando SETX, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).  
  
##  <a name="step3"></a>Quite la versión de código auxiliar de la solución orientada a servicios  
  
1.  Abra la **consola de administración de BizTalk Server** como se indica a continuación: haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en  **Administración de BizTalk Server**.  
  
2.  En el **consola de administración de BizTalk Server**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, haga clic en **BTSScn.SO.CustomerService**y, a continuación, haga clic en **detener**. En el **detener aplicación** cuadro de diálogo, seleccione **detención completa: finalizar instancias**y, a continuación, haga clic en **detener**.  
  
    > [!NOTE]
    >  No tiene que quitar la versión de código auxiliar para instalar las versiones de adaptador y en línea. Si desea colocar todas las versiones juntas, debería omitir este paso.  
  
3.  Abra un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR: Este comando cambia el host predeterminado de secuencias de comandos a CScript.exe:  
  
    -   `cscript /H:CScript`  
  
4.  En el símbolo del sistema, cambie el directorio actual a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, escriba el comando siguiente y, a continuación, presione ENTRAR:  
  
    -   `UnEnlistStub.vbs`  
  
5.  En el símbolo del sistema, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
    -   `UndeployStub.vbs`  
  
6.  En el símbolo del sistema, ejecute el siguiente comando:  
  
     SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"  
  
     De este modo, se configurará la ruta para buscar las utilidades de SAE.  
  
    > [!NOTE]
    >  Si está utilizando un equipo de 64 bits, escriba `%ProgramFiles(x86)%` en lugar de `%ProgramFiles%`.  
  
7.  En el símbolo del sistema, cambie el directorio a %BTSSolutionsPath%\SO\BTSSoln\BAM y, a continuación, ejecute el comando siguiente:  
  
    -   `bm remove-all -DefinitionFile:ServiceLevelTracking.xml`  
  
8.  En el símbolo del sistema, cambie al directorio \< *Enterprise Single Sign-On directorio de instalación*>, y, a continuación, ejecute el siguiente comando:  
  
    -   `ssomanage -tickets no no`  
  
9. En el símbolo del sistema, ejecute el comando siguiente para eliminar la aplicación afiliada de SSO WoodgroveBank.CustomerService:  
  
    -   `ssomanage -deleteapp WoodgroveBank.CustomerService`  
  
10. En el símbolo del sistema, ejecute los comandos siguientes para eliminar los sitios Web que utiliza la versión de código auxiliar. Para obtener más información acerca de iisvdir.vbs, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker`  
  
11. Iniciar el Administrador de Internet Information Services (IIS) como sigue: haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas de administración**y, a continuación, haga clic en **De Internet Information Services (IIS) Manager**.  
  
    -   Expanda el **grupos de aplicaciones**, haga clic en el grupo de aplicaciones que creó para las aplicaciones Web anteriores, haga clic en **eliminar**y, a continuación, haga clic en **Aceptar** en la confirmación cuadro de diálogo.  
  
12. Haga clic en **iniciar**, seleccione **el Panel de Control**, haga clic en **agregar o quitar programas**y, a continuación, desinstalar el cliente IBM WebSphere MQ para Windows.  
  
13. Iniciar **Visual Studio Command Prompt** y, a continuación, ejecute el siguiente comando para eliminar el archivo amqmdnet.dll que instaló para la versión de código auxiliar.  
  
    -   `gacutil /u amqmdnet`  
  
##  <a name="step5"></a>Preparar los sistemas back-end para la solución orientada a servicios tener acceso a  
  
1.  Instalar IBM WebSphere MQ para Windows Server en el equipo local.  
  
    1.  Mantenga todos los valores de configuración predeterminados. Configurar la **configuración predeterminada** al final de la **Prepare WebSphere MQ Wizard**. El Administrador de cola se denomina QM_\<*el nombre del equipo*>.  
  
    2.  Instale Fix Pack10 (CSD10). Mantenga todos los valores de configuración predeterminados.  
  
2.  Instale MQSeries Agent.  
  
    1.  Vuelva a ejecutar el programa de instalación de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
    2.  En el **mantenimiento del programa** página, seleccione **modificar**y, a continuación, haga clic en **siguiente**.  
  
    3.  En el **instalación de componentes** página, expanda la **Software adicional** nodo y, a continuación, seleccione **MQSeries Agent**.  
  
    4.  En el **finalización** página, asegúrese de que **iniciar de Asistente de configuración de BizTalk MQSeries Agent** no está seleccionada.  
  
    > [!NOTE]
    >  El **MQSeries Agent** casilla se activa después de IBM WebSphere MQ para Windows está instalado.  
  
3.  Abra un **Visual Studio Command Prompt**, cambie el directorio a la \< *directorio de instalación de MQSeries de IBM*> carpeta \bin y, a continuación, ejecute el comando siguiente:  
  
    -   `gacutil /i amqmdnet.dll`  
  
4.  Instale Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] si desea instalar Microsoft Host Integration Server 2004 para obtener acceso al gran sistema (mainframe). En el programa de instalación en el **opciones** página, seleccione **Visual C# .NET**y, a continuación, desactive las casillas de verificación de otros componentes. No es necesario instalar otros componentes de la **Visual C# .NET**.  
  
    > [!NOTE]
    >  TI Designer de Host Integration Server 2004 requiere [!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)].  
  
5.  Instale y configure Microsoft Host Integration Server 2004 si tiene que obtener acceso a un gran sistema. Mantenga todos los valores de configuración predeterminados.  
  
#### <a name="create-the-mqseries-queues"></a>Crear las colas de MQSeries  
  
1.  Abra WebSphere MQ Explorer, expanda **administradores de cola**y, a continuación, expanda el Administrador de cola en el que desea crear las colas. Normalmente, un administrador de cola se denomina QM_\<*el nombre del equipo*>.  
  
2.  En WebSphere MQ Explorer, haga clic en **colas**, seleccione **New**, haga clic en **cola Local**y, a continuación, crear las colas locales siguientes para la versión del adaptador de la solución:  
  
    -   AdapterSOAInputQueue  
  
    -   AdapterSOAOutputQueue  
  
    > [!NOTE]
    >  Aunque no es necesario, las colas pueden compartir un clúster de MQSeries.  
  
    > [!NOTE]
    >  Los nombres administradores de cola MQSeries y los nombres de cola distinguen mayúsculas de minúsculas.  
  
3.  Repita el paso anterior para crear las colas locales siguientes para la versión en línea:  
  
    -   InlineSOAOutputQueue  
  
    -   InlineSOAInputQueue  
  
4.  Repita el paso anterior para crear las colas locales siguientes para el simulador de seguimiento de pago (el simulador de seguimiento de pago se utiliza tanto en la versión de adaptador como en la versión en línea):  
  
    -   LastPaymentsInputQueue  
  
    -   LastPaymentsOutputQueue  
  
#### <a name="complete-configuration-of-the-mqseries-adapter"></a>Completar la configuración del adaptador de MQSeries  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **el Asistente para la configuración de BizTalk MQSeries Agent**.  
  
2.  En el **bienvenida** página, haga clic en **siguiente**.  
  
3.  En el **identidad de aplicación** página, seleccione **este usuario**y, a continuación, escriba el nombre de usuario y la contraseña. La aplicación COM+ de MQSeries Agent se ejecutará bajo esta cuenta de usuario. Para este tutorial, use la misma cuenta de usuario que está utilizando el servicio de BizTalk. Si no lo es, las cuentas de usuario para servicios de BizTalk que aloja el adaptador de MQSeries deben agregarse a la **CreatorOwner** rol de la aplicación COM +.  
  
4.  Haga clic en **Sí** en el **MQSConfigWiz** cuadro de diálogo, si se le solicita que la cuenta de usuario que escribió en el paso anterior tiene privilegio administrativo.  
  
5.  En el **nombre de la función** página, haga clic en **siguiente**.  
  
6.  En el **crear el MQSAgent COM + Application** página, haga clic en **siguiente**y, a continuación, haga clic en **finalizar** en el **finalización** página.  
  
#### <a name="configure-the-mainframe-cics-application"></a>Configurar la aplicación CICS de gran sistema  
  
1.  En la carpeta %BTSSolutionsPath%\SO\MFAccess\HISTIComponent, abra el archivo bizcbl.txt y su "libro de copia" (MainFrameProgramVTCS2Description.txt) con el Bloc de notas y, a continuación, revise su contenido.  
  
    -   Bizcbl.txt incluye el procedimiento COBOL para devolver las instrucciones aleatorias de la cuenta a partir de la entrada de números en la misma.  
  
    -   MainFrameProgramVTCS2Descriptoin.txt contiene COMMAREA, que describe la información de los datos de entrada y salida. COMMAREA es un bloque de memoria contigua que se utiliza para pasar datos entre los programas llamados y los que realizan las llamadas (en ambas direcciones).  
  
    > [!NOTE]
    >  También puede usar el libro de copia para generar el archivo de metadatos de Transaction Integrator (TI) con el complemento TI Designer en Visual Studio.  
  
    > [!NOTE]
    >  Aunque los pasos siguientes son fundamentales para realizar una implementación correcta, no suele llevarlos a cabo el programador de BizTalk Server. El éxito de la implementación depende de que el personal del gran sistema configure el entorno mainframe correctamente. El software necesario para realizar este tutorial suele estar instalado en la mayoría de los entornos de gran sistema. Para obtener más información acerca del entorno de sistema operativo mínimo de gran sistema, consulte la documentación de Host Integration Server.  
  
2.  Copie el código COBOL en el host mediante FTP o utilizando un método similar.  
  
3.  Compile el código COBOL y el libro de copia. En el código siguiente, se muestra un ejemplo del lenguaje de control de tareas (JCL) del compilador COBOL.  
  
    ```  
    //COB      EXEC PGM=IGYCRCTL,  
    //            PARM=&COBPARM,  
    //            REGION=&REG  
    //STEPLIB  DD DSN=&COMPINDX..SIGYCOMP,DISP=SHR  
    //SYSLIB   DD DSN=&INDEX..SDFHCOB,DISP=SHR  
    //         DD DSN=&INDEX..SDFHMAC,DISP=SHR  
    //         DD DSN=&HLQ..&COMP..COBCOPY,DISP=SHR  
    //SYSPRINT DD SYSOUT=&OUTC  
    //*SYSPRINT DD DSN=&&INPUT,DISP=(,PASS),UNIT=SYSDA,  
    //*         SPACE=(TRK,(100,50)),  
    //*         DCB=(DSORG=PS,LRECL=121,BLKSIZE=2420,RECFM=FBA)  
    //SYSIN    DD DSN=&&SYSCIN,DISP=(OLD,DELETE)  
    //SYSLIN   DD DSN=&&LOADSET,  
    //            DISP=(MOD,PASS),  
    //            UNIT=&WORK,  
    //            SPACE=(80,(250,100))  
    //SYSUT1   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT2   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT3   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT4   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT5   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT6   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT7   DD UNIT=&WORK,SPACE=(460,(350,150))  
    ```  
  
4.  Edite el vínculo con el código fuente compilado para crear un archivo ejecutable. El código siguiente muestra un ejemplo de JCL para la edición de un vínculo de COBOL.  
  
    ```  
    //LKED     EXEC PGM=IEWL,REGION=&REG,  
    //            PARM=&LNKPARM,COND=(5,LT,COB)  
    //SYSLIB   DD DSN=&INDEX..SDFHLOAD,DISP=SHR  
    //         DD DSN=CEE.SCEELKED,DISP=SHR  
    //         DD DSN=&TCPINDX..SEZATCP,DISP=SHR  
    //SYSLMOD  DD DSN=&LMINDX..&COMP..LOADLIB,DISP=SHR  
    //SYSUT1   DD UNIT=&WORK,  
    //            DCB=BLKSIZE=1024,  
    //            SPACE=(1024,(200,20))  
    //SYSPRINT DD SYSOUT=&OUTC  
    //SYSLIN   DD DSN=&&LOADSET,DISP=(OLD,DELETE)  
    //         DD DSN=&&COPYLINK,DISP=(OLD,DELETE)  
    ```  
  
5.  Configure la aplicación CICS de gran sistema.  
  
    -   En este paso, el programador de grandes sistemas o el programador de CICS debe instalar las definiciones de recurso de Servicio TCP/IP, Sesión, Conexión, Transacción y Programa.  
  
    -   Para obtener una dirección IP, un número de puerto y un vínculo al programa al que puede tener acceso, vea con los administradores del gran sistema.  
  
        > [!NOTE]
        >  Este tutorial supone que el gran sistema utiliza un servidor de aplicaciones CICS y que el modelo de programación de la transacción es TCP/IP (vínculo Modo de escucha mejorado [ELM]).  
  
##  <a name="step7"></a>Configurar el servidor Web para las capas de sockets seguros (SSL)  
  
#### <a name="install-certificate-services"></a>Instalar servicios de Certificate Server  
  
1.  Haga clic en **iniciar**, seleccione **el Panel de Control**y, a continuación, haga clic en **agregar o quitar programas**.  
  
2.  En el **agregar o quitar programas** cuadro de diálogo, haga clic en **agregar o quitar componentes de Windows**.  
  
3.  En el **Asistente para componentes de Windows**, seleccione la **servicios de Certificate Server**, haga clic en **siguiente**y, a continuación, siga las que aparecen en pantalla instrucciones para completar la instalación.  
  
#### <a name="create-a-certificate-request"></a>Crear una solicitud de certificado  
  
1.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, haga clic en **propiedades** , haga clic en el **seguridad de directorios** ficha y, a continuación, haga clic en **certificado de servidor**.  
  
2.  En el **bienvenida** página de la **Asistente para certificados de servidor Web**, haga clic en **siguiente**.  
  
3.  En el **certificado de servicio** página, seleccione **crear un nuevo certificado**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **Petición demorada o inmediata** página, haga clic en **preparar la petición ahora pero enviarla más tarde**y, a continuación, haga clic en **siguiente**.  
  
5.  En el **nombre y la configuración de seguridad** página mantener todos los valores predeterminados y, a continuación, haga clic en **siguiente**.  
  
6.  En el **información de la organización** página, escriba el nombre de la unidad organizativa y organización de su empresa y, a continuación, haga clic en **siguiente**.  
  
7.  En el **nombre común de su sitio Web** página, escriba el nombre del equipo en el **nombre común** cuadro y, a continuación, haga clic en **siguiente**.  
  
8.  En el **información geográfica** página, rellene la información geográfica y, a continuación, haga clic en **siguiente**.  
  
9. En el **nombre de archivo de solicitud de certificado** página, escriba `c:\certreq.txt` en el **nombre de archivo** cuadro y, a continuación, haga clic en **siguiente**.  
  
10. En el **resumen del archivo de petición** página, haga clic en **siguiente**y, a continuación, haga clic en **finalizar** en el **finalización** página.  
  
#### <a name="submit-the-certificate-request-to-the-certification-authority"></a>Enviar la solicitud de certificado a la entidad de certificación  
  
1.  En Internet Explorer, en el cuadro Dirección, escriba `http://localhost/certsrvt`, y, a continuación, presione ENTRAR.  
  
2.  En el **bienvenida** página, haga clic en **solicitar un certificado**y, a continuación, haga clic en **solicitud de certificado avanzada** en el **solicitar un certificado** página.  
  
3.  En el **solicitud de certificado avanzada** página, haga clic en **enviar una solicitud de certificado mediante un base64 codificado archivo PKCS #10 o una solicitud de renovación mediante un archivo de PKCS #7 codificado en base64**.  
  
4.  Copiar todo el texto de la c:\certreq.txt que creó en el procedimiento "para crear una solicitud de certificado", péguelo en el **solicitud guardada** cuadro en el **enviar una solicitud de certificado o una solicitud de renovación** página y, a continuación, haga clic en **enviar**.  
  
#### <a name="issue-a-certificate-using-certification-authority-management-tool"></a>Emitir un certificado con la herramienta de administración de la entidad de certificación  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **entidad de certificación**.  
  
2.  En el **entidad de certificación** de la consola, expanda el nombre de la entidad de certificación, el **solicitud pendiente**, haga clic en la solicitud de certificado que envió en el paso anterior, punto para **todas las tareas**y, a continuación, haga clic en **problema**.  
  
3.  Cerrar la **entidad de certificación** consola.  
  
#### <a name="download-the-certificate-to-the-web-server"></a>Descargar el certificado en el servidor Web  
  
1.  En Internet Explorer, en el cuadro Dirección, escriba `http://localhost/certsrvt`, y, a continuación, presione ENTRAR.  
  
2.  En el **bienvenida** página, haga clic en **ver el estado de una solicitud de certificado pendiente**.  
  
3.  En el **ver el estado de una solicitud de certificado pendiente** página, haga clic en el certificado **solicitud** que creó en el procedimiento "para crear una solicitud de certificado".  
  
4.  En el **certificado emitido** , seleccione cualquiera de los esquemas de codificación y, a continuación, haga clic en **Descargar certificado**.  
  
5.  En el **advertencia de seguridad** cuadro de diálogo, haga clic en **guardar**y, a continuación, guarde el certificado como c:\certnew.cer.  
  
#### <a name="install-the-certificate-to-the-web-server"></a>Instale el certificado en el servidor Web  
  
1.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado** para la que se creó la solicitud de certificado y, a continuación, Haga clic en **propiedades**.  
  
2.  En el **propiedades** cuadro de diálogo, haga clic en el **seguridad de directorios** ficha y, a continuación, haga clic en **certificado de servidor**.  
  
3.  En el **bienvenida** página de la **Asistente para certificados de servidor Web**, haga clic en **siguiente**.  
  
4.  En el **solicitud de certificado pendiente** página, seleccione **procesar la petición pendiente e instalar el certificado**y, a continuación, haga clic en **siguiente**.  
  
5.  En el **procesar una solicitud pendiente** página, escriba `c:\certnew.cer` en el **ruta de acceso y nombre de archivo** cuadro de texto y, a continuación, haga clic en **siguiente**.  
  
6.  Haga clic en **siguiente** en el **puerto SSL** página, haga clic en **siguiente** en el **resumen del certificado** página y, a continuación, haga clic en **finalizar** en el **confirmación** página.  
  
    > [!NOTE]
    >  En este tutorial, no necesita instalar el certificado de servidor en el almacén de entidades emisoras de certificados raíz de confianza del equipo local, ya que tanto los Servicios de Certificate Server como el servidor Web están instalados en el mismo equipo.  
  
##  <a name="step9"></a>Crear los servicios Web para los sistemas back-end  
  
1.  En el **Internet Information Services (IIS) Manager**, haga clic en **grupos de aplicaciones**, seleccione **New**y, a continuación, seleccione **delgrupodeaplicaciones**.  
  
    > [!NOTE]
    >  La solución orientada a servicios obtiene acceso al gran sistema a través de este servicio Web.  
  
2.  En el **Agregar nuevo grupo de aplicaciones** diálogo cuadro, escriba la **Id. de grupo de aplicaciones** (cualquier valor) y, a continuación, haga clic en **Aceptar**.  
  
3.  En el **Internet Information Services (IIS) Manager**, haga clic en el grupo de aplicaciones recién creado y, a continuación, seleccione **propiedades**.  
  
4.  En el **propiedades** página, haga clic en el **identidad** ficha, seleccione **Configurable**, escriba la **nombre de usuario** y **contraseña** y, a continuación, haga clic en **Aceptar**. Para este tutorial, use la misma cuenta de usuario que está utilizando el servicio de BizTalk.  
  
#### <a name="create-the-pendingtransactions-web-service-for-runtime"></a>Crear el servicio Web de transacciones pendientes para el tiempo de ejecución  
  
1.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.  
  
     Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web SAP de código auxiliar:  
  
     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions  
  
     Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\MFAccess\PendingTransactions  
  
     Permisos de acceso = lectura, ejecución de scripts  
  
2.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions y, a continuación, haga clic en **propiedades**.  
  
    1.  En el **seguridad de directorios** , haga clic en **editar** modificar **autenticación y control de acceso**. Seleccione **la autenticación básica (la contraseña se envía en texto no cifrado)**y desactive las demás **de acceso de autenticación** casillas de verificación. Haga clic en **Aceptar** para cerrar el **métodos de autenticación** cuadro de diálogo.  
  
    2.  En el **seguridad de directorios** , haga clic en **editar** en el **una comunicación segura** cuadro del grupo y, a continuación, busque **Requerir canal seguro (SSL)**en la **comunicaciones seguras** cuadro de diálogo.  
  
    3.  En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** al grupo de aplicaciones que creó en el procedimiento "para crear un nuevo grupo de aplicaciones de IIS para los servicios Web de transacciones pendientes".  
  
#### <a name="create-the-pendingtransactions-web-service-for-development-environment"></a>Crear el servicio Web de transacciones pendientes para el entorno de desarrollo  
  
1.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.  
  
     Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web SAP de código auxiliar:  
  
     Alias = PendingTransactions  
  
     Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\MFAccess\PendingTransactions  
  
     Permisos de acceso = lectura, ejecución de scripts  
  
2.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en PendingTransactions y, a continuación, haga clic en **Propiedades**.  
  
    1.  En el **seguridad de directorios** , haga clic en **editar** modificar **autenticación y control de acceso**. Seleccione **habilitar el acceso anónimo**. Haga clic en **Aceptar** para salir.  
  
        > [!NOTE]
        >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] usará la aplicación Web PendingTransactions para el entorno de desarrollo. Esta aplicación Web no es necesaria para un entorno de producción.  
  
    2.  En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** al grupo de aplicaciones que creó en el procedimiento "para crear un nuevo grupo de aplicaciones de IIS para los servicios Web de transacciones pendientes".  
  
#### <a name="create-the-stub-sap-web-service"></a>Crear el servicio Web SAP de código auxiliar  
  
1.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.  
  
     Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web SAP de código auxiliar:  
  
     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  
  
     Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  
  
     Permisos de acceso = lectura, ejecución de scripts  
  
2.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:  
  
    1.  En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que creó en el procedimiento "para crear una nueva aplicación IIS grupo para los servicios Web de transacciones pendientes".  
  
    2.  En el **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**. Haga clic en **Aceptar** para salir.  
  
##  <a name="step11"></a>Crear el componente TI para la solución orientada a servicios  
  
#### <a name="create-a-com-application-for-the-ti-component"></a>Crear una aplicación COM + para el componente TI  
  
1.  En un símbolo del sistema, ejecute %systemroot%\system32\com\comexp.msc.  
  
2.  En **servicios de componentes** de la consola, expanda **servicios de componentes**, expanda **equipos**, expanda **Mi PC**, haga clic en  **La aplicación COM +**, seleccione **New**y, a continuación, haga clic en **aplicación**.  
  
    1.  En el **bienvenida** página, haga clic en **siguiente**y, a continuación, haga clic en **crear una aplicación vacía** en el **instale o cree una nueva aplicación** página.  
  
    2.  Tipo de `BTSScn SO TI Component` en el **escriba un nombre para la nueva aplicación** cuadro, seleccione **aplicación de servidor** como **tipo de activación**y, a continuación, haga clic en **siguiente**.  
  
    3.  En el **cuenta** cuadro de grupo de la **establecer identidad de la aplicación** página, seleccione **Este usuario**y, a continuación, escriba el nombre de usuario y la contraseña en la **usuario**y **contraseña** cuadros. La nueva aplicación COM+ se ejecutará bajo esta cuenta de usuario. La cuenta de usuario debe ser un miembro del grupo local de usuarios en tiempo de ejecución de HIS. Para este tutorial, use la misma cuenta de usuario que está utilizando el servicio de BizTalk.  
  
    4.  En el **agregar funciones de aplicación** página, haga clic en **siguiente**.  
  
    5.  En el **agregar usuarios a funciones** página, expanda **CreatorOwner**, haga clic en **usuarios**y, a continuación, haga clic en **agregar**.  
  
    6.  En el **Seleccionar usuarios o grupos** cuadro de diálogo, seleccione una cuenta de usuario que se utilizará para tener acceso a los clientes de mainframe. Para este tutorial, agregue la cuenta local UserID.  
  
        > [!NOTE]
        >  Para tener acceso a la transacción CICS a través del componente TI, puede utilizar la aplicación COM+ o la aplicación Web que contiene el componente .NET Remoting. Este tutorial utiliza la aplicación COM+ y la interoperabilidad COM para componentes TI para obtener acceso al gran sistema y mejorar el rendimiento.  
  
    7.  En el **finalización** página, haga clic en **finalizar**.  
  
#### <a name="create-a-remote-environment-to-access-the-mainframe"></a>Crear un entorno remoto para obtener acceso al mismo  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Host Integration Server 2004**y, a continuación, haga clic en **TI Manager**.  
  
2.  En el **TI Manager** de la consola, haga clic en **Transaction Integrator (Configuration)**, expanda **Windows Initiated Processing**, haga clic en **remoto Entornos**, seleccione **New**y, a continuación, haga clic en **Remote Environment**.  
  
    1.  En el **bienvenida** página, haga clic en **siguiente**.  
  
    2.  En el **configura un nuevo entorno remoto** página, escriba el **Remote Application Name**y, a continuación, haga clic en **siguiente**. Para este tutorial, utilice el nombre Mainframe_TCP.  
  
    3.  En el **Configure Host Environment and Programming Model** página, seleccione **CICS** para el **host de destino** y **ELM Link** para el  **Modelo de programación**y, a continuación, haga clic en **siguiente**.  
  
    4.  En **el punto de conexión configurar, TCP/IP** página, escriba la dirección IP del gran sistema en el **dirección IP/DNS** cuadro y, a continuación, haga clic en **editar** para agregar el número de puerto. Su COM de HIS tendrá acceso a las transacciones a través de la dirección de extremo.  
  
    5.  En el **finalización** página, haga clic en **finalizar**.  
  
#### <a name="create-the-ti-component-for-the-service-oriented-solution"></a>Crear el componente TI para la solución orientada a servicios  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Host Integration Server 2004**y, a continuación, haga clic en **TI Manager**.  
  
2.  En el **TI Manager** de la consola, haga clic en **Transaction Integrator (Configuration)**, haga clic en **Windows Initiated Processing**y, a continuación, haga clic en **objetos**. Haga clic en **objetos**, haga clic en **New**y, a continuación, haga clic en **objeto**.  
  
    1.  En el **bienvenida** página, haga clic en **siguiente**.  
  
    2.  En el **especificar Or Locate An Object** página, haga clic en **examinar**, elija SOHISTIUsingCOM.TLB en la carpeta %BTSSolutionsPath%\SO\MFAccess\HISTIComponent y, a continuación, haga clic en **siguiente**.  
  
    3.  En el **Define Environment Characteristics para el objeto COM** página, seleccione **btsscn SO TI Component** para el **aplicación COM +**y, a continuación, haga clic en **siguiente** .  
  
    4.  En el **Define Remote Environment** página, seleccione el entorno remoto que ha creado en el procedimiento anterior para el **entorno remoto y, a continuación, haga clic en siguiente.**  
  
    5.  En el **Creation of WIP Objects** página, haga clic en **siguiente**y, a continuación, haga clic en **finalizar** en el **finalización** página.  
  
#### <a name="test-the-connectivity-to-the-mainframe"></a>Probar la conectividad con el gran sistema  
  
1.  En el Explorador de Windows, vaya a la carpeta %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester y haga doble clic en el archivo Interop.SOHISTIUsingCOM.dll.reg. Al hacerlo, agregará los valores de registro de la aplicación HISTISimpleTester para llamar al componente TI en tiempo de ejecución mediante RCW.  
  
2.  En el Explorador de Windows, vaya a la carpeta %BTSSolutionsPath%\SO\MFAccess\ y, a continuación, ejecute SetupMFAccess.bat.  
  
3.  En el Explorador de Windows, vaya a la carpeta %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug y, a continuación, ejecute BTSScnSOHISTIComponentSimpleTester.exe.  
  
    -   En la aplicación HISTISimpleTester, haga clic en **Call Mainframe Program - usar COM**. Devuelve cinco registros de la aplicación COBOL que se ejecuta en el gran sistema (mainframe).  
  
##  <a name="step13"></a>Crear los directorios virtuales para la orquestación de servicios Web  
  
1.  En el **Internet Information Services (IIS) Manager**, haga clic en **grupos de aplicaciones**, seleccione **New**y, a continuación, seleccione **delgrupodeaplicaciones**.  
  
    1.  En el **Agregar nuevo grupo de aplicaciones** diálogo cuadro, escriba la **Id. de grupo de aplicaciones** (cualquier valor) y, a continuación, haga clic en **Aceptar**.  
  
    2.  Haga clic en el grupo de aplicaciones recién creado y, a continuación, seleccione **propiedades**.  
  
    3.  En el **propiedades** página, haga clic en el **identidad** ficha, seleccione **Configurable**, escriba la **nombre de usuario** y **contraseña** y, a continuación, haga clic en **Aceptar**. Para este tutorial, use la misma cuenta de usuario que utiliza el servicio de BizTalk.  
  
    > [!NOTE]
    >  Este usuario debe tener permiso para ejecutar el servicio Web de proxy de orquestación y debe agregarse a uno de los grupos de administradores de BizTalk Server, administradores de SSO o administradores de aplicaciones afiliadas de SSO.  
  
2.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.  
  
     Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión del adaptador:  
  
     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter  
  
     Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter  
  
     Permisos de acceso = lectura, ejecución de scripts  
  
3.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:  
  
    1.  En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que creó en el paso anterior.  
  
    2.  En el **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro de grupo, seleccione **autenticación integrada de Windows habilitado**y, a continuación, desactive las demás **de acceso de autenticación** casillas de verificación. Haga clic en **Aceptar** para salir.  
  
4.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.  
  
     Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión en línea:  
  
     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline  
  
     Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline  
  
     Permisos de acceso = lectura, ejecución de scripts  
  
5.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:  
  
    1.  En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que acaba de crear.  
  
    2.  Haga clic en **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro de grupo, seleccione **autenticación integrada de Windows habilitado**y, a continuación, desactive las demás **de acceso de autenticación** casillas de verificación. Haga clic en **Aceptar** para salir.  
  
##  <a name="step15"></a>Crear solución orientada a servicios  
  
-   En un símbolo del sistema, cambie el directorio a % BTSSolutionsPath%\SO\BTSSoln, escriba `SetupBTSSoln.bat`, y, a continuación, presione ENTRAR. El archivo SetupBTSSoln.bat realiza las tareas siguientes:  
  
    -   Crea una clave de nombre seguro único (SNK) para firmar los ensamblados de la solución SO.  
  
    -   Extrae el símbolo de clave pública de la clave SNK y actualiza los archivos de enlace con el símbolo público.  
  
    -   Genera la solución SO.  
  
    -   Genera SSOApplicationConfig en la carpeta %BTSSolutionsPath%\Common.  
  
##  <a name="step17"></a>Crear aplicaciones afiliadas SSO  
  
1.  Abra un símbolo del sistema y, a continuación, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts.  
  
2.  En el símbolo del sistema, abra el archivo PendTransAffApp.xml con el Bloc de notas y revíselo. No es necesario realizar cambios en este archivo.  
  
    > [!NOTE]
    >  El archivo PendTransAffApp.xml define la aplicación afiliada SSO WoodgroveBank.PendingTransactions, para el sistema de servidor de transacciones pendientes. También define los grupos administrativos y de usuarios de la aplicación afiliada SSO. En este tutorial, utilice **usuarios de la aplicación de BizTalk** y **administradores de BizTalk Server**.  
    >   
    >  Si desea utilizar grupos diferentes de la aplicación afiliada SSO, debe crear grupos de Windows (con cualquier nombre) en Active Directory y, a continuación, cambie la **appAdminAccount** y **appUserAccount** nodos en el archivo PendTransAffApp.xml. Si lo hace, debe establecer el valor de **groupApp** atributo de **marcas** nodo en "Sí".  
    >   
    >  Para obtener más información sobre las aplicaciones afiliadas SSO, vea [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).  
  
3.  En el símbolo del sistema, abra el archivo PendTransUserMap.xml con el Bloc de notas y, a continuación, realice las siguientes modificaciones:  
  
    ```  
    <mapping>  
      <windowsDomain><DomainName></windowsDomain>  
      <windowsUserId><UserID></windowsUserId>  
      <externalUserId><ExternalUserID></externalUserId>  
    </mapping>  
    ```  
  
    > [!NOTE]
    >  El archivo PendTransUserMap.xml contiene las asignaciones de usuario para el sistema de servidor de transacciones pendientes.  
  
    > [!NOTE]
    >  Para el **externalUserId** nodo, use el identificador de usuario externo para el sistema de back-end de transacciones pendientes. Para este tutorial, utilice UserID como identificador externo.  
  
    > [!NOTE]
    >  Para el **windowsUserId** nodo, escriba el usuario que el nombre del **externalUserId** se asignarán a. Puede utilizar tanto un grupo de dominio como una cuenta de usuario de dominio. El usuario debe ser miembro del grupo al que se permitirá utilizar el sistema de servidor de transacciones pendientes. En este tutorial, utilice el nombre de usuario del servicio de BizTalk.  
  
    > [!NOTE]
    >  Para el **windowsDomain** nodo, escriba el nombre de dominio de la **windowsUserId**.  
  
4.  En el símbolo del sistema, abra el archivo PmntTrckAffApp.xml con el Bloc de notas y, a continuación, analice su contenido. No es necesario realizar cambios en este archivo.  
  
    > [!NOTE]
    >  El archivo PmntTrckAffApp.xml define la aplicación afiliada SSO WoodgroveBank.PaymentTracker para el sistema de servidor de seguimiento de pago.  
  
5.  En el símbolo del sistema, abra el archivo PmntTrckUserMap.xml con el Bloc de notas y, a continuación, realice las siguientes modificaciones:  
  
    ```  
    <mapping>  
      <windowsDomain><DomainName></windowsDomain>  
      <windowsUserId><UserID></windowsUserId>  
      <externalUserId><ExternalUserID></externalUserId>  
    </mapping>  
    ```  
  
    > [!NOTE]
    >  La aplicación afiliada SSO de seguimiento de pago se utilizará para el adaptador de MQSeries, y el Id. de usuario y contraseña externos asignados se enviarán con las propiedades de encabezado de MQSeries. MQSeries Server valida sólo la cuenta de servicio de BizTalk con la que se está ejecutando el adaptador de MQSeries. No valida ninguna credencial de usuario externo.  
    >   
    >  Para obtener más información acerca de SSO afiliadas aplicaciones para el adaptador de MQSeries, vea [cómo configurar ubicaciones de recepción de MQSeries adaptador y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).  
  
    > [!NOTE]
    >  El archivo PmntTrckUserMap.xml contiene las asignaciones de usuario SSO para el sistema de servidor de seguimiento de pago. El programa de simulador de seguimiento de pago simula las condiciones de acierto y error de la autenticación de usuarios.  
    >   
    >  El programa autentica correctamente todos los identificadores de usuario que comienzan con las letras **PT** (por ejemplo, **PTUserID**) pero no puede autenticar los identificadores que no comienzan por usuario **PT**. Esto permite elegir el Id. de usuario correcto según la condición que desee probar. También puede repetir todo el **asignación** nodo para cada identificador de usuario y definir varias asignaciones en el mismo archivo.  
  
    > [!NOTE]
    >  Para el **externalUserId** nodo, escriba el identificador de usuario externo para el sistema de back-end de seguimiento de pago. Para este tutorial, utilice PTUserID como identificador externo.  
  
    > [!NOTE]
    >  Para el **windowsUserId** nodo, escriba el usuario que el nombre del **externalUserId** se asignarán a. El usuario debe ser miembro del grupo al que se permitirá utilizar el sistema de servidor de seguimiento de pago. En este tutorial, utilice el nombre de usuario del servicio de BizTalk.  
  
    > [!NOTE]
    >  Para el **windowsDomain** nodo, escriba el nombre de dominio de la **windowsUserId**.  
  
6.  En el símbolo del sistema, abra el archivo ConfigStoreApp.xml con el Bloc de notas y, a continuación, analice su contenido.  
  
     Este archivo define la aplicación de almacenamiento de configuración de SSO que el escenario emplea para mantener los parámetros de configuración. Entre los parámetros de configuración, se encuentra el valor de tiempo de espera para la comunicación con SAP (tanto para la versión en línea como para la de adaptador), el nombre del administrador de cola y las colas que se emplearán al utilizar la versión en línea. No es necesario realizar cambios en este archivo.  
  
7.  En el símbolo del sistema, abra el archivo SetConfigValuesInSSO.cmd con el Bloc de notas y revise y cambie su contenido de acuerdo con los valores de la tabla siguiente.  
  
    > [!NOTE]
    >  Este archivo de comandos establece los valores de los parámetros de configuración de la base de datos de SSO. Contiene varios comandos establecidos que asignan valores a variables locales al principio del archivo de comandos.  
    >   
    >  Los valores SAPAdapterTimeout, PendingTransactionsAdapterTimeout y PaymentTrackingAdapterTimeout se utilizan en la versión de adaptador. Los valores restantes se utilizan en la versión en línea.  
  
    > [!NOTE]
    >  Puede escribir "" (dos comillas dobles) para los valores predeterminados marcados \<especificado por el usuario > en la tabla siguiente.  
  
    |Parámetro|Valor predeterminado|Description|  
    |---------------|-------------------|-----------------|  
    |SAPAdapterTimeout|20000|Tiempo máximo de espera (en milisegundos) de una solicitud al back-end SAP|  
    |SAPInlineTimeout|20000|Tiempo máximo de espera (en milisegundos) de una solicitud al back-end SAP|  
    |SAPInlineHostName|\<Especificado por el usuario >|Identificador de servidor SAP|  
    |SAPInlineClientNumber|\<Especificado por el usuario >|Número de cliente SAP|  
    |SAPInlineSystemNumber|\<Especificado por el usuario >|Número de sistema SAP|  
    |SAPInlineUserName|\<Especificado por el usuario >|Nombre de usuario utilizado para conectarse al servidor SAP.|  
    |SAPInlinePassword|\<Especificado por el usuario >|Contraseña utilizada para conectarse al servidor SAP.|  
    |PendingTransactionsAdapterTimeout|20000|Tiempo máximo de espera (en milisegundos) para una solicitud al servidor de transacciones pendientes|  
    |PendingTransactionsInlineTimeout|20000|Tiempo máximo de espera (en milisegundos) para una solicitud al servidor de transacciones pendientes|  
    |PendingTransactionsInlineURL|https://\<*el nombre del equipo*> /Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx|Dirección URL del servicio transacciones pendientes. \<*El nombre del equipo*> debe coincidir con el **nombre común** en el procedimiento "para crear una solicitud de certificado". No debe utilizar "localhost" para \< *el nombre del equipo*>.|  
    |PendingTransactionsInlineSSOAffiliateApp|WoodgroveBank.PendingTransactions|Nombre de la aplicación SSO de transacciones pendientes|  
    |PaymentTrackingAdapterTimeout|20000|Tiempo máximo de espera (en milisegundos) para una solicitud al sistema seguimiento de pagos|  
    |PaymentTrackingInlineTimeout|20000|Tiempo máximo de espera (en milisegundos) para una solicitud al sistema seguimiento de pagos|  
    |PaymentTrackingInlineQManager|\<Usuario Specified > (normalmente QM_\<*el nombre del equipo*>).|Nombre del administrador de la cola MQSeries|  
    |PaymentTrackingInlineMQChannelDefinition|" " (es necesario escribir las dos comillas dobles).|Si es local, una cadena vacía, o bien el nombre del canal con formato del servidor MQ remoto. Si mantiene todos los valores predeterminados en la configuración de IBM WebSphere MQ, la definición de canal será S__\<*el nombre del equipo*>/TCP /\<*el nombre del equipo*> (1414).|  
    |PaymentTrackingInlineRequestQueue|LastPaymentsInputQueue|Nombre de la cola MQ para las solicitudes de seguimiento de pago|  
    |PaymentTrackingInlineResponseQueue|LastPaymentsOutputQueue|Nombre de la cola MQ para respuestas de seguimiento de pago|  
    |PaymentTrackingInlineSSOAffiliateApp|WoodgroveBank.PaymentTracker|Nombre de la aplicación SSO de seguimiento de pago|  
    |StubSAPWebServiceURL|http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx|URL del servicio Web de código auxiliar del sistema SAP de límite de crédito|  
  
8.  En el símbolo del sistema, ejecute el siguiente comando establecer el entorno PATH:  
  
    -   `SET PATH=%PATH%;"%CommonProgramFiles%\Enterprise Single Sign-On"`  
  
9. En el símbolo del sistema, ejecute el CreateInitialConfigInSSO.cmd. Crea las aplicaciones afiliadas de SSO, la aplicación de almacén de configuración de SSO y las asignaciones de usuario para las aplicaciones afiliadas. A continuación, ejecuta SetConfigValuesInSSO.cmd para almacenar los valores de configuración en la aplicación de almacenamiento de la configuración SSO.  
  
10. En el símbolo del sistema, ejecute el comando siguiente para establecer la credencial de usuario de la aplicación afiliada de transacciones pendientes. Use la \< **DomainName**> y \< **UserID**> definido en el archivo PendTransUserMap.xml para el \<WindowsDomain >\\< WindowsUserId\>. Este comando pide que facilite la contraseña del usuario externo, UserID, utilizado en este tutorial.  
  
    -   `ssomanage -setcredentials <WindowsDomain>\<WindowsUserId> WoodgroveBank.PendingTransactions`  
  
11. En el símbolo del sistema, ejecute el comando siguiente para establecer la credencial de usuario de la aplicación afiliada de seguimiento de pago. Use la \< **DomainName**> y \< **UserID**> definido en el archivo PmntTrckUserMap.xml para el \<WindowsDomain >\\< WindowsUserId \>. Este comando pide que facilite la contraseña del usuario externo, PTUserID, utilizado en este tutorial.  
  
    > [!NOTE]
    >  El simulador de seguimiento de pago no valida la credencia de usuario externo. Puede escribir cualquier contraseña para el identificador PTUserID.  
  
    -   `ssomanage -setcredentials < WindowsDomain >\< WindowsUserId > WoodgroveBank.PaymentTracker`  
  
##  <a name="step19"></a>Implementar el archivo de definición de BAM para la solución orientada a servicios  
  
1.  Abra un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR para establecer la ruta para buscar las utilidades de SAE:  
  
    -   SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"  
  
2.  En el símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\BAM, escriba el comando siguiente y, a continuación, presione ENTRAR:  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
##  <a name="step21"></a>Implementar solución orientada a servicios  
  
#### <a name="update-the-binding-files-for-the-service-oriented-solution"></a>Actualizar los archivos de enlace para la solución orientada a servicios  
  
1.  En el símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, abra el archivo Deployallbinding.xml en Notepad y, a continuación, realice las siguientes modificaciones:  
  
    -   Cambie el nombre del servidor que aparece en SET MGMT_DB_SERVER y en MBMT_DB al nombre del servidor y de la base de datos que está utilizando BizTalk Server.  
  
    -   Cambie el valor de la variable SOLNDIR a "%BTSSolutionsPath%\SO\BTSSoln".  
  
2.  En un símbolo de sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Bindings.  
  
3.  Para la versión de adaptador, abra el archivo AdapterSOAOrchBindings.xml con el Bloc de notas y, a continuación, realice las siguientes modificaciones:  
  
    -   Reemplace todas las apariciones de __MQ_SERVER_NAME\_ \_ con el nombre del servidor de MQSeries.  
  
    -   Reemplace todas las apariciones de __MQ_QMANAGER_NAME\_ \_ con el nombre del Administrador de cola de MQSeries.  
  
    -   Reemplace todas las apariciones de __PT_WS_SERVER_NAME\_ \_ en la cadena "\<dirección > https://\__PT_WS_SERVER_NAME\_\_" con el nombre del servidor donde las transacciones pendientes Se implementa el servicio Web. El nombre del servidor debe coincidir con el **nombre común** en el paso "para configurar el servidor Web para SSL". No debe utilizar localhost.  
  
    > [!NOTE]
    >  El archivo de enlace, AdapterSOAOrchBindings.xml, emplea el servicio Web de código auxiliar para las siguientes funciones:  
    >   
    >  1.  El sistema de back-end SAP de límite de crédito.  
    > 2.  El adaptador de MQSeries para integrarse con el sistema de back-end de seguimiento de pagos.  
    > 3.  El servicio web de transacciones pendientes para realizar la llamada al componente .NET TI de HIS y realizar la integración con el sistema de back-end de mainframe.  
    >   
    >  Si no está utilizando un sistema mainframe, deberá emplear el servicio Web de código auxiliar para generar datos para el sistema de transacciones pendientes.  
  
4.  Para la versión en línea, abra el archivo InlineSOAOrchBindings.xml con el Bloc de notas y, a continuación, realice las siguientes modificaciones:  
  
    -   Reemplace todas las apariciones de __MQ_SERVER_NAME\_ \_ con el nombre del servidor de MQSeries.  
  
    -   Reemplace todas las apariciones de __MQ_QMANAGER_NAME\_ \_ con el nombre del Administrador de cola de MQSeries.  
  
#### <a name="deploy-the-service-oriented-solution"></a>Implementar la solución orientada a servicios  
  
-   En un símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, escriba el comando siguiente y, a continuación, presione ENTRAR:  
  
    -   `Deployallbinding.cmd`  
  
    > [!NOTE]
    >  El comando Deployallbinding.cmd crea una aplicación de BizTalk denominada BTSScn.SO.CustomerService e importa archivos de enlace para las versiones de adaptador y en línea.  
  
##  <a name="step23"></a>Configurar el código auxiliar de servicios Web de transacciones pendientes cuando no hay un gran sistema  
  
#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-adapter-version-without-a-mainframe"></a>Configurar el servicio Web de transacciones pendientes (para utilizar la versión del adaptador sin un gran sistema) de código auxiliar  
  
1.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.  
  
     Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web de transacciones pendientes para la versión del adaptador de código auxiliar:  
  
     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
     Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
     Permisos de acceso = lectura, ejecución de scripts  
  
2.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, haga clic en **propiedades**y, a continuación, modifique la configuración como se indica a continuación mediante el **propiedades** cuadro de diálogo.  
  
    1.  En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que creó en el paso "para crear los directorios virtuales de IIS para la solución".  
  
    2.  En el **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**. Haga clic en **Aceptar** para salir.  
  
3.  En el **consola de administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda y BTSScn.SO.CustomerService **enviar Puertos**, haga clic en **PendingTransactionSolicitResponsePort**y, a continuación, haga clic en **propiedades**.  
  
    1.  En el **General** página, haga clic en **configurar** para mostrar la **propiedades de transporte** diálogo cuadro y, a continuación, modifique la **dirección URL del servicio Web** a el servicio de código auxiliar Web de transacciones pendientes, por ejemplo:  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
    2.  Cierre todos los cuadros de diálogo.  
  
#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-inline-version-without-a-mainframe"></a>Configurar el servicio Web de transacciones pendientes (para utilizar la versión en línea sin un gran sistema) de código auxiliar  
  
1.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.  
  
     Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web de transacciones pendientes para la versión del adaptador de código auxiliar:  
  
     Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
     Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
     Permisos de acceso = lectura, ejecución de scripts  
  
2.  En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:  
  
    1.  En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que creó en el paso "para crear los directorios virtuales de IIS para la solución".  
  
    2.  En el **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**. Haga clic en **Aceptar** para salir.  
  
3.  Abra un símbolo del sistema y, a continuación, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts.  
  
4.  En el símbolo del sistema, abra el archivo SetConfigValuesInSSO.cmd con el Bloc de notas y, a continuación, establezca el valor de la **PendingTransactionsInlineURL** a la dirección URL del servicio Web de transacción pendiente de código auxiliar.  
  
    -   `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
5.  En el símbolo del sistema, escriba `SetConfigValuesInSSO.cmd`, y, a continuación, presione ENTRAR.  
  
##  <a name="step25"></a>Inicie el servicio solución orientada a servicios  
  
1.  Abra un símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, escriba el comando siguiente y, a continuación, presione ENTRAR para iniciar todas las orquestaciones de las versiones de adaptador y en línea.  
  
    -   `startAll.vbs`  
  
2.  Ejecute la solución orientada a servicios Para obtener más información acerca de cómo ejecutar la solución, vea [cómo ejecutar la solución orientada a servicios](../core/how-to-run-the-service-oriented-solution.md).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Pruebe las versiones del adaptador y en línea de la solución orientada a servicios en [cómo ejecutar la solución orientada a servicios](../core/how-to-run-the-service-oriented-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Antes de instalar la solución orientada a servicios](../core/before-installing-the-service-oriented-solution.md)   
 [Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [Solución orientada a servicios de configuración del equipo del desarrollador para el servicio](../core/developer-machine-setup-for-the-service-oriented-solution.md)