---
title: "Cómo configurar una aplicación de Workflow Foundation para la intercepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c82e83f-9dbd-4325-9f30-778eba892296
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad184ce4b0ef619361f44f6eb1ee54a2354f5148
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-workflow-foundation-application-for-interception"></a>Cómo configurar una aplicación de Workflow Foundation para llevar a cabo una intercepción
Debe instalar el software interceptor de BAM y configurar la aplicación para utilizar el servicio de interceptor [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] antes de comenzar a recopilar los datos de actividad de BAM. Se supone que ha instalado correctamente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y sus dependencias, y que ha creado al menos un grupo de BizTalk.  
  
## <a name="installing-the-bam-eventing-software"></a>Instalar el software de eventos BAM  
 Antes de configurar la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] para usar el interceptor de BAM para [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], deberá instalar el software Eventos BAM mediante el programa de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre cómo instalar el software eventos BAM y registrar los contadores de rendimiento, consulte [instalar el Software eventos BAM](../core/installing-the-bam-eventing-software.md).  
  
## <a name="configuring-a-windows-workflow-foundation-application-for-tracking"></a>Configurar una aplicación de Workflow Foundation para llevar a cabo un seguimiento  
 Deben llevarse a cabo cuatro tareas antes de que la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] pueda comenzar a escribir la información de eventos de BAM:  
  
-   Debe crearse un modelo de observación mediante las herramientas de BAM de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y, a continuación, implementarlo mediante la herramienta de línea de comandos del administrador de BAM (bm.exe).  
  
-   Un archivo de configuración de interceptor se debe crear e implementarse mediante la línea de comandos de administrador de BAM-herramienta (bm.exe).  
  
-   El usuario que ejecuta la aplicación host debe ser un miembro del sistema de escritura de evento de actividad BAM adecuado (bam_\<actividad > _EventWriter) roles de SQL Server para permitir que la aplicación leer información de configuración de interceptor y escribir en el de BAM actividades.  
  
-   Debe modificar el archivo App.config o la aplicación para cargar el servicio de seguimiento de BAM y, a continuación, reiniciar la aplicación.  
  
 Los eventos comenzarán a aparecer en la base de datos de BAM de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] únicamente después de completar estas tareas correctamente.  
  
### <a name="deploying-an-observation-model"></a>Implementar modelos de observación  
 Debe haberse implementado un modelo de observación antes de implementar un archivo de configuración de interceptor o capturar actividades de BAM en la aplicación.  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a>Para implementar un modelo de observación mediante bm.exe  
  
1.  Haga clic en **iniciar** y, a continuación, haga clic en **ejecutar** para abrir el símbolo del sistema de Windows.  
  
2.  Tipo de **cmd** en el **abiertos** campo y, a continuación, haga clic en **Aceptar**.  
  
3.  Utilice el comando de cambio de directorio para mover el directorio que contiene el modelo de observación que se va a implementar. Por ejemplo, **c:\businessprocess\Orders cd**.  
  
4.  Implementar un modelo de observación mediante bm.exe:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\BM.exe implementar-all - definitionfile:\<*definitionfile.xml*>  
  
     Asegúrese de reemplazar \< *definitionfile.xml*> con el nombre del archivo de observación que desea implementar. Para obtener más opciones, consulte [comandos de administración de Interceptor](../core/interceptor-management-commands.md).  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
5.  Tipo de **Exit**, y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.  
  
### <a name="deploying-an-interceptor-configuration-file"></a>Implementar un archivo de configuración de interceptor  
 Debe implementar un archivo de configuración de interceptor antes de que la aplicación puede capturar actividades de BAM.  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a>Para implementar un archivo de configuración de interceptor mediante bm.exe  
  
1.  Haga clic en **iniciar** y, a continuación, haga clic en **ejecutar** para abrir el símbolo del sistema de Windows.  
  
2.  Tipo de **cmd** en el **abiertos** campo y, a continuación, haga clic en **Aceptar**.  
  
3.  Utilice el comando de cambio de directorio para mover el directorio que contiene el archivo de configuración de interceptor que se va a implementar. Por ejemplo, **c:\businessprocess\Orders cd**.  
  
4.  Implementar un archivo de configuración de interceptor mediante bm.exe:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\BM.exe implementar-interceptor - filename:\<*icfile.xml*>  
  
     Asegúrese de reemplazar \< *icfile.xml*> con el nombre del archivo de configuración de interceptor que desea implementar.  
  
    > [!NOTE]
    >  Puede usar el **-Force: True** marca para invalidar los orígenes de eventos existentes con el mismo nombre que los de su archivo de configuración de interceptor. Si lo hace, asegúrese de hacer la copia de seguridad de la configuración existente mediante el **get-interceptor** comando. Con la marca -Force:True puede eliminar cualquier configuración de interceptor que haga referencia a los orígenes de eventos que se están anulando.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
