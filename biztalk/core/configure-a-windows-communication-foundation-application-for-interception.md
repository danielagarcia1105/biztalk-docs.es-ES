---
title: Cómo configurar una aplicación de Windows Communication Foundation para la intercepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37f2ccde-aa79-470a-ac31-57e4168dc54a
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42f8328268b82a377bb6d73f3bd7305122a830c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969658"
---
# <a name="how-to-configure-a-windows-communication-foundation-application-for-interception"></a>Cómo configurar una aplicación de Windows Communication Foundation para llevar a cabo una intercepción
Debe instalar el software interceptor de BAM y configurar la aplicación para utilizar el servicio de interceptor [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] de BAM antes de comenzar a recopilar los datos de actividad de BAM. Se supone que ha instalado correctamente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y sus dependencias, y que ha creado al menos un grupo de BizTalk.  
  
## <a name="installing-the-bam-eventing-software"></a>Instalar el software de eventos BAM  
 Antes de configurar la aplicación [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] para usar el interceptor de BAM para [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], deberá instalar el software Eventos BAM mediante el programa de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre cómo instalar el software eventos BAM y registrar los contadores de rendimiento, consulte [instalar el Software eventos BAM](../core/installing-the-bam-eventing-software.md).  
  
## <a name="configuring-a-wcf-application-for-tracking"></a>Configurar una aplicación de WCF para llevar a cabo un seguimiento  
 Deben llevarse a cabo cuatro tareas antes de que la aplicación [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] pueda comenzar a escribir la información de eventos de BAM:  
  
-   Se debe crear un modelo de observación mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de las herramientas de BAM y, a continuación, se implementa mediante la herramienta de línea de comandos del Administrador de BAM (bm.exe).  
  
-   Debe crearse e implementarse un archivo de configuración de interceptor mediante la herramienta de línea de comandos del administrador de BAM (bm.exe).  
  
-   El usuario que ejecuta la aplicación host debe ser un miembro del sistema de escritura de evento de actividad BAM adecuado (bam_\<actividad\>_EventWriter) roles de SQL Server para permitir que la aplicación leer información de configuración de interceptor y escribir para las actividades de BAM.  
  
-   Debe modificar el archivo App.config para el servidor y la aplicación cliente para cargar el servicio de seguimiento de BAM. Una vez modificado el archivo App.config, debe reiniciar la aplicación.  
  
 Los eventos comenzarán a aparecer en la base de datos de BAM de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] únicamente después de completar estas tareas correctamente.  
  
### <a name="deploying-an-observation-model"></a>Implementar modelos de observación  
 Debe haberse implementado un modelo de observación antes de implementar un archivo de configuración de interceptor o capturar actividades de BAM en la aplicación.  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a>Para implementar un modelo de observación mediante bm.exe  
  
1.  Haga clic en **iniciar** y, a continuación, haga clic en **ejecutar** para abrir el símbolo del sistema de Windows.  
  
2.  Tipo de **cmd** en el **abiertos** campo y, a continuación, haga clic en **Aceptar**.  
  
3.  Utilice el comando de cambio de directorio para mover el directorio que contiene el modelo de observación que se va a implementar. Por ejemplo, **c:\businessprocess\Orders cd**.  
  
4.  Implemente un modelo de observación mediante bm.exe:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm.exe implementar-all - Definitionfile:\<*definitionfile.xml*\>  
  
     Asegúrese de reemplazar \< *definitionfile.xml* \> con el nombre del archivo del modelo de observación que desea implementar. Para obtener más opciones, consulte [comandos de administración de Interceptor](../core/interceptor-management-commands.md).  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
5.  Tipo de **Exit** y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.  
  
### <a name="deploying-an-interceptor-configuration-file"></a>Implementar un archivo de configuración de interceptor  
 Debe implementar un archivo de configuración de interceptor antes de que la aplicación pueda capturar actividades de BAM.  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a>Para implementar un archivo de configuración de interceptor mediante bm.exe  
  
1.  Haga clic en **iniciar** y, a continuación, haga clic en **ejecutar** para abrir el símbolo del sistema de Windows.  
  
2.  Tipo de **cmd** en el **abiertos** campo y, a continuación, haga clic en **Aceptar**.  
  
3.  Utilice el comando de cambio de directorio para mover el directorio que contiene el archivo de configuración de interceptor que se va a implementar. Por ejemplo, **c:\businessprocess\Orders cd**.  
  
4.  Implementar un archivo de configuración de interceptor mediante bm.exe:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm.exe implementar-interceptor - Filename:\<*icfile.xml*\>  
  
     Asegúrese de reemplazar \< *icfile.xml* \> con el nombre del archivo de configuración de interceptor que desea implementar.  
  
    > [!NOTE]
    >  Puede usar el **-Force: True** marca para invalidar los orígenes de eventos existentes con el mismo nombre que los de su archivo de configuración de interceptor. Si lo hace, asegúrese de hacer la copia de seguridad de la configuración existente mediante el **get-interceptor** comando. Con la marca -Force:True puede eliminar cualquier configuración de interceptor que haga referencia a los orígenes de eventos que se están anulando.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
5.  Tipo de **Exit** y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.  
  
 Si ya ha implementado la aplicación [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], la nueva configuración no se cargará hasta el siguiente intervalo de sondeo. Sin embargo, si configura la aplicación y la reinicia, la configuración se selecciona de inmediato.  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a>Adición de usuarios al rol de actividad de BAM adecuado  
 El marco de trabajo de interceptor de BAM usa roles de SQL Server por actividad para controlar el acceso a las actividades y a la información de configuración. Debe agregar la cuenta del usuario que ejecuta la aplicación WCF a los roles de actividad de BAM correspondientes en la base de datos BAMPrimaryImport.  
  
