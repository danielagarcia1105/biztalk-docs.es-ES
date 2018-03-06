---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: 
ROBOTS: NOINDEX
ms.openlocfilehash: 2aa74be2d86bcb8f32661fdcf06727eb6391861d
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a>Utilizar el adaptador de MQSeries con una versión anterior del adaptador
Las distintas versiones de BizTalk Server del adaptador de MQSeries pueden trabajar con el mismo WebSphere MQ Server remoto en Windows. Esto resulta posible porque las siguientes versiones de las aplicaciones COM+ utilizadas con el adaptador de MQSeries pueden coexistir en el mismo equipo con WebSphere MQSeries:  
  
-   **Aplicación MQSAgent (MQSAgent2) COM +** utilizada con el adaptador de MQSeries (BizTalk Server 2006) 
  
-   **Aplicación MQSAgent COM +** utilizada con el adaptador de MQSeries (BizTalk Server 2004)  
  
-   **Aplicación MQHelper COM +** utilizada con el adaptador de MQSeries (BizTalk Server 2002) 
  
> [!NOTE]
>  Al realizar la configuración de una instalación en paralelo de estas aplicaciones COM+, asegúrese de que ninguna se configura para utilizar las mismas colas de MQSeries.  
  
> [!IMPORTANT]
>  Solo se admite la instalación en paralelo de la versión de BizTalk Server 2006 de la aplicación COM + del adaptador de MQSeries con una versión anterior de la aplicación COM + del adaptador de MQSeries si una versión anterior de BizTalk Server no está instalada en el WebSphere Equipo de MQSeries.  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a>Para instalar la versión BizTalk Server 2006 de la aplicación COM+ del Adaptador de MQSeries en un equipo con WebSphere MQSeries que está ejecutando una versión anterior de la aplicación COM+ del Adaptador de MQSeries  
  
1.  Ejecute el Bootstrap.msi desde el directorio \Platform\BootStrap\ del CD BizTalk Server 2006 para copiar los archivos de dependencia MSVCR80.dll y MSVCP80.dll en el equipo con WebSphere MQSeries.  
  
2.  Copie el archivo MQSAgent.dll desde el directorio \Msi\Program Files\ en el CD de BizTalk Server 2006 en el equipo con WebSphere MQSeries.  
  
    > [!NOTE]
    >  Copie también el archivo MQSTrace.cmd desde este directorio para usar el equipo con WebSphere MQSeries si tiene intención de usar la utilidad de seguimiento de MQSAgent. Para obtener más información sobre el MQSAgent vea utilidad de seguimiento [analizar errores del adaptador de MQSeries con las herramientas de seguimiento](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).  
  
3.  Registre de forma manual los componentes de MQSAgent.dll mediante la ejecución de regsvr32 mqsagent.dll en el equipo con WebSphere MQSeries:  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  Ejecute este comando desde el mismo directorio al que copió MQSAgent.dll.  
  
4.  Cree una nueva aplicación COM+ para los componentes de MQSAgent:  
  
    -   Haga clic en aplicaciones COM +, haga clic en **New**, **aplicación** para mostrar la **Asistente para instalación de aplicación COM +** y haga clic en **siguiente**.  
  
    -   Haga clic en **crear una aplicación vacía**.  
  
    -   Escriba el nombre **MQSAgent2**, deje la opción predeterminada para **aplicación de servidor** habilitado y haga clic en **siguiente**.  
  
    -   Seleccione la opción de **este usuario**, escriba la información de cuenta correspondiente y haga clic en **siguiente**.  
  
        > [!NOTE]
        >  Esta cuenta debe tener permisos de connect, put o get en las colas adecuadas de IBM WebSphere MQ.  
  
    -   Haga clic en **siguiente** en el complemento **Roles de aplicación** cuadro de diálogo.  
  
    -   Haga clic en **siguiente** en el **agregar usuarios a funciones** cuadro de diálogo.  
  
    -   Haga clic en **Finalizar**.  
  
5.  Agregue los componentes de MQSAgent.dll a la aplicación MQSAgent2 COM+:  
  
    -   Haga clic para expandir el **MQSAgent2** aplicación COM +.  
  
    -   Haga clic en **componentes** y haga clic en **New**, **componente** para iniciar el Asistente para instalación de componentes COM + y, a continuación, haga clic en **siguiente**.  
  
    -   Haga clic en **instalar nuevos componentes**, busque el archivo MQSAgent.dll y, a continuación, haga clic en **abiertos**.  
  
    -   Haga clic en **Siguiente**y, a continuación, en **Finalizar**.  
  
## <a name="see-also"></a>Vea también  
 [Uso del adaptador de MQSeries](../core/using-the-mqseries-adapter.md)