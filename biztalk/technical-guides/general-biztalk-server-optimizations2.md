---
title: Generales de BizTalk Server Optimizations2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41b452e9-d94c-4bcb-8ef6-e9cea28fc0ab
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af09f938d93377a6463926fad3725c9f9dace294
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022186"
---
# <a name="general-biztalk-server-optimizations"></a>Optimizaciones generales de BizTalk Server
Se pueden usar las siguientes recomendaciones para aumentar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rendimiento. Las optimizaciones enumeradas en este tema se aplican después de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ha instalado y configurado.  
  
## <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>Creación de varios hosts de BizTalk Server e instancias de host independientes por funcionalidad  
 Para enviar, recibir, procesar y funcionalidad de seguimiento, se deben crear hosts independientes. Creación de varios hosts de BizTalk proporciona flexibilidad al configurar la carga de trabajo en el grupo de BizTalk y es el medio principal de distribuir el procesamiento en los servidores BizTalk Server en un grupo de BizTalk. Varios hosts también permiten detener un host sin que afecte a otros hosts. Por ejemplo, desea dejar de enviar mensajes para permitirles cola la base de datos de cuadro de mensajes, mientras sigue permitiendo la recepción de mensajes que se produzca entrante. Separación de instancias de host mediante la funcionalidad, también proporciona las siguientes ventajas:  
  
-   Cada instancia de host tiene su propio conjunto de recursos, como memoria, identificadores y los subprocesos en el grupo de subprocesos. NET.  
  
-   Varios hosts de BizTalk también reducen la contención en las tablas de cola de host de base de datos de cuadro de mensajes porque cada host se asigna a sus propias tablas de cola de trabajo en la base de datos de cuadro de mensajes.  
  
-   Se implementa la limitación en BizTalk Server en el nivel de host. Esto le permite establecer diferentes características de limitación para cada host.  
  
-   Se implementa la seguridad en el nivel de host; cada host se ejecuta bajo una identidad de Windows discreta. Esto le permitiría, por ejemplo, para proporcionar acceso de Host_A a FileShare_B, al no permitir que cualquiera de los demás hosts para tener acceso a recurso compartido de archivos.  
  