5.  Tipo de **Exit**, y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.  
  
 Si ya ha implementado la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], la nueva configuración no se cargará hasta el siguiente intervalo de sondeo. Sin embargo, si configura la aplicación y la reinicia, la configuración se selecciona de inmediato.  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a>Adición de usuarios al rol de actividad de BAM adecuado  
 El marco de trabajo de interceptor de BAM usa roles de SQL Server por actividad para controlar el acceso a las actividades y a la información de configuración. Debe agregar la cuenta del usuario que ejecuta la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] a la aplicación de BAM adecuada de la Base de datos de importación principal de BAM.  
  
### <a name="configuring-the-application-to-load-the-bam-tracking-service"></a>Configurar la aplicación para cargar el servicio de seguimiento de BAM  
 Hay tres escenarios posibles para cargar el servicio de seguimiento de BAM en la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]:  
  
-   Si la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] ya utiliza WorkflowRuntime para cargar una sección de configuración de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], puede agregar información de servicio de seguimiento de BAM a la sección existente.  
  
-   Si la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] no utiliza WorkflowRuntime para cargar una sección de configuración de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], tendrá que agregar código para cargar una sección personalizada desde el archivo de configuración de la aplicación. Tendrá que crear la sección y agregarle la información del servicio de seguimiento de BAM.  
  
-   Si prefiere codificar la configuración, puede utilizar la API de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] para cargar mediante programación el servicio de seguimiento sin un archivo de configuración, o bien cargar la configuración a partir de un origen personalizado.  
  
 Al configurar la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], tenga en cuenta las siguientes consideraciones:  
  
-   El interceptor de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] sólo admite un BamTrackingService por cada WorkflowRuntime.  
  
-   El interceptor de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] admite varias instancias de BamTrackingService por cada dominio de aplicación.  
  
    -   El número N de BamTrackingService se admite para el número N de WorkflowRuntime.  
  
-   El interceptor genera una excepción si se utilizan cadenas de conexión distintas para instancias de BamTrackingService independientes en el mismo dominio de la aplicación.  
  
-   El interceptor obtiene el valor de intervalo de sondeo de IC de la primera instancia de BamTrackingService que se inicia.  
  
-   El interceptor detiene el subproceso de sondeo de IC cuando se detiene el último BamTrackingService del dominio de la aplicación  
  
 Para obtener más información sobre WorkflowRuntime y cargar la información de configuración, consulte [http://go.microsoft.com/fwlink/?LinkId=83314](http://go.microsoft.com/fwlink/?LinkId=83314).  
  
##### <a name="to-configure-the-appconfig-file-for-the-bam-tracking-service"></a>Para configurar el archivo App.config para el servicio de seguimiento de BAM  
  
1.  Abra el archivo App.config relacionado con la aplicación. Puede utilizar Notepad.exe u otro editor de texto para esta tarea.  
  
2.  Agregue el servicio de seguimiento de BAM insertando la siguiente información de configuración en el archivo App.config. Debe situarse de forma que sea un elemento secundario del elemento `configuration`.  
  
    > [!NOTE]
    >  El elemento de sección debe corresponder al nombre utilizado por el código de la aplicación al utilizar la clase WorkflowRuntime.  
  
    ```  
    <!-- The element name must match the one expected by WorkflowRuntime in your WF application -->  
    <WorkflowServiceContainer>  
      <Services>  
        <add type="Microsoft.BizTalk.Bam.Interceptors.Workflow.BamTrackingService, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  
       ConnectionString="Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"   
          PollingIntervalSec="5"/>  
        </Services>  
    </WorkflowServiceContainer>  
    ```  
  
3.  Modificar el **ConnectionString** atributo para que coincida con su entorno.  
  
4.  Reinicie la aplicación.  
  
##### <a name="to-modify-your-application-to-load-a-custom-configuration-section"></a>Para modificar la aplicación para cargar una sección de configuración personalizada  
  
1.  Abra el proyecto de Windows Workflow Foundation en Visual Studio.  
  
2.  Agregue una nueva instancia de BamTrackingService con los parámetros adecuados en la instancia de la aplicación de WorkflowRuntime:  
  
    ```  
    // !! Replace "WorkflowServiceContainer" with the section name  
    // you used in your App.config file.  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime("WorkflowServiceContainer");  
    ```  
  
3.  Vuelva a compilar e implemente la aplicación modificada.  
  
##### <a name="to-modify-your-application-to-programmatically-load-the-bam-tracking-service"></a>Para modificar la aplicación para cargar mediante programación el servicio de seguimiento de BAM  
  
1.  Abra el proyecto de Windows Workflow Foundation en Visual Studio.  
  
2.  Agregue una nueva instancia de BamTrackingService con los parámetros adecuados en la instancia de la aplicación de WorkflowRuntime:  
  
    ```  
    string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"  
    int pollingInterval = 5;  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
    workflowRuntime.AddService(new BamTrackingService(connectionString, pollingInterval));  
    ```  
  
     Puede agregar o quitar parámetros basándose en su entorno específico.  
  
3.  Vuelva a compilar e implemente la aplicación modificada.