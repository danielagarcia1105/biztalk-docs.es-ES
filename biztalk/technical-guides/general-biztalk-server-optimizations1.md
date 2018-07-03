---
title: Generales de BizTalk Server Optimizations1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8032553-bae3-440d-9197-b926160b0bdf
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2605a7acd9610b0b5417e8c5d7c875f67f22f30c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006717"
---
# <a name="general-biztalk-server-optimizations"></a>Optimizaciones generales de BizTalk Server
Las recomendaciones siguientes pueden utilizarse para aumentar el rendimiento de BizTalk Server. Las optimizaciones enumeradas en este tema se aplican después de que se ha instalado y configurado BizTalk Server.  
  
## <a name="configure-msdtc"></a>Configurar MSDTC  
 Para facilitar las transacciones entre SQL Server y BizTalk Server, debe habilitar Microsoft Distributed Transaction Coordinator (MS DTC). Para configurar MSDTC en BizTalk Server, vea el tema [directrices generales para mejorar el rendimiento del sistema operativo](../technical-guides/general-guidelines-for-improving-operating-system-performance.md).  
  
## <a name="recommendations-for-configuring-biztalk-server-hosts"></a>Recomendaciones para configurar los hosts de BizTalk Server  
 Esta sección proporcionan recomendaciones para configurar los hosts de BizTalk Server.  
  
### <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>Creación de varios hosts de BizTalk Server e instancias de host independientes por funcionalidad  
 Siga estas instrucciones para crear varios hosts de BizTalk Server y asignar la carga de trabajo en esos hosts:  
  
-   Cree hosts independientes para enviar, recibir, procesar y funcionalidad de seguimiento. Creación de varios hosts de BizTalk proporciona flexibilidad al configurar la carga de trabajo en el grupo de BizTalk y es el medio principal de distribuir el procesamiento en los equipos que ejecutan BizTalk Server en un grupo de BizTalk. Uso de varios hosts le permite detener un host sin que afecte a otros hosts. Por ejemplo, desea detener el envío de mensajes para permitirles cola en la base de datos de cuadro de mensajes mientras sigue permitiendo que un adaptador de recepción que se ejecuta en una instancia de host diferente recibir los mensajes entrantes. Separación de instancias de host mediante la funcionalidad, también proporciona las siguientes ventajas:  
  
    -   Ejecuta varios hosts de BizTalk reduce la contención en las tablas de cola de host de base de datos de cuadro de mensajes porque cada host se asigna a sus propias tablas de cola de trabajo en la base de datos de cuadro de mensajes.  
  
    -   Se implementa la limitación en BizTalk Server en el nivel de host. Esto le permite establecer diferentes características de limitación para cada host.  
  
    -   Se implementa la seguridad en el nivel de host; cada host se ejecuta bajo una identidad de Windows discreta. Esto le permite, por ejemplo, permitir acceso de Host_A a FileShare_B, al no permitir que cualquiera de los demás hosts para tener acceso a recurso compartido de archivos.  
  
-   Cada instancia de host tiene su propio conjunto de recursos, como memoria, identificadores y los subprocesos en el grupo de subprocesos. NET. Al asignar la carga de trabajo a través de hosts, considere la posibilidad de colocar los recursos que se escalan juntos en el mismo host.  
  
-   Las orquestaciones que tengan diferentes prioridades para los recursos en distintos hosts y los adaptadores independientes. Esta técnica se adapta a la ubicación de los hosts que ejecutan aplicaciones de alta prioridad en equipos dedicados de BizTalk Server.  
  
