---
title: Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IIS, installing virtual directories [service solutions]
- service solution tutorial, IIS virtual directories
- service solution tutorial, stub version
- deploying, BAM solutions [service solutions]
- service solution tutorial, solutions [BAM]
- service solution tutorial, service solutions
- SSO, configuring
- IBM WebSphere MQ Client
- service solution tutorial, IBM WebSphere MQ Client
- installing, tutorials
- service solutions, deploying
- service solution tutorial, SSO
- BAM, deploying solutions
- service solution tutorial, building solutions
- service solution tutorial, installing
ms.assetid: 45de7681-4df0-47a4-a02c-509140423a1e
caps.latest.revision: 53
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d42b559afb89c931aec44080beaa4c00dea89ba2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023666"
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a>Cómo instalar la versión de código auxiliar de esta solución orientada a servicios
Los pasos siguientes describen cómo preparar el equipo para instalar la versión de código auxiliar de la solución orientada a servicios y cómo instalar ésta en el equipo.  
  
-   [Preparar el equipo para instalar la versión de código auxiliar de la solución orientada a servicios](#step1)  
  
-   [Instalar al cliente IBM WebSphere MQ para Windows](#step3)  
  
-   [Crear los directorios virtuales en IIS para la solución orientada a servicios](#step5)  
  
-   [Compilar solución orientada a servicios](#step7)  
  
-   [Crear las entradas de inicio de sesión único (SSO) empresarial y los valores en la base de datos SSO](#step9)  
  
-   [Implementar la definición de BAM para la solución orientada a servicios](#step11)  
  
-   [Implementar la solución orientada a servicios](#step13)  
  
##  <a name="step1"></a> Preparar el equipo para instalar la versión de código auxiliar de la solución orientada a servicios  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a>Para preparar el equipo para instalar la versión de código auxiliar de la solución orientada a servicios  
  
1. Asegúrese de que el **sitio Web predeterminado** está configurado para usar ASP.NET 2.X.  
  
   1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  
  
   2.  En el **Internet Information Services (IIS) Manager**, el nombre del equipo, expanda **sitios**, expanda **sitio Web predeterminado**, expanda **aspnet_client**, expanda **system_web**.  
  
   3.  Asegúrese de que la subcarpeta es 2.X.  
  
2. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **herramientas administrativas**y, a continuación, haga clic en **servicios**. Mediante el **servicios** de consola, asegúrese de que se están ejecutando los siguientes servicios:  
  
   -   **Publicación en World Wide Web**  
  
3. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **herramientas administrativas**, haga clic en **administración de equipos** de consola y, a continuación, agregue el Cuenta de servicio de BizTalk al grupo de administradores local.  
  
4. Si ha instalado Windows SharePoint Services, excluya (raíz) de la **sitio Web predeterminado** desde Windows SharePoint Services rutas de acceso administradas como sigue: haga clic en **iniciar**, apunte a **todos los programas** , apunte a **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint**.  
  
   1.  En **configuración del servidor Virtual**, seleccione **configurar servidor virtual**.  
  
   2.  En el **lista de servidores virtuales** página, haga clic en **sitio Web predeterminado**.  
  
   3.  En el **configuración del servidor Virtual** página, haga clic en **definir rutas administradas**.  
  
   4.  En el **rutas incluidas** sección de la **definir rutas administradas** página, seleccione **raíz** y, a continuación, haga clic en **quitar rutas seleccionadas**.  
  
   5.  En el símbolo del sistema, ejecute IISReset.  
  
5. Cierre la sesión y, a continuación, inicie una sesión en el equipo con la cuenta de servicio de BizTalk.  
  
6. Abra un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR para establecer el entorno %BTSSolutionsPath%. A continuación, cierre el símbolo del sistema.  
  
   - setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"  
  
     > [!NOTE]
     >  Si está utilizando un equipo de 64 bits, escriba %ProgramFiles(x86)% en lugar de %ProgramFiles%.  
  
     > [!NOTE]
     >  Para obtener más información acerca del comando SETX, vea el sitio Web de Microsoft TechNet en [ http://go.microsoft.com/fwlink/?LinkId=67831 ](http://go.microsoft.com/fwlink/?LinkId=67831).  
  
##  <a name="step3"></a> Instalar al cliente IBM WebSphere MQ para Windows  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a>Para instalar el cliente IBM WebSphere MQ para Windows  
  
1. Descargue la última versión del cliente IBM WebSphere MQ para Windows.  
  
   > [!NOTE]
   >  Aunque la versión de código auxiliar de la solución no requiere IBM WebSphere Server, la aplicación cliente utiliza como referencia el archivo amqmdnet.dll incluido en el cliente IBM WebSphere MQ para Windows y, por tanto, es necesario instalarlo. En realidad, el cliente de la versión de código auxiliar no realiza llamadas a API del archivo DLL. Sólo es necesario para compilar y ejecutar la aplicación cliente. Puede descargar el cliente IBM WebSphere MQ para Windows desde el sitio Web de IBM.  
  
2. Instale el cliente IBM WebSphere MQ para Windows.  
  
   > [!NOTE]
   >  No es necesario configurar el cliente IBM WebSphere MQ para Windows. Mantener toda la configuración predeterminada.  
  
3. Agregue las clases WebSphere MQ para el ensamblado .NET a la caché de ensamblados global (GAC).  
  
   1. En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, desplácese al directorio \<directorio de instalación de IBM MQSeries\>\bin.  
  
   2. Ejecute el siguiente comando (asegúrese de que gacutil.exe se encuentra en el entorno de la ruta):  
  
       `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a> Crear los directorios virtuales en IIS para la solución orientada a servicios  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a>Para crear en IIS los directorios virtuales para la solución orientada a servicios  
  
1.  En el **Internet Information Services (IIS) Manager**, haga clic en **grupos de aplicaciones**, seleccione **Agregar grupo de aplicaciones**.  
  
     En el **Agregar grupo de aplicaciones** cuadro de diálogo, escriba `SSOStubAppPool` en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
     Los directorios virtuales que utiliza la solución orientada a servicios incluye el servicio Web publicado para la versión de código auxiliar de las orquestaciones, el servicio Web SAP de código auxiliar, el servicio Web de seguimiento de pago de código auxiliar y el servicio Web de de código auxiliar de transacciones pendientes.  
  
2.  En el **Internet Information Services (IIS) Manager**, haga clic en el grupo de aplicaciones recién creado y, a continuación, haga clic en **configuración avanzada**.  
  
3.  Haga clic en la columna a la derecha de la **identidad** propiedad y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
4.  En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione el **cuenta personalizada** opción y, a continuación, haga clic en **establecer**.  
  
5.  En el **establecer credenciales** cuadro de diálogo, especifique un nombre de usuario y una contraseña, confirme la contraseña y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Este usuario debe tener permiso para ejecutar el servicio Web de proxy de orquestación y debe agregarse a uno de los grupos de administradores de BizTalk Server, administradores de SSO o administradores de aplicaciones afiliadas de SSO.  
  
6.  Haga clic en **Aceptar** para cerrar el **identidad del grupo de aplicación** cuadro de diálogo.  
  
7.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Configuración avanzada** .  
  
8.  Crear una aplicación COM + para el componente de TI  
  
    1.  Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión de adaptador:  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub  
  
         Ruta de acceso = \<directorio de instalación de BizTalk\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub  
  
         Permisos de acceso = lectura, ejecución de scripts  
  
    2.  Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión de adaptador:  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP  
  
         Ruta de acceso = \<directorio de instalación de BizTalk\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP  
  
         Permisos de acceso = lectura, ejecución de scripts  
  
    3.  Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión de adaptador:  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions  
  
         Ruta de acceso = \<directorio de instalación de BizTalk\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans  
  
         Permisos de acceso = lectura, ejecución de scripts  
  
    4.  Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión de adaptador:  
  
         Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker  
  
         Ruta de acceso = \<directorio de instalación de BizTalk\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack  
  
         Permisos de acceso = lectura, ejecución de scripts  
  
9. En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub, haga clic en **propiedades**y, a continuación, modifique la configuración del siguiente modo:  
  
    1.  En el **directorio Virtual** pestaña, establezca el **AppPool** a **SSOStubAppPool** que acaba de crear.  
  
    2.  Haga clic en **seguridad de directorios** , haga clic **editar** en el **autenticación y control de acceso** cuadro de grupo, seleccione **autenticación integrada de Windows habilitado**y, a continuación, desactive las demás **de acceso de autenticación** casillas de verificación. Haga clic en **Aceptar** para salir.  
  
10. En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, haga clic en **propiedades**y, a continuación, modifique la configuración del siguiente modo:  
  
    1.  En el **directorio Virtual** pestaña, establezca el **AppPool** a **SSOStubAppPool** que acaba de crear.  
  
    2.  Haga clic en **seguridad de directorios** , haga clic **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**. Haga clic en **Aceptar** para salir.  
  
11. En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, haga clic en **propiedades**y, a continuación, modifique la configuración del siguiente modo:  
  
    1.  En el **directorio Virtual** pestaña, establezca el **AppPool** a **SSOStubAppPool** que acaba de crear.  
  
    2.  Haga clic en **seguridad de directorios** , haga clic **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**. Haga clic en **Aceptar** para salir.  
  
12. En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker, haga clic en **propiedades**y, a continuación, modifique la configuración del siguiente modo:  
  
    1.  En el **directorio Virtual** pestaña, establezca el **AppPool** a **SSOStubAppPool** que acaba de crear.  
  
    2.  Haga clic en **seguridad de directorios** , haga clic **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**. Haga clic en **Aceptar** para salir.  
  
##  <a name="step7"></a> Compilar solución orientada a servicios  
  
#### <a name="to-build-the-service-oriented-solution"></a>Para compilar la solución orientada a servicios  
  
1. Iniciar **símbolo del sistema de Visual Studio**.  
  
   > [!NOTE]
   >  En los archivos **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs** y **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\ customerserviceport.asmx.cs**, reemplace todas las instancias de 17f20caea2afcc8c por a1054514fc67bded.  
  
2. En el símbolo del sistema de Visual Studio, cambie el directorio por la carpeta %RutaSolucionesBTS%\SO\BTSSoln y, a continuación, ejecute el siguiente comando para generar la versión de código auxiliar de la solución orientada a servicios.  
  
   -   `SetupBTSSoln.bat`  
  
   > [!NOTE]
   >  En los archivos que se indican a continuación, sustituya todas las instancias de 17f20caea2afcc8c por el token de clave pública actual.  
   > 
   > - %RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs  
   >   -   %RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs  
   >   -   %RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs  
   >   -   %RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs  
   >   -   %RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs  
   >   -   %RutaInstalaciónBTS%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs  
  
##  <a name="step9"></a> Crear las entradas de inicio de sesión único (SSO) empresarial y los valores en la base de datos SSO  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a>Para crear las entradas y valores del inicio de sesión único (SSO) empresarial en la base de datos de SSO  
  
1.  Abra un símbolo del sistema, cambie el directorio actual a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts y, a continuación, ejecute el siguiente comando para generar el entorno PATH en la carpeta de inicio de sesión único (SSO) empresarial.  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  En el símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, abra el archivo ConfigStoreApp.xml en Notepad y, a continuación, revise el contenido del archivo.  
  
    > [!NOTE]
    >  Este archivo define la aplicación de almacenamiento de configuración de SSO que el escenario emplea para almacenar parámetros de configuración. Algunos de los parámetros de configuración incluyen la **tiempo de espera** valor utilizado para comunicarse con SAP (para las tres versiones). No es necesario realizar cambios en este archivo.  
  
3.  En el símbolo del sistema, ejecute el comando siguiente para crear la aplicación de almacenamiento de configuración de SSO.  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  En el símbolo del sistema, abra el archivo SetConfigValuesInSSO.cmd con Notepad y revise su contenido.  
  
    > [!NOTE]
    >  Este archivo de comandos establece los valores de los parámetros de configuración de la base de datos SSO. Contiene varias instrucciones SET que establecen los valores de las variables locales al principio del archivo de comandos. El **SAPAdapterTimeout**, **PendingTransactionsAdapterTimeout**, y **PaymentTrackingAdapterTimeout** valores se utilizan en la versión de código auxiliar y el adaptador. Los valores restantes se utilizan en la versión en línea. No es necesario realizar cambios en este archivo para la versión de código auxiliar.  
  
5.  En el símbolo del sistema, escriba `SetConfigValuesInSSO.cmd`, y, a continuación, presione ENTRAR para almacenar los valores en la aplicación de almacenamiento de configuración de inicio de sesión único.  
  
6.  En el símbolo del sistema, ejecute el siguiente comando para habilitar los vales en SSO:  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a> Implementar la definición de BAM para la solución orientada a servicios  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a>Para implementar la definición de SAE para la solución orientada a servicios  
  
1.  En el símbolo del sistema, escriba el siguiente comando y presione ENTRAR. De este modo, se configurará la ruta para buscar la utilidad de SAE:  
  
    -   CONJUNTO PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking  
  
2.  En el símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\BAM y escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
##  <a name="step13"></a> Implementar solución orientada a servicios  
  
#### <a name="to-deploy-the-service-oriented-solution"></a>Para implementar la solución orientada a servicios  
  
1.  Abra un símbolo del sistema y, a continuación, cambie el directorio a la carpeta %RutaSolucionesBTS%\SO\BTSSoln\Scripts.  
  
2.  Modificar el **DeployStubBinding.cmd** archivo reemplazando todas las instancias de "debug" y "development" por "release".  
  
3.  Abra un símbolo del sistema y, a continuación, cambie el directorio a la carpeta %RutaSolucionesBTS%\SO\BTSSoln\Scripts. Escriba el siguiente comando y presione ENTRAR:  
  
    -   `DeployStubBinding.cmd`  
  
4.  En el símbolo del sistema, ejecute el comando siguiente para iniciar las orquestaciones de la versión de código auxiliar:  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a>Pasos siguientes  
 Compruebe cómo funciona la versión de código auxiliar de la solución orientada a servicios [cómo ejecutar la solución orientada a servicios](../core/how-to-run-the-service-oriented-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Antes de instalar la solución orientada a servicios](../core/before-installing-the-service-oriented-solution.md)   
 [Solución orientada a servicios de instalación de las versiones de adaptador del servicio y en línea](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [Configurar el equipo del desarrollador para la solución orientada a servicios](../core/developer-machine-setup-for-the-service-oriented-solution.md)