### <a name="configuring-the-windows-communication-foundation-application-to-load-the-bam-tracking-service"></a>Configurar la aplicación de Windows Communication Foundation para cargar el Servicio de seguimiento de BAM  
 Configure la aplicación para cargar el Servicio de seguimiento de BAM mediante la agregación de unas cuantas líneas al archivo App.config para la aplicación servidor o cliente.  
  
 Para habilitar el seguimiento de BAM en su servidor o aplicación cliente de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], necesitará modificar el archivo de configuración App.config para incluir un comportamiento de extremo y una extensión de comportamiento adicionales y agregar un atributo de configuración de comportamiento. Los formatos del servicio y las plantillas de clientes son similares.  
  
 Al configurar la aplicación de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], tenga en cuenta lo siguiente. Si hay más de un comportamiento de extremo de BAM definido en el archivo App.config para la misma aplicación, es decir, el mismo cliente o servicio, BAM llevará a cabo las siguientes acciones:  
  
-   Si las cadenas de conexión son diferentes, BAM producirá una excepción.  
  
-   Si sólo difiere el intervalo de sondeo, BAM seleccionará uno y lo moverá. Durante el tiempo de diseño, no es posible determinar cuál se va a seleccionar.  
  
> [!NOTE]
>  Si las cadenas de conexión son iguales, lo que significa que hacen referencia al mismo equipo, el procesamiento de BAM tendrá lugar con normalidad.  
  
 La siguiente plantilla de App.config de ejemplo está configurada para una aplicación de servidor de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Define un extremo que usa un comportamiento personalizado "bamEndpointBehavior", configurado para usar el interceptor de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].  
  
```  
<system.serviceModel>  
  <services>  
    <service name="Service.CreditCardAuthorization">  
      <!-- The endpoint will use the "bamEndpointBehavior" -->   
      <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
    </service>  
  </services>  
  <bindings>  
    <wsDualHttpBinding>  
      <binding name="wsDualHttpBinding_ICreditCardAuthorization" transactionFlow="true" />  
    </wsDualHttpBinding>  
  </bindings>  
  <behaviors>  
    <endpointBehaviors>  
      <!-- Define a new behavior named "bamEndpointBehavior" -->  
      <behavior name="bamEndpointBehavior">  
        <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  <extensions>  
    <behaviorExtensions>  
      <!-- Define a new enpoint behavior extension using WCF interceptor -->  
      <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
    </behaviorExtensions>  
  </extensions>  
</system.serviceModel>  
```  
  
 Antes de usar su propio archivo App.config, tendrá que realizar algunos cambios pequeños en esta plantilla.  
  
##### <a name="to-use-this-template-in-your-wcf-service-appconfig-file"></a>Para usar esta plantilla en su archivo App.config del Servicio WCF  
  
1.  Abra el archivo App.config relacionado con la aplicación. Puede utilizar Notepad.exe u otro editor de texto para esta tarea.  
  
2.  Agregue la extensión de comportamiento BamEndpointBehavior de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] al elemento de `extensions` mediante el uso de los siguientes XML:  
  
    ```  
    <behaviorExtensions>  
      <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
    </behaviorExtensions>  
    ```  
  
    > [!NOTE]
    >  La extensión de comportamiento se denomina "BamEndpointBehaviorExtension", y puede modificarse según sea necesario para que se adapte a su entorno.  
  
3.  Agregue un nuevo comportamiento de extremo que use la nueva extensión de comportamiento al elemento `behaviors` mediante el uso de los siguientes XML. La extensión de comportamiento proporciona una cadena de conexión y un intervalo de sondeo en segundos.  
  
    ```  
    <endpointBehaviors>  
      <behavior name="bamEndpointBehavior">  
        <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
      </behavior>  
    </endpointBehaviors>  
    ```  
  
     Sustituya el origen de datos por el nombre del equipo que aloje la base de datos BamPrimaryImport en su entorno. Modifique el intervalo de sondeo para que se adapte a sus necesidades; un número alto significa que el interceptor de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] tardará más tiempo en detectar los cambios de configuración. Si ha cambiado el nombre de la extensión de comportamiento, úselo para sustituir "BamEndpointBehaviorExtension".  
  
    > [!NOTE]
    >  El nombre del comportamiento es "bamEndpointBehavior", y puede modificarse para que se adapte a su entorno.  
  
    > [!NOTE]
    >  En la especificación de `ConnectionString`, evite el uso de una combinación de nombre de usuario/contraseña en texto sin cifrar. Si lo usa, puede poner en peligro su servidor de base de datos.  
  
    > [!NOTE]
    >  Debe especificar un `PollingIntervalSec` superior o igual a 5 (segundos). Si especifica un valor inferior u omite el elemento `PollingIntervalSec`, se producirá un error y la intercepción no se configurará.  
  
4.  Agregue el atributo `behaviorConfiguration` al extremo del que va a realizar un seguimiento y proporcione el nombre del nuevo comportamiento:  
  
    ```  
    <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
    ```  
  
    > [!NOTE]
    >  Si ha usado un nombre de comportamiento diferente, proporciónelo en su lugar.  
  
     Puede aplicar la configuración de comportamiento a varios extremos.  
  
5.  Guarde el archivo App.config modificado y reinicie la aplicación.