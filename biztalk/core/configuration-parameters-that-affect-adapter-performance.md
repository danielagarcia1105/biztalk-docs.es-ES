---
title: "Parámetros de configuración que afectan al rendimiento del adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bbb9fb-0b31-45f0-a54c-7b2025e653b9
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e48eb329a50dda26555e76dd54dd4f4d33cb2c98
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="configuration-parameters-that-affect-adapter-performance"></a>Configuración de parámetros que afectan al rendimiento del adaptador
Esta sección describe los valores de configuración que pueden afectar al rendimiento de los adaptadores de BizTalk Server.  
  
## <a name="clr-hosting-thread-values-for-the-host"></a>Valores de subprocesos que alojan CLR para el host  
 Dado que un subproceso de Windows es la unidad más básica ejecutable disponible para un proceso de Windows, es importante asignar suficientes subprocesos al grupo de subprocesos .NET asociado a una instancia de host de BizTalk de para impedir la falta de subprocesos. Si hay falta de subprocesos, no hay suficientes subprocesos disponibles para realizar el trabajo solicitado, lo que puede afectar de forma negativa al rendimiento. Asimismo, se debe tener cuidado para evitar la asignación de más subprocesos de los que sean necesarios en el grupo de subprocesos .NET asociado a un host. La asignación de demasiados subprocesos al grupo de subprocesos .NET asociado a un host puede aumentar el cambio de contexto, lo que también puede tener un impacto negativo sobre el rendimiento general. El cambio de contexto se produce cuando el kernel de Windows pasa de ejecutar un subproceso a ejecutar otro subproceso y puede ser una operación de CPU de alto coste.  
  
 Modifique el número de subprocesos de Windows disponibles en el grupo de subprocesos .NET asociado a una instancia de un host de BizTalk. Para hacerlo, configure los valores apropiados en el Panel de configuraciones de BizTalk Server. Para obtener más información acerca de cómo modificar los valores de CLR. NET, vea [cómo modificar la configuración de .NET CLR](http://msdn.microsoft.com/library/ff629681\(v=BTS.70\).aspx).  
  
## <a name="aspnet-settings-that-can-impact-http-or-soap-adapter-performance"></a>Valores ASP.NET que pueden afectar al rendimiento del adaptador de HTTP o de SOAP  
 Los valores siguientes se pueden aplicar a una aplicación ASP.NET que hospeda una aplicación web con la que se comunique el adaptador de SOAP o de HTTP. Estos parámetros se configuran en los archivos web.config o machine.config del servidor que hospeda la aplicación web. Modifique estos valores para dar cabida a la carga que genera el puerto de envío del adaptador de HTTP o de SOAP. Para obtener más información acerca de estas opciones, consulte [contención, mal rendimiento e interbloqueos cuando hace solicitudes de servicios Web desde aplicaciones ASP.NET](http://go.microsoft.com/fwlink/p/?LinkId=196842).  
  
|**Parámetro**|**Sección del archivo de configuración**|**Valor predeterminado**|**Valor recomendado**|  
|-------------------|---------------------------------------|-----------------------|---------------------------|  
|**minFreeThreads**<br /><br /> El número mínimo de subprocesos libres para permitir la ejecución de nuevas solicitudes. ASP.NET mantiene tantos subprocesos libres para solicitudes que requieren subprocesos adicionales para completar su procesamiento.|\<httpRuntime\>|8|88 * es el número de procesadores del servidor que hospeda la aplicación web.|  
|**minFreeLocalRequestFreeThreads**<br /><br /> El número mínimo de subprocesos libres que ASP.NET mantiene disponibles para permitir la ejecución de nuevas solicitudes locales. Este número de subprocesos se mantiene reservado para las solicitudes que procedan del host local en caso de que algunas solicitudes emitan solicitudes secundarias al host local durante su procesamiento. Esto evita que se produzca un interbloqueo con una reentrada recursiva en el servidor Web.|\<httpRuntime\>|4|76 * el número de procesadores en el servidor que hospeda la aplicación Web.|  
|**executionTimeout**<br /><br /> Indica el número máximo de segundos que una solicitud tiene permitido ejecutar antes de que ASP.NET la cierre automáticamente.|\<httpRuntime\>|90|90|  
|**maxconnection**<br /><br /> Determina el número de conexiones a una dirección IP específica que se pueden realizar.|\<connectionManagement\>|2<br /><br /> Un valor de 2 para este ajuste cumple con la RFC de IETF RFC para la especificación HTTP 1.1 y está disponible para los escenarios de usuarios, pero no optimizada para un alto rendimiento.|12 * número de procesadores en el servidor que hospeda la aplicación Web.|  
|**maxWorkerThreads**<br /><br /> Configura la cantidad máxima de subprocesos de trabajador que se van a utilizar para el proceso por CPU.|\<processModel\>|20|100 **Nota:** este valor se multiplica implícitamente por el número de procesadores en el servidor.|  
|**minWorkerThreads**|\<processModel\>|1|**maxWorkerThreads** / 2 **Nota:** el parámetro minWorkerThreads no está en el archivo de configuración de forma predeterminada. Debe agregarlo. **Nota:** este valor se multiplica implícitamente por el número de procesadores en el servidor.|  
|**maxIoThreads**<br /><br /> ASP.NET lo utiliza para limitar el número de subprocesos de finalización que se utilizan.|\<processModel\>|20|100<br /><br /> Este valor se multiplica implícitamente por el número de procesadores del servidor.|  
  
 Si el equipo que hospeda los servicios Web ejecuta ASP.NET 2.0 o posterior, puede establecer **autoConfig = true** en la sección processModel del archivo Machine.config para configurar automáticamente las siguientes opciones para conseguir óptimo rendimiento en comparación con la configuración del equipo:  
  
-   El **maxWorkerThreads** atributo.  
  
-   El **maxIoThreads** atributo.  
  
-   El **minFreeThreads** atributo del elemento httpRuntime.  
  
-   El **minLocalRequestFreeThreads** atributo del elemento httpRuntime.  
  
-   El **maxConnection** atributo de la \<connectionManagement\> elemento Element (Network Settings).  
  
> [!NOTE]
>  El **processModel** sección se pueden establecer solo en el archivo Machine.config y afecta a todas las aplicaciones de ASP.NET que se ejecutan en el servidor.  
  
 Para obtener más información sobre la **processModel** el elemento del archivo machine.config vea el sitio Web de Microsoft MSDN en [http://go.microsoft.com/fwlink/p/?LinkId=62307](http://go.microsoft.com/fwlink/p/?LinkId=62307).  
  
## <a name="registry-setting-that-governs-the-tcp-window-size"></a>Valor del Registro que controla el tamaño de la ventana TCP  
 Los valores del Registro siguientes controlan el tamaño de la ventana TCP, que es la cantidad de datos recibidos (en bytes) que se almacenan en el búfer durante una conexión. Si el parámetro no está configurado como un valor óptimo, el rendimiento del adaptador puede verse afectado de forma negativa. Implemente esta configuración del Registro para aumentar el tamaño de la ventana TCP.  
  
> [!WARNING]
>  El uso incorrecto del Editor del Registro podría ocasionar graves problemas que podrían requerir la reinstalación del sistema operativo. Microsoft no garantiza que se puedan resolver los problemas derivados de un uso incorrecto del Editor del Registro. Utilice el Editor del Registro bajo su propia responsabilidad. Antes de modificar el registro, siempre hacer copia de seguridad del registro y compruebe que sabe cómo restaurar la copia de seguridad si se produce un problema.  
  
 Para aumentar el tamaño predeterminado de las ventanas TCP, siga los pasos siguientes:  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit.exe**y, a continuación, haga clic en **Aceptar** para iniciar el Editor del registro.  
  
     Vaya a **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\\**  
  
2.  En el **parámetros** clave, cree la siguiente entrada DWORD con el valor indicado.  
  
    |Entrada DWORD|Valor predeterminado|Valor recomendado|  
    |-----------------|-------------------|-----------------------|  
    |**TcpWindowSize**<br /><br /> Este valor determina el tamaño máximo de la ventana de recepción TCP del equipo. La ventana de recepción determina el número de bytes que un remitente puede transmitir sin recibir una confirmación. Normalmente, las ventanas de recepción grandes mejorarán el rendimiento en redes de gran ancho de banda.|17520|Configure un múltiplo del tamaño del segmento máximo de Ethernet (MSS) de 1460 como máximo hasta 64240. Si se usa la escala de Windows, configúrelo hasta un máximo de 65535.|  
  
    > [!NOTE]
    >  Debe reiniciar el equipo para que la nueva configuración surta efecto.  
  
3.  Cierre el Editor del registro.  
  
## <a name="see-also"></a>Vea también  
 [Planificación del rendimiento y la capacidad](../core/performance-and-capacity-planning.md)