> [!NOTE]  
>  Aunque existen ventajas a la creación de instancias de host adicionales, también hay inconvenientes posibles si se han creado demasiadas instancias de host. Cada instancia de host es un servicio de Windows (BTSNTSvc.exe), que genera una carga adicional en la base de datos de cuadro de mensajes y consume recursos del equipo (como CPU, memoria, subprocesos).  
  
 Para obtener más información acerca de cómo modificar las propiedades de Host de BizTalk Server, vea "Cómo para modificar propiedades de Host" en la Ayuda de BizTalk Server en [ http://go.microsoft.com/fwlink/?LinkId=101588 ](http://go.microsoft.com/fwlink/?LinkId=101588).  
  
## <a name="configure-a-dedicated-tracking-host"></a>Configurar un host de seguimiento dedicado  
 BizTalk Server está optimizado para rendimiento, por lo que la orquestación principal y los motores de mensajes no realmente mover los mensajes directamente a las bases de datos de seguimiento de BizTalk o BAM, como esto sería desviar estos motores de su trabajo principal de la ejecución de procesos empresariales. En su lugar, BizTalk Server deja los mensajes en la base de datos de cuadro de mensajes y los marca como que requieren un cambio a la base de datos de seguimiento de BizTalk. Un proceso en segundo plano (el host de seguimiento), a continuación, se mueve los mensajes a las bases de datos de seguimiento de BizTalk y BAM. Porque el seguimiento es una operación de uso intensivo de recursos, un host independiente debe crearse que se dedica a seguimiento, lo que minimiza el impacto que tiene seguimiento en los hosts dedicados al procesamiento de mensajes.  
  
 Uso de un host de seguimiento dedicado también le permite detener otros hosts de BizTalk sin interferir con el seguimiento de BizTalk Server. El movimiento de datos fuera de la base de datos de cuadro de mensajes de seguimiento es fundamental para un sistema de BizTalk Server en buen estado. Si se detiene el Host de BizTalk responsable de mover datos de seguimiento en el grupo de BizTalk, no se ejecutará el servicio de descodificación de datos de seguimiento. El impacto de esto es como sigue:  
  
- Datos de seguimiento de HAT no se moverá desde la base de datos de cuadro de mensajes a la base de datos de seguimiento de BizTalk.  
  
- Datos de seguimiento de BAM no se moverá desde la base de datos de cuadro de mensajes a la base de datos de importación principal de BAM.  
  
- Dado que no se mueven los datos, no se puede eliminar de la base de datos de cuadro de mensajes.  
  
- Cuando se detiene el servicio de descodificación de datos de seguimiento, los interceptores de seguimiento aún desencadenará y escribir datos de seguimiento en la base de datos de cuadro de mensajes. Si no se mueven los datos, esto hará que la base de datos de cuadro de mensajes se infle, lo que afectará al rendimiento en el tiempo. Incluso si no se realiza el seguimiento de las propiedades personalizadas o no se configuran los perfiles BAM, de forma predeterminada algunos datos se realiza un seguimiento (como canalización de recepción / envío de eventos y eventos de orquestación). Si no desea ejecutar el servicio de descodificación de datos de seguimiento, desactive la opción de todo el seguimiento para que no los interceptores de guardan los datos en la base de datos. Para deshabilitar el seguimiento global, consulte "Cómo para desactivar el seguimiento Global" en el servidor BizTalk Server ayuda a [ http://go.microsoft.com/fwlink/?LinkId=101589 ](http://go.microsoft.com/fwlink/?LinkId=101589). Usar la consola de administración de BizTalk Server para deshabilitar de forma selectiva los eventos de seguimiento.  
  
  El host de seguimiento debe ejecutarse en al menos dos equipos que ejecuten BizTalk Server (para la redundancia en caso que se produce un error). Para obtener un rendimiento óptimo, debe tener al menos un seguimiento de la instancia de host por base de datos de cuadro de mensajes. El número real de las instancias de host de seguimiento debe (N + 1), donde N = número de bases de datos. El "+ 1" es para conseguir redundancia, en caso de que se produce un error en uno de los equipos que hospedan el seguimiento.  
  
  Seguimiento de un instancia de host mueve datos de seguimiento para bases de datos de cuadro de mensajes específicas, pero nunca habrá movimiento de datos para una base de datos de cuadro de mensajes específico de la instancia de host de más de un seguimiento. Por ejemplo, si tiene tres bases de datos de cuadro de mensajes y solo dos instancias de host de seguimiento, a continuación, una de las instancias de host debe mover los datos de dos de las bases de datos de cuadro de mensajes. Agrega una tercera instancia de host de seguimiento distribuye el seguimiento de host de trabajo a otro equipo que ejecuta BizTalk Server. En este escenario, agregando una cuarta instancia de host de seguimiento no sería distribuir cualquier host de seguimiento más trabajo, pero proporcionaría adicional seguimiento de la instancia de host para la tolerancia a errores.  
  
  Para obtener más información sobre el servicio de Bus de eventos BAM, vea los temas siguientes en la Ayuda de BizTalk Server:  
  
- "Administrar el servicio de Bus de eventos BAM" en [ http://go.microsoft.com/fwlink/?LinkId=101590 ](http://go.microsoft.com/fwlink/?LinkId=101590).  
  
- "Creación de instancias de servicio de Bus de eventos BAM" en [ http://go.microsoft.com/fwlink/?LinkId=101591 ](http://go.microsoft.com/fwlink/?LinkId=101591).  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-host-orchestrations-published-as-a-web-or-wcf-service"></a>Administrar el uso de subprocesos ASP.NET o que se ejecutan concurrentemente solicitudes de aplicaciones Web que las orquestaciones de host se publican como un servicio WCF o Web  
 El número de trabajo y subprocesos de E/S (IIS 6.0 e IIS 7.0 en modo clásico) o el número de solicitudes (modo integrado de IIS 7.0) para una aplicación Web ASP.NET que hospeda una orquestación que se ejecutan concurrentemente publicado como un servicio Web debe modificarse en el condiciones siguientes:  
  
-   Uso de CPU no es un cuello de botella en el servidor de hospedaje Web.  
  
-   El valor de la **v2.0.50727\Request aplicaciones ASP.NET de tiempo de espera** o **aplicaciones ASP.NET v2.0.50727\Request tiempo de ejecución** los contadores de rendimiento es extraordinariamente alto.  
  
-   Un error similar al siguiente generado en el registro de aplicación del equipo que hospeda la aplicación Web:  
  
    ```  
    Event Type: Warning  
    Event Source: W3SVC Event Category: None  
    Event ID: 1013  
    Date: 6/4/2009  
    Time: 1:03:47 PM  
    User: N/A  
    Computer: <ComputerName>  
    Description: A process serving application pool 'DefaultAppPool' exceeded time limits during shut down. The process id was '<xxxx>'  
    ```  
  
### <a name="manage-aspnet-thread-usage-for-web-applications-that-host-orchestrations-on-iis-60-and-on-iis-70-running-in-classic-mode"></a>Administrar el uso de subprocesos ASP.NET para aplicaciones Web que hospedan las orquestaciones en IIS 6.0 y en IIS 7.0 que se ejecuta en modo clásico  
 Cuando el **autoConfig** se establece el valor en el archivo machine.config de un servidor de IIS 6.0 o IIS 7.0 que se ejecuta en modo clásico en **true**, ASP.NET 2.0 administra el número de subprocesos de trabajo y de subprocesos de E/S que están asignado a los procesos de trabajo IIS asociados:  
  
```  
<processModel autoConfig="true" />  
```  
  
 Para modificar manualmente el número de subprocesos de E/S para una aplicación Web de ASP.NET 2.0 y de trabajo, abra el archivo machine.config asociado y, a continuación, escriba nuevos valores para el **maxWorkerThreads** y **maxIoThreads**parámetros:  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  Estos valores son únicamente; como guía Asegúrese de que probar los cambios realizados en estos parámetros.  
  
 Para obtener más información acerca de cómo ajustar parámetros en el archivo machine.config para una aplicación Web de ASP.NET 2.0, consulte el artículo de Microsoft Knowledge Base [821268 "contención, mal rendimiento e interbloqueos cuando hace solicitudes de servicio Web de ASP.NET aplicaciones"](http://go.microsoft.com/fwlink/?LinkID=66483) (http://go.microsoft.com/fwlink/?LinkID=66483).  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-web-applications-that-host-orchestrations-on-iis-70-running-in-integrated-mode"></a>Administrar el número de solicitudes para las aplicaciones Web que hospedan las orquestaciones en ejecución en el modo integrado de IIS 7.0 que se ejecutan concurrentemente  
 Cuando ASP.NET 2.0 se hospeda en IIS 7.0 en modo integrado, el uso de subprocesos se controla de forma diferente que en IIS 6.0 o IIS 7.0 en modo clásico. Cuando ASP.NET 2.0 se hospeda en IIS 7.0 en modo integrado, ASP.NET 2.0 restringe el número de la que se ejecutan concurrentemente **solicitudes** en vez del número de **subprocesos** las solicitudes que se ejecutan concurrentemente. Escenarios sincrónicos indirectamente Esto limitará el número de subprocesos, pero para escenarios asincrónicos en el número de solicitudes y subprocesos probablemente serán muy diferente. Cuando se ejecuta ASP.NET 2.0 en IIS 7.0 en modo integrado, el **maxWorkerThreads** y **maxIoThreads** parámetros en el archivo machine.config no se usan para controlar el número de subprocesos en ejecución. En su lugar, se puede cambiar el número de solicitudes que se ejecutan concurrentemente desde el valor predeterminado de 12 por CPU modificando el valor especificado para **maxConcurrentThreadsPerCPU**. El **maxConcurrentThreadsPerCPU** valor se puede especificar en el reqistry o en la sección de configuración de un archivo aspnet.config. Siga estos pasos para cambiar el valor predeterminado de **maxConcurrentThreadsPerCPU** para controlar el número de solicitudes que se ejecutan concurrentemente:  
  
 **Para establecer el valor de maxConcurrentThreadsPerCPU en el registro**  
  
> [!WARNING]  
>  El uso incorrecto del Editor del Registro podría ocasionar problemas que hicieran necesaria una reinstalación del sistema operativo. Utilice el Editor del Registro bajo su propia responsabilidad. Para obtener más información acerca de cómo realizar copias de seguridad, restaurar y modificar el registro, consulte el artículo de Microsoft Knowledge Base "Descripción del registro de Microsoft Windows" en [ http://go.microsoft.com/fwlink/?LinkId=62729 ](http://go.microsoft.com/fwlink/?LinkId=62729).  
  
> [!NOTE]  
>  Esta configuración es global y no se puede cambiar para grupos de aplicaciones individuales o aplicaciones.  
  
1. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit.exe**y, a continuación, haga clic en **Aceptar** para iniciar el Editor del registro.  
  
2. Vaya a **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3. Cree la clave siguiendo estos pasos:  
  
   1.  En el **editar** menú, haga clic en **New**y, a continuación, haga clic en **clave**.  
  
   2.  Tipo **maxConcurrentThreadsPerCPU**y, a continuación, presione **ENTRAR**.  
  
   3.  En el **maxConcurrentThreadsPerCPU** clave, cree una entrada DWORD con el nuevo valor para maxConcurrentThreadsPerCPU.  
  
   4.  Cierre el Editor del registro.  
  
   **Para establecer el valor de maxConcurrentThreadsPerCPU para un grupo de aplicaciones en la sección de configuración de un archivo aspnet.config**  
  
> [!NOTE]  
>  Debe instalarse Microsoft .NET Framework 3.5 Service Pack 1 para dar cabida a establecer los valores siguientes a través del archivo de configuración. Puede descargar Microsoft .NET Framework 3.5 Service Pack 1 de [ http://go.microsoft.com/fwlink/?LinkID=136345 ](http://go.microsoft.com/fwlink/?LinkID=136345).  
  
-   Abra el archivo aspnet.config para el grupo de aplicaciones y, a continuación, escriba nuevos valores para el **maxConcurrentRequestsPerCPU** y **requestQueueLimit** parámetros:  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  Este valor invalida el valor especificado para **maxConcurrentThreadsPerCPU** en el registro. El valor requestQueueLimit es igual a processModel/requestQueueLimit, salvo que la configuración en el archivo aspnet.config invalidará la configuración en el archivo machine.config.  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>Definir valores de subprocesos para las instancias de host de BizTalk de hospedaje de CLR  
 Dado que un subproceso de Windows es la unidad más básica ejecutable disponible para un proceso de Windows, es importante asignar suficientes subprocesos al grupo de subprocesos .NET asociado a una instancia de host de BizTalk de para impedir la falta de subprocesos. Cuando se produzca el colapso de los subprocesos, no hay suficientes subprocesos disponibles para realizar el trabajo solicitado que afecta negativamente al rendimiento. Asimismo, se debe tener cuidado para evitar la asignación de más subprocesos en el grupo de subprocesos .NET asociado a un host que ya no es necesario. La asignación de demasiados subprocesos al grupo de subprocesos .NET asociado a un host puede aumentar el cambio de contexto. Cambio de contexto se produce cuando cambia el kernel de Windows de ejecutar un subproceso a otro subproceso, ya que conlleva un costo de rendimiento. Asignación excesiva de subprocesos puede provocar el cambio de contexto excesivo que afectará negativamente al rendimiento general.  
  
 Modificar el número de subprocesos de Windows disponibles en el grupo de subprocesos .NET asociado a una instancia de un host de BizTalk mediante la creación de los valores de CLR Hosting apropiados en el registro de BizTalk Server.  
  
> [!WARNING]  
>  El uso incorrecto del Editor del Registro podría ocasionar problemas que hicieran necesaria una reinstalación del sistema operativo. Utilice el Editor del Registro bajo su propia responsabilidad. Para obtener más información acerca de cómo realizar copias de seguridad, restaurar y modificar el registro, consulte el artículo de Microsoft Knowledge Base "Descripción del registro de Microsoft Windows" en [ http://go.microsoft.com/fwlink/?LinkId=62729 ](http://go.microsoft.com/fwlink/?LinkId=62729).  
  
> [!NOTE]  
>  **Subprocesos de trabajo** se usan para controlar los elementos de trabajo en cola y **subprocesos de E/S** son subprocesos dedicados de devolución de llamada asociados con un puerto de terminación de E/S para controlar una solicitud de E/S asincrónica completada.  
  
 **Para modificar el número de subprocesos disponibles en el grupo de subprocesos .NET asociado a cada instancia de un host de BizTalk, siga estos pasos:**  
  
1. Detenga la instancia de host de BizTalk.  
  
2. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit.exe**y, a continuación, haga clic en **Aceptar** para iniciar el Editor del registro.  
   Vaya a **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$**<em>hostname</em>] donde *hostname* es el nombre del host asociado con el host instancia de.  
  
   > [!NOTE]  
   >  Si ha actualizado la instalación de BizTalk Server 2006 de BizTalk Server 2004, esta clave del registro puede representarse como **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc *** guid*] donde *guid*  es un GUID único para cada instancia de un host de BizTalk Server.  
  
3. Busque el **alojamiento CLR** clave. Si esta clave no existe, a continuación, cree la clave siguiendo estos pasos:  
  
   1.  En el **editar** menú, haga clic en **New**y, a continuación, haga clic en **clave**.  
  
   2.  Tipo **alojamiento CLR**y, a continuación, presione **ENTRAR**.  
  
4. En el **alojamiento CLR** clave, cree las siguientes entradas DWORD con los valores indicados.  
  
   |Entrada DWORD|Valor predeterminado|Valor recomendado|  
   |-----------------|-------------------|-----------------------|  
   |MaxIOThreads|20|100|  
   |MaxWorkerThreads|25|100 **importante:** al aumentar este valor por encima de 100 puede tener un efecto adverso en el rendimiento del equipo de SQL Server que hospeda la base de datos de cuadro de mensajes de BizTalk Server. Cuando se produce este problema, el servidor SQL Server puede encontrar una condición de interbloqueo. Se recomienda que este parámetro no se aumenta más allá de un valor de 100.|  
   |MinIOThreads|1|25|  
   |MinWorkerThreads|1|25|  
  
   > [!NOTE]  
   >  Estos recomienda valores serán suficientes para la mayoría de los escenarios, pero es posible que tenga que aumentar dependiendo de cuántos controladores de adaptador u orquestaciones que se ejecutan en cada instancia de host.  
  
   > [!NOTE]  
   >  Estos valores se multiplican implícitamente por el número de procesadores del servidor. Por ejemplo, si define la entrada MaxWorkerThreads en un valor de 100 se definiría un valor de 400 en un servidor de 4 CPU.  
  
5. Cierre el Editor del registro.  
  
6. Reinicie la instancia de host de BizTalk.  
  
## <a name="disable-tracking-for-orchestrations-send-ports-receive-ports-and-pipelines-when-tracking-is-not-required"></a>Deshabilitar el seguimiento para orquestaciones, puertos de envío, puertos y canalizaciones de recepción cuando no se requiere seguimiento  
 Seguimiento implica rendimiento sobrecarga en BizTalk Server ya tienen datos se escriben en la base de datos de cuadro de mensajes y, a continuación, mueve asincrónicamente a la base de datos de seguimiento de BizTalk. Si el seguimiento no es un requisito empresarial, a continuación, deshabilitar el seguimiento para reducir la sobrecarga y aumentar el rendimiento. Para obtener más información acerca de cómo configurar el seguimiento, vea "Configuración de seguimiento utilizando la consola de administración" en el servidor BizTalk Server la Ayuda en [ http://go.microsoft.com/fwlink/?LinkID=106742 ](http://go.microsoft.com/fwlink/?LinkID=106742).  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>Reducir el período de purgado para el trabajo DTA Purge and Archive de 7 días en 2 días en escenarios de alto rendimiento  
 De forma predeterminada, el intervalo de purgado de datos de seguimiento en el servidor BizTalk Server se establece en 7 días. En un escenario de alto rendimiento, esto puede producir en una compilación excesivo copia de datos en la base de datos de seguimiento, que finalmente afectará al rendimiento del cuadro de mensajes y negativamente a su vez al rendimiento de procesamiento de mensajes de impacto.  
  
 En escenarios de alto rendimiento, reducir el hardware y software de purga de intervalo del valor predeterminado de 7 días en 2 días. Para obtener más información acerca de cómo configurar el intervalo de purgado, vea "Cómo configurar la DTA purgar y archivar trabajo" en el servidor BizTalk Server la Ayuda en [ http://go.microsoft.com/fwlink/?LinkID=104908 ](http://go.microsoft.com/fwlink/?LinkID=104908).  
  
## <a name="install-the-latest-service-packs"></a>Instalar los service packs más recientes  
 Deben instalarse el service Pack más recientes de BizTalk Server y .NET Framework, ya que estos contienen correcciones que pueden corregir los problemas de rendimiento que pueden producirse.  
  
## <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>No clúster de hosts de BizTalk a menos que sea absolutamente necesario  
 Mientras [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] y versiones posteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permiten configurar un host de BizTalk como recurso de clúster, solo puede hacerlo si tiene que proporcionar una alta disponibilidad a un recurso que no se puede hospedar en varios BizTalk equipos. Como ejemplo, los puertos que usa el adaptador de FTP únicamente debe residir en una instancia de host, como el protocolo FTP no proporciona el bloqueo de archivos, sin embargo, esto introduce un único punto de error que se beneficiaría de agrupación en clústeres. Hosts que contienen los adaptadores, como archivos, SQL, HTTP o procesar solo los hosts, pueden ser internamente carga equilibrada entre equipos y no se benefician de agrupación en clústeres.  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>Optimizaciones de rendimiento en la documentación de BizTalk Server  
 Se aplican las siguientes recomendaciones de la documentación de BizTalk Server según corresponda:  
  
-   "Solucionar problemas de latencia del cuadro de mensajes" en [http://go.microsoft.com/fwlink/?LinkId=114747](http://go.microsoft.com/fwlink/?LinkId=114747)  
  
-   "Identificar cuellos de botella de rendimiento" en [http://go.microsoft.com/fwlink/?LinkID=104418](http://go.microsoft.com/fwlink/?LinkID=104418)  
  
-   "Evitar excepciones DBNETLIB" en [http://go.microsoft.com/fwlink/?LinkID=108787](http://go.microsoft.com/fwlink/?LinkID=108787)  
  
-   "Evitar el agotamiento de puertos TCP/IP" en [http://go.microsoft.com/fwlink/?LinkID=101610](http://go.microsoft.com/fwlink/?LinkID=101610)  
  
-   "Establecer el tamaño del grupo de subprocesos de EPM" en [http://go.microsoft.com/fwlink/?LinkId=114748](http://go.microsoft.com/fwlink/?LinkId=114748)