> [!NOTE]  
>  Aunque existen ventajas a la creación de instancias de host adicionales, también hay inconvenientes posibles si se han creado demasiadas instancias de host. Cada instancia de host es un servicio de Windows (BTSNTSvc.exe), que genera una carga adicional en la base de datos de cuadro de mensajes y consume recursos del equipo (como CPU, memoria, subprocesos).  
  
 Las propiedades de host para obtener más información acerca de cómo modificar el servidor BizTalk Server, vea [cómo modificar las propiedades de Host](http://go.microsoft.com/fwlink/?LinkID=154359) (http://go.microsoft.com/fwlink/?LinkID=154359) en la Ayuda de BizTalk Server 2010.  
  
### <a name="configure-a-dedicated-tracking-host"></a>Configurar un host de seguimiento dedicado  
 BizTalk Server está optimizado para rendimiento, por lo que la orquestación principal y los motores de mensajes no realmente mover los mensajes directamente a las bases de datos de seguimiento de BizTalk o BAM, como esto sería desviar estos motores de su trabajo principal de la ejecución de procesos empresariales. En su lugar, BizTalk Server deja los mensajes en la base de datos de cuadro de mensajes y los marca como que requieren un cambio a la base de datos de seguimiento de BizTalk. Un proceso en segundo plano (el host de seguimiento), a continuación, se mueve los mensajes a las bases de datos de seguimiento de BizTalk y BAM. Dado que seguimiento es una operación que consume muchos recursos, un host independiente debe crearse que se dedica a seguimiento, lo que minimiza el impacto que tiene seguimiento en los hosts dedicados al procesamiento de mensajes. Para obtener un rendimiento óptimo, debería haber menos un seguimiento instancia de host por base de datos de cuadro de mensajes. El número real de las instancias de host de seguimiento debe ser N + 1, donde N = número de bases de datos. El "+ 1" es para conseguir redundancia, en caso de que se produce un error en uno de los equipos que hospedan el seguimiento.  
  
 Uso de un host de seguimiento dedicado también le permite detener otros hosts de BizTalk sin interferir con el seguimiento de BizTalk Server. El movimiento de datos fuera de la base de datos de cuadro de mensajes de seguimiento es fundamental para un sistema de BizTalk Server en buen estado. Si se detiene el Host de BizTalk responsable de mover datos de seguimiento en el grupo de BizTalk, no se ejecutará el servicio de descodificación de datos de seguimiento. El impacto de esto es como sigue:  
  
- Datos de seguimiento de HAT no se moverá desde la base de datos de cuadro de mensajes a la base de datos de seguimiento de BizTalk.  
  
- Datos de seguimiento de BAM no se moverá desde la base de datos de cuadro de mensajes a la base de datos de importación principal de BAM.  
  
- Dado que no se mueven los datos, no se puede eliminar de la base de datos de cuadro de mensajes.  
  
- Cuando se detiene el servicio de descodificación de datos de seguimiento, los interceptores de seguimiento aún desencadenará y escribir datos de seguimiento en la base de datos de cuadro de mensajes. Si no se mueven los datos, esto hará que la base de datos de cuadro de mensajes se infle, lo que afectará al rendimiento en el tiempo. Incluso si no se realiza el seguimiento de las propiedades personalizadas o no se configuran los perfiles BAM, de forma predeterminada algunos datos se realiza un seguimiento (como canalización de recepción / envío de eventos y eventos de orquestación). Si no desea ejecutar el servicio de descodificación de datos de seguimiento, desactive la opción de todo el seguimiento para que no los interceptores de guardan los datos en la base de datos. Para deshabilitar el seguimiento global, consulte [cómo desactivar el seguimiento Global](http://go.microsoft.com/fwlink/?LinkID=154193) (http://go.microsoft.com/fwlink/?LinkID=154193) en la Ayuda de BizTalk Server 2010. Usar la consola de administración de BizTalk Server para deshabilitar de forma selectiva los eventos de seguimiento.  
  
  El host de seguimiento debe ejecutarse en al menos dos equipos que ejecuten BizTalk Server (para la redundancia en caso que se produce un error). Para obtener un rendimiento óptimo, debe tener al menos un seguimiento de la instancia de host por base de datos de cuadro de mensajes. El número real de las instancias de host de seguimiento debe (N + 1), donde N = número de bases de datos. El "+ 1" es para conseguir redundancia, en caso de que se produce un error en uno de los equipos que hospedan el seguimiento.  
  
  Seguimiento de un instancia de host mueve datos de seguimiento para bases de datos de cuadro de mensajes específicas, pero nunca habrá movimiento de datos para una base de datos de cuadro de mensajes específico de la instancia de host de más de un seguimiento. Por ejemplo, si tiene tres bases de datos de cuadro de mensajes y solo dos instancias de host de seguimiento, a continuación, una de las instancias de host debe mover los datos de dos de las bases de datos de cuadro de mensajes. Agrega una tercera instancia de host de seguimiento distribuye el seguimiento de host de trabajo a otro equipo que ejecuta BizTalk Server. En este escenario, agregando una cuarta instancia de host de seguimiento no sería distribuir cualquier host de seguimiento más trabajo, pero proporcionaría adicional seguimiento de la instancia de host para la tolerancia a errores.  
  
  Para obtener más información sobre el servicio de Bus de eventos BAM, consulte los siguientes temas de Ayuda de BizTalk Server 2010:  
  
- [Administrar el servicio de Bus de eventos BAM](http://go.microsoft.com/fwlink/?LinkID=154194) (http://go.microsoft.com/fwlink/?LinkID=154194).  
  
- [Creación de instancias de servicio de Bus de eventos BAM](http://go.microsoft.com/fwlink/?LinkID=154195) (http://go.microsoft.com/fwlink/?LinkID=154195).  
  
### <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>No clúster de hosts de BizTalk a menos que sea absolutamente necesario  
 Mientras que BizTalk Server 2010 le permite configurar un host de BizTalk como recurso de clúster, solo debe hacerlo si tiene que proporcionar una alta disponibilidad a un recurso que no se puede hospedar en varios equipos de BizTalk. Por ejemplo, los puertos mediante el adaptador de FTP únicamente deben residir en una instancia de host, como el protocolo FTP no proporciona el bloqueo de archivos. Sin embargo, esto introduce un único punto de error, que se beneficiaría de agrupación en clústeres. Hosts que contienen los adaptadores, como archivos, SQL, HTTP o procesar solo los hosts, pueden ser internamente carga equilibrada entre equipos y no se benefician de agrupación en clústeres.  
  
## <a name="increase-the-number-of--http-concurrent-connections-allowed-by-changing-the-value-for-the-maxconnection-parameter"></a>Aumentar el número de conexiones simultáneas de HTTP permitido cambiando el valor del parámetro maxconnection  
 De forma predeterminada, los adaptadores HTTP (incluidos los adaptadores de HTTP basado en WCF) abran sólo dos conexiones HTTP simultáneas desde cada equipo que ejecuta BizTalk Server a cualquier servidor de destino específico.  
  
 Esta configuración se ajusta a la RFC de IETF para la especificación HTTP 1.1 y, aunque es adecuado para escenarios de usuario, no está optimizado para un alto rendimiento. La configuración eficazmente limita las llamadas HTTP salientes para cada servidor para dos envíos simultáneos desde cada equipo que ejecuta BizTalk Server.  
  
 Para aumentar el número de conexiones simultáneas, puede modificar el valor del parámetro de maxconnection en el archivo de configuración de BizTalk Server, BTSNTSvc.exe.config (o BTSNTSvc64.exe.config para hosts de 64 bits), en cada servidor BizTalk Server. Esto puede aumentar para los servidores específicos que se llama. Como regla general, debe establecerse el valor del parámetro de maxconnection en 12 * el número de CPU o núcleos en el equipo que hospeda la aplicación web.  
  
> [!NOTE]  
>  No aumente el valor del parámetro de maxconnection en un valor tan grande que el servidor Web que se llama se desborda con conexiones HTTP. Después de cambiar el valor del parámetro maxconnection, realizar pruebas mediante el envío de solicitudes para cada servidor Web de destino para determinar un valor para maxconnection que proporcionará un buen rendimiento y HTTP envía sin sobrecargar el sitio Web de destino de esfuerzo servidores.  
  
 El siguiente ejemplo muestra la configuración de la propiedad de número máximo de conexiones:  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="24" />  
      <add address="*" maxconnection="48" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
 Al establecer la propiedad maxconnection, se pueden especificar el número de puerto, la dirección IP del sitio web, HTTPS y HTTP. Otros ejemplos incluyen:  
  
 **\<Agregar dirección = "<https://www.contoso.com>" maxconnection = "24" /\>**   
**\<Agregar dirección = "<http://www.contoso.com:8080>" maxconnection = "24" /\>**   
**\<Agregar dirección = "http://*IPAddress*" maxconnection = "24" /\>**  para obtener más información acerca de cómo ajustar la configuración de IIS y ASP.NET para servicios Web, vea la configuración de ASP.NET"que puede afectar al adaptador de HTTP sección de rendimiento"de [parámetros de configuración que afectan al rendimiento del adaptador](http://go.microsoft.com/fwlink/?LinkID=154200) (<http://go.microsoft.com/fwlink/?LinkID=154200>) en la Ayuda de BizTalk Server 2010.  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-can-host--isolated-received-locations-back-end-web-services-and-wcf-services"></a>Administrar el uso de subprocesos ASP.NET o que se ejecutan concurrentemente solicitudes para las aplicaciones Web que pueden hospedar aislado ubicaciones recibidas, servicios de back-end Web y servicios WCF  
 El número de trabajo y subprocesos de E/S (IIS 7.5 e IIS 7.0 en modo clásico) o el número de solicitudes (IIS 7.5 y 7.0 el modo integrado) para una aplicación Web ASP.NET que los hosts aislado ubicaciones recibidas, servicios de back-end Web y servicios WCF que se ejecutan concurrentemente debe modificarse en las siguientes condiciones:  
  
-   Uso de CPU no es un cuello de botella en el servidor de hospedaje Web.  
  
-   El valor de:  
  
    -   **ASP.NET aplicaciones v4.0.30319 \Request de tiempo de espera** o **aplicaciones ASP.NET v4.0.30319 \Request tiempo de ejecución** los contadores de rendimiento es extraordinariamente alto.  
  
    -   **Las aplicaciones ASP.NET v2.0.50727\Request de tiempo de espera** o **aplicaciones ASP.NET v2.0.50727\Request tiempo de ejecución** los contadores de rendimiento es extraordinariamente alto.  
  
-   Se genera un error similar al siguiente en el registro de aplicación del equipo que hospeda la aplicación Web.  
  
    ```  
    Event Type: Warning  
    Event Source: W3SVC Event Category: None  
    Event ID: 1013  
    Date: 11/4/2010  
    Time: 1:03:47 PM  
    User: N/A  
    Computer: <ComputerName>  
    Description: A process serving application pool 'DefaultAppPool' exceeded time limits during shut down. The process id was '<xxxx>'  
    ```  
  
### <a name="manage-aspnet-thread-usage-for-web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-iis-70-running-in-classic-mode"></a>Administrar el uso de subprocesos ASP.NET para aplicaciones Web que puede hospedar aisladas ubicaciones recibidas, servicios de back-end Web y servicios WCF en IIS 7.5 e IIS 7.0 que se ejecuta en modo clásico  
 Cuando el **autoConfig** se establece el valor en el archivo machine.config de un servidor IIS 7.5 e IIS 7.0 que se ejecuta en modo clásico en **true**, ASP.NET 2.0 y ASP.NET 4 administra el número de subprocesos de trabajo y subprocesos de E/S que se asignan a los procesos de trabajo IIS asociados.  
  
```  
<processModel autoConfig="true" />  
```  
  
 Para modificar manualmente el número de subprocesos de E/S para una aplicación de ASP.NET 2.0 y Web de ASP.Net 4 y de trabajo, abra el archivo machine.config asociado y, a continuación, escriba nuevos valores para el **maxWorkerThreads** y **maxIoThreads**  parámetros.  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  Estos valores son únicamente; como guía Asegúrese de que probar los cambios realizados en estos parámetros.  
  
 Para obtener más información acerca de cómo ajustar parámetros en el archivo machine.config para una aplicación Web de ASP.NET 2.0, consulte el artículo de Microsoft Knowledge Base 821268 [contención, mal rendimiento e interbloqueos cuando hace solicitudes de servicio Web de ASP. Las aplicaciones .NET](http://go.microsoft.com/fwlink/?LinkID=144169) (http://go.microsoft.com/fwlink/?LinkID=144169).  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-20-web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-iis-70-running-in-integrated-mode"></a>Administrar el número de solicitudes para las aplicaciones Web de ASP.NET 2.0 que pueden hospedar aisladas ubicaciones recibidas, servicios de back-end Web y servicios WCF en IIS 7.5 e IIS 7.0 que se ejecuta en modo integrado que se ejecutan concurrentemente  
 Cuando ASP.NET 2.0 se hospeda en IIS 7.5 e IIS 7.0 en modo integrado, el uso de subprocesos se controla de forma diferente que en IIS 7.5 e IIS 7.0 en modo clásico. Cuando ASP.NET 2.0 se hospeda en IIS 7.5 e IIS 7.0 en modo integrado, ASP.NET 2.0 restringe el número de la que se ejecutan concurrentemente **solicitudes** en vez del número de **subprocesos** que se ejecutan concurrentemente solicitudes. Escenarios sincrónicos indirectamente Esto limitará el número de subprocesos, pero para escenarios asincrónicos en el número de solicitudes y subprocesos probablemente serán muy diferente. Cuando se ejecuta ASP.NET 2.0 en IIS 7.5 e IIS 7.0 en modo integrado, el **maxWorkerThreads** y **maxIoThreads** parámetros en el archivo machine.config no se usan para controlar el número de subprocesos en ejecución. En su lugar, se puede cambiar el número de solicitudes que se ejecutan concurrentemente desde el valor predeterminado de 12 por CPU modificando el valor especificado para **maxConcurrentRequestsPerCPU**. El **maxConcurrentRequestsPerCPU** valor se puede especificar en el reqistry o en la sección de configuración de un archivo aspnet.config. Siga estos pasos para cambiar el valor predeterminado de **maxConcurrentRequestsPerCPU** para controlar el número de solicitudes que se ejecutan concurrentemente:  
  
 **Para establecer el valor de maxConcurrentRequestsPerCPU en el registro**  
  
> [!WARNING]  
>  El uso incorrecto del Editor del Registro podría ocasionar problemas que hicieran necesaria una reinstalación del sistema operativo. Utilice el Editor del Registro bajo su propia responsabilidad. Para obtener más información acerca de cómo realizar copias de seguridad, restaurar y modificar el registro, consulte el artículo de Microsoft Knowledge Base 256986 [información del registro de Windows para usuarios avanzados](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729).  
  
> [!NOTE]  
>  Esta configuración es global y no se puede cambiar para grupos de aplicaciones individuales o aplicaciones.  
  
1. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit.exe**y, a continuación, haga clic en **Aceptar** para iniciar el Editor del registro.  
  
2. Vaya a **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3. Cree la clave siguiendo estos pasos:  
  
   1.  En el **editar** menú, haga clic en **New**y, a continuación, haga clic en **clave**.  
  
   2.  Tipo **maxConcurrentRequestsPerCPU**y, a continuación, presione **ENTRAR**.  
  
   3.  En el **maxConcurrentRequestsPerCPU** clave, cree una entrada DWORD con el nuevo valor para maxConcurrentRequestsPerCPU.  
  
   4.  Cierre el Editor del registro.  
  
   **Para establecer el valor de maxConcurrentRequestsPerCPU para un grupo de aplicaciones en la sección de configuración de un archivo aspnet.config**  
  
> [!NOTE]  
>  Debe instalarse Microsoft .NET Framework 3.5 Service Pack 1 para dar cabida a establecer los valores siguientes a través del archivo de configuración. Puede descargar Microsoft .NET Framework 3.5 Service Pack 1 de [Microsoft .NET Framework 3.5 Service Pack 1](http://go.microsoft.com/fwlink/?LinkID=136345) (http://go.microsoft.com/fwlink/?LinkID=136345).  
  
 Abra el archivo aspnet.config para el grupo de aplicaciones y, a continuación, escriba nuevos valores para el **maxConcurrentRequestsPerCPU** y **requestQueueLimit** parámetros.  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  Este valor invalida el valor especificado para **maxConcurrentRequestsPerCPU** en el registro. El valor requestQueueLimit es igual a processModel/requestQueueLimit, salvo que la configuración en el archivo aspnet.config invalidará la configuración en el archivo machine.config.  
  
 Para obtener más información sobre cómo configurar el uso de subprocesos de ASP.NET en IIS 7.0, vea [Blog de Thomas Marquardt sobre el uso de subprocesos de ASP.NET en IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=157518) (http://go.microsoft.com/fwlink/?LinkId=157518).  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-4web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-70-running-in-integrated-mode"></a>Administrar el número de solicitudes para las aplicaciones ASP.NET 4Web que pueden hospedar aisladas ubicaciones recibidas, servicios de back-end Web y servicios WCF en IIS 7.5 y 7.0 que se ejecuta en modo integrado que se ejecutan concurrentemente  
 Con .NET Framework 4, el valor predeterminado de maxConcurrentRequestsPerCPU es 5000, que es un número muy grande y, por tanto, le permitirá una gran cantidad de solicitudes asincrónicas que se ejecuten simultáneamente. Para obtener más información, consulte [ \<applicationPool\> (configuración Web) del elemento](http://go.microsoft.com/fwlink/?LinkID=205339) (http://go.microsoft.com/fwlink/?LinkID=205339).  
  
 Para el modo de IIS 7.5 e IIS 7.0 integrado, un valor DWORD denominado MaxConcurrentRequestsPerCPU en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0 determina el número de solicitudes simultáneas por CPU. De forma predeterminada, no existe la clave del registro y el número de solicitudes por CPU se limita a 5000.  
  
 **Para establecer el valor de maxConcurrentRequestsPerCPU en el registro**  
  
> [!WARNING]  
>  El uso incorrecto del Editor del Registro podría ocasionar problemas que hicieran necesaria una reinstalación del sistema operativo. Utilice el Editor del Registro bajo su propia responsabilidad. Para obtener más información acerca de cómo realizar copias de seguridad, restaurar y modificar el registro, consulte el artículo de Microsoft Knowledge Base 256986 [información del registro de Windows para usuarios avanzados](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729).  
  
> [!NOTE]  
>  Esta configuración es global y no se puede cambiar para grupos de aplicaciones individuales o aplicaciones.  
  
1. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit.exe**y, a continuación, haga clic en **Aceptar** para iniciar el Editor del registro.  
  
2. Vaya a **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0**.  
  
3. Cree la clave siguiendo estos pasos:  
  
   1.  En el **editar** menú, haga clic en **New**y, a continuación, haga clic en **clave**.  
  
   2.  Tipo **maxConcurrentRequestsPerCPU**y, a continuación, presione **ENTRAR**.  
  
   3.  En el **maxConcurrentRequestsPerCPU** clave, cree una entrada DWORD con el nuevo valor para maxConcurrentRequestsPerCPU.  
  
   4.  Cierre el Editor del registro.  
  
   **Para establecer el valor de maxConcurrentRequestsPerCPU para un grupo de aplicaciones en la sección de configuración de un archivo aspnet.config**  
  
> [!NOTE]  
>  Debe instalarse Microsoft .NET Framework 4 para dar cabida a establecer los valores siguientes a través del archivo de configuración. Puede descargar Microsoft .NET Framework 4 desde [Microsoft .NET Framework 4 (instalador Web)](http://go.microsoft.com/fwlink/?LinkID=189318) (http://go.microsoft.com/fwlink/?LinkID=189318).  
  
-   Abra el archivo aspnet.config para el grupo de aplicaciones y, a continuación, escriba nuevos valores para el **maxConcurrentRequestsPerCPU** y **requestQueueLimit** parámetros.  
  
     Los valores en el ejemplo siguiente son los valores predeterminados.  
  
    ```  
    <system.web>  
        <applicationPool maxConcurrentRequestsPerCPU="5000" requestQueueLimit="5000"/>  
    </system.web>  
    ```  
  
> [!NOTE]  
>  Este valor invalida el valor especificado para **maxConcurrentRequestsPerCPU** en el registro. El **requestQueueLimit** configuración es igual a processModel/requestQueueLimit, salvo que la configuración en el archivo aspnet.config invalidará la configuración en el archivo machine.config.  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>Definir valores de subprocesos para las instancias de host de BizTalk de hospedaje de CLR  
 Dado que un subproceso de Windows es la unidad más básica ejecutable disponible para un proceso de Windows, es importante asignar suficientes subprocesos al grupo de subprocesos .NET asociado a una instancia de host de BizTalk de para impedir la falta de subprocesos. Cuando se produzca el colapso de los subprocesos, no hay suficientes subprocesos disponibles para realizar el trabajo solicitado que afecta negativamente al rendimiento. Asimismo, se debe tener cuidado para evitar la asignación de más subprocesos en el grupo de subprocesos .NET asociado a un host que ya no es necesario. La asignación de demasiados subprocesos al grupo de subprocesos .NET asociado a un host puede aumentar el cambio de contexto. Cambio de contexto se produce cuando cambia el kernel de Windows de ejecutar un subproceso a otro subproceso, ya que conlleva un costo de rendimiento. Asignación excesiva de subprocesos puede provocar el cambio de contexto excesivo que afectará negativamente al rendimiento general. El número predeterminado de subprocesos asignados al grupo de subprocesos de .NET de la instancia de host de BizTalk depende de qué versión de .NET Framework está instalada. .NET Framework 4 y .NET Framework 3.5 SP1 aumenta en gran medida los valores predeterminados, lo que pueden causar la asignación excesiva de subprocesos en los equipos de BizTalk Server y la contención de bloqueo excesivo en la base de datos de cuadro de mensajes.  
  
 Mediante el **panel de configuración de BizTalk**, puede modificar el valor predeterminado para el número de subprocesos de Windows disponibles en .NET asociado a una instancia de un host de BizTalk del grupo de subprocesos. Para obtener más información sobre cómo modificar la configuración de .NET CLR, vea [cómo modificar la configuración de .NET CLR](http://go.microsoft.com/fwlink/?LinkID=205344) (http://go.microsoft.com/fwlink/?LinkID=205344). La configuración de .NET CLR se realiza por CPU principal.  
  
> [!NOTE]  
>  **Subprocesos de trabajo** se usan para controlar los elementos de trabajo en cola y **subprocesos de E/S** son subprocesos dedicados de devolución de llamada asociados con un puerto de terminación de E/S para controlar una solicitud de E/S asincrónica completada.  
  
|Configuración de subprocesos|Valor predeterminado|Valor recomendado|  
|------------------------|-------------------|-----------------------|  
|Subprocesos de E/S máxima|250|250|  
|Subprocesos de trabajo máximo|25|100 **importante:** al aumentar este valor por encima de 100 puede tener un efecto adverso en el rendimiento del equipo de SQL Server que hospeda la base de datos de cuadro de mensajes de BizTalk Server. Cuando se produce este problema, el servidor SQL Server puede encontrar una condición de interbloqueo. Se recomienda no aumentar este parámetro más allá de un valor de 100.|  
|Subprocesos de E/S mínima|25|25|  
|Subprocesos de trabajo mínimo|5|25|  
  
> [!NOTE]  
>  Los valores recomendados no son absolutos y pueden que necesite ajustar en función de la aplicación de BizTalk. Cambiar un parámetro a la vez y, a continuación, medir el impacto en el rendimiento y la estabilidad de la plataforma de BizTalk antes de realizar cambios adicionales.  
  
> [!NOTE]  
>  Estos valores se multiplican implícitamente por el número de procesadores del servidor. Por ejemplo, si se establece la **MaxWorkerThreads** entrada en un valor de 100 establecería eficazmente un valor de 400 en un servidor de 4 CPU.  
  
## <a name="disable-biztalk-server-group-level-tracking"></a>Deshabilitar el seguimiento de nivel de grupo de BizTalk Server  
 Seguimiento implica rendimiento sobrecarga en BizTalk Server ya tienen datos se escriben en la base de datos de cuadro de mensajes y, a continuación, mueve asincrónicamente a la base de datos de seguimiento de BizTalk. Al configurar el seguimiento en un entorno de BizTalk Server de producción, se aplican las consideraciones siguientes:  
  
- Como regla general, si el seguimiento no es un requisito empresarial, a continuación, deshabilitar seguimiento de nivel de grupo para reducir la sobrecarga y aumentar el rendimiento.  
  
   Para deshabilitar el seguimiento de nivel de grupo de BizTalk Server, realice los pasos siguientes:  
  
  1.  En el **consola de administración de BizTalk Server**, expanda **administración de BizTalk Server**, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración** .  
  
  2.  En el cuadro de diálogo Panel de configuración de BizTalk, en la página grupo, desactive la **habilitar el seguimiento de nivel de grupo** casilla de verificación.  
  
  3.  Haga clic en **Aceptar** para aplicar las modificaciones y salir del panel de configuración.  
  
- Use solo el cuerpo del mensaje de seguimiento si es necesario. Función de procesamiento de mensajes y tamaño del mensaje, seguimiento de cuerpos de mensaje pueden provocar una sobrecarga considerable. Mientras la actividad de seguimiento de BizTalk tiene ventajas evidentes para depuración y la auditoría, también tiene implicaciones de escalabilidad y de rendimiento considerable. Por lo tanto, debe realizar un seguimiento únicamente los datos que es estrictamente necesario por motivos de seguridad y depuración y evita el seguimiento de información redundante.  
  
- De forma predeterminada, están habilitadas las siguientes opciones de seguimiento para orquestaciones:  
  
  - Orquestación inicio y fin  
  
  - Envío y recepción de mensajes  
  
  - Forma Inicio y finalización  
  
    La orquestación "de forma Inicio y de finalización" la opción de seguimiento implica una sobrecarga considerable y no debe habilitarse en un entorno de producción donde es necesario un alto rendimiento. Opciones de seguimiento de orquestaciones son accesibles en la consola de administración de BizTalk en el **seguimiento** página del cuadro de diálogo Propiedades de orquestación.  
  
  Para obtener más información acerca de cómo configurar el seguimiento, vea [configuración de seguimiento del uso de la consola de administración de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=158021) (http://go.microsoft.com/fwlink/?LinkId=158021).  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>Reducir el período de purgado para el trabajo DTA Purge and Archive de 7 días en 2 días en escenarios de alto rendimiento  
 De forma predeterminada, el intervalo de purgado de datos de seguimiento en el servidor BizTalk Server se establece en 7 días. En un escenario de alto rendimiento, esto puede producir en una compilación excesivo copia de datos en la base de datos de seguimiento, que finalmente afectará al rendimiento del cuadro de mensajes y negativamente a su vez al rendimiento de procesamiento de mensajes de impacto.  
  
 En escenarios de alto rendimiento, reducir el hardware y software de purga de intervalo del valor predeterminado de 7 días en 2 días. Para obtener más información acerca de cómo configurar el intervalo de purgado, vea [cómo configurar el trabajo DTA Purge and Archive](http://go.microsoft.com/fwlink/?LinkID=153814) (http://go.microsoft.com/fwlink/?LinkID=153814) en la Ayuda de BizTalk Server 2010.  
  
## <a name="configure-the-temp-path-for-the-biztalk-service-account-to-point-to-a-separate-disk-or-lun"></a>Configurar la ruta de acceso % temp % para la cuenta de BizTalk Service para que apunte a otro disco o LUN  
 Esto debe hacerse porque BizTalk utiliza la ubicación temporal para archivos de flujo en el disco cuando se realizan operaciones de asignación compleja.  
  
## <a name="install-the-latest-service-packs"></a>Instalar los service packs más recientes  
 Deben instalarse el service Pack más recientes de BizTalk Server y .NET Framework, ya que estos contienen correcciones que pueden corregir los problemas de rendimiento que pueden producirse.  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>Optimizaciones de rendimiento en la documentación de BizTalk Server  
 Se aplican las siguientes recomendaciones de la documentación de BizTalk Server según corresponda:  
  
-   [Solucionar problemas de latencia del cuadro de mensajes](http://go.microsoft.com/fwlink/?LinkId=158019) ()http://go.microsoft.com/fwlink/?LinkId=158019)  
  
-   [Identificar cuellos de botella de rendimiento](http://go.microsoft.com/fwlink/?LinkID=154238) ()http://go.microsoft.com/fwlink/?LinkID=154238)  
  
-   [Evitar excepciones DBNETLIB](http://go.microsoft.com/fwlink/?LinkID=155308) ()http://go.microsoft.com/fwlink/?LinkID=155308)  
  
-   [Evitar el agotamiento de puertos TCP/IP](http://go.microsoft.com/fwlink/?LinkID=153240) ()http://go.microsoft.com/fwlink/?LinkID=153240)  
  
-   [Establecer el tamaño del grupo de subprocesos EPM](http://go.microsoft.com/fwlink/?LinkId=158020) ()http://go.microsoft.com/fwlink/?LinkId=158020)  
  
## <a name="see-also"></a>Vea también  
 [Optimización del rendimiento de BizTalk Server](../technical-guides/optimizing-biztalk-server-performance.md)