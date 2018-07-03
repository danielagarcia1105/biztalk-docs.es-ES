---
title: Optimizar el rendimiento de IIS | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6722a2ee-3704-4aaa-9b0d-cef97bcb9a04
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad8db99f2f6d26b05960950376e30faaa5a2155d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971453"
---
# <a name="optimizing-iis-performance"></a>Optimizar el rendimiento de IIS
## <a name="apply-iis-configuration-options-to-improve-iis-performance"></a>Aplicar las opciones de configuración de IIS para mejorar el rendimiento de IIS  
 Internet Information Services (IIS) expone numerosos parámetros de configuración que afectan al rendimiento de IIS. En este tema se describe algunos de estos parámetros y se proporciona instrucciones generales para establecer los valores de parámetro para mejorar el rendimiento de IIS.  
  
### <a name="log-only-essential-information-or-completely-disable-iis-logging"></a>Registrar solamente información esencial o deshabilitar completamente el registro de IIS  
 El registro de IIS debe minimizar o incluso deshabilitar en un entorno de producción. Para deshabilitar el registro siga estos pasos:  
  
1.  Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el **conexiones** panel, haga clic para expandir **sitios**, haga clic para seleccionar el sitio Web para el que desea deshabilitar el registro, haga clic para seleccionar **vista características**y, a continuación, Haga doble clic en el **registro** característica.  
  
3.  Haga clic en **deshabilitar** en el **acciones** panel para deshabilitar el registro para este sitio Web.  
  
### <a name="disable-iis-asp-debugging-in-production-environments"></a>Deshabilitar la depuración de ASP de IIS en entornos de producción  
 Depuración de ASP de IIS debe deshabilitarse en un entorno de producción. Para deshabilitar ASP IIS depuración siga estos pasos: en el **conexiones** panel, haga clic para expandir **sitios**, haga clic para seleccionar el sitio web para el que desea deshabilitar la depuración, haga clic para seleccionar **Vista características**y, a continuación, haga doble clic en el **ASP** característica. Haga clic para expandir **compilación**, haga clic para expandir **propiedades de depuración**y compruebe que ambos **habilitar la depuración del lado cliente** y **habilitar del lado servidor Depuración** se establecen en **False**.  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2. En el **conexiones** panel, haga clic para expandir **sitios**, haga clic para seleccionar el sitio web para el que desea deshabilitar la depuración, haga clic para seleccionar **vista características**y, a continuación, Haga doble clic en el **ASP** característica.  
  
3. Haga clic para expandir **compilación**, haga clic para expandir **propiedades de depuración**y compruebe que ambos **habilitar la depuración del lado cliente** y **habilitar del lado servidor Depuración** se establecen en **False**.  
  
4. Si es necesario, haga clic en **aplicar** en el **acciones** panel.  
  
   Deshabilitar la depuración para aplicaciones de ASP.NET y servicios Web mediante la especificación de la \<la depuración de compilación = "false"\> sección en el archivo web.config de la aplicación web.  
  
### <a name="tune-the-value-of-the-asp-threads-per-processor-limit-property"></a>Ajustar el valor de la propiedad ASP subprocesos por procesador límite  
 El ASP **límite de subprocesos por procesador** propiedad especifica el número máximo de subprocesos de trabajo por procesador que crea IIS. Aumente el valor para el límite de subprocesos por procesador hasta que la utilización del procesador cumple al menos un 50 por ciento o superior. Esta configuración puede influir notablemente la escalabilidad de las aplicaciones Web y el rendimiento del servidor en general. Dado que esta propiedad define el número máximo de peticiones ASP que se pueden ejecutar simultáneamente, este valor debe permanecer en el valor predeterminado a menos que las aplicaciones ASP están realizando llamadas a componentes externos de larga duración. En este caso, puede aumentar el valor de límite de subprocesos por procesador. Esto permite que el servidor para crear más subprocesos para atender más solicitudes simultáneas. El valor predeterminado de límite de subprocesos por procesador es 25. El valor máximo recomendado para esta propiedad es 100.  
  
 Para aumentar el valor para el límite de subprocesos por procesador, siga estos pasos: en el **conexiones** panel, seleccione el servidor web, haga clic para seleccionar **vista características**y, a continuación, haga doble clic en el  **ASP** característica.  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2. En el **conexiones** panel, seleccione el servidor web, haga clic para seleccionar **vista características**y, a continuación, haga doble clic en el **ASP** característica.  
  
3. Haga clic para expandir **límites propiedades** en **comportamiento**, haga clic en **límite de subprocesos por procesador**, escriba el valor deseado para **límite de subprocesos por procesador**  y haga clic en **aplicar** en el **acciones** panel.  
  
   Para obtener más información acerca de cómo modificar las propiedades en el \<límites\> elemento de IIS 7.5 o 7.0 \<asp\> elemento, vea [límites de ASP \<límites\> ](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483).  
  
> [!NOTE]  
>  Dado que esta propiedad solo puede aplicarse en el nivel de servidor, la modificación de esta propiedad afecta a todos los sitios Web que se ejecutan en el servidor.  
  
### <a name="tune-the-value-of-the-asp-queue-length-property"></a>Ajustar el valor de la propiedad de longitud de cola de ASP  
 El objetivo de la optimización de esta propiedad es garantizar el buen tiempo de respuesta mientras se minimizan la frecuencia con el servidor envía el error HTTP 503 (Server Too Busy) a los clientes cuando la cola de solicitudes ASP está lleno. Si el valor de propiedad de longitud de cola de ASP es demasiado bajo, el servidor enviará el error HTTP 503 con mayor frecuencia. Si el valor de propiedad de longitud de cola de ASP es demasiado alto, es posible que perciben los usuarios que el servidor no responde cuando en realidad que su solicitud está esperando en la cola. A través de la cola durante los períodos de mucho tráfico, debe distinguir un patrón de web solicitud picos y valles. Anote el valor máximo y establezca el valor de la propiedad de longitud de cola de ASP justo encima el valor máximo. Utilice la cola para manejar los picos a corto plazo, asegúrese de tiempo de respuesta y limitar el sistema para evitar la sobrecarga cuando prolongado, se producen picos inesperados. Si no tiene datos para ajustar la propiedad de longitud de cola de ASP, será un buen punto de partida establecer una relación de uno a uno de las colas en conversaciones totales. Por ejemplo, si la propiedad ASP subprocesos por procesador límite se establece en 25 y tiene cuatro procesadores (4 * 25 = 100 subprocesos), establezca la propiedad de longitud de cola de ASP en 100 y ajustar a partir de ahí.  
  
 Para aumentar el valor de la longitud de cola de propiedad, siga estos pasos:  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2. En el **conexiones** panel, seleccione el servidor Web, haga clic para seleccionar **vista características**y, a continuación, haga doble clic en el **ASP** característica.  
  
3. Haga clic para expandir **límites propiedades** en **comportamiento**, haga clic en **longitud de cola**, escriba el valor deseado para **longitud de cola** y, a continuación, Haga clic en **aplicar** en el **acciones** panel.  
  
   Para obtener más información acerca de cómo modificar las propiedades en el \<límites\> elemento de IIS 7.5 o 7.0 \<asp\> elemento, vea [límites de ASP \<límites\> ](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483).  
  
> [!NOTE]  
>  Dado que esta propiedad solo puede aplicarse en el nivel de servidor, la modificación de esta propiedad afecta a todos los sitios Web que se ejecutan en el servidor.  
  
### <a name="tune-the-maxpoolthreads-registry-entry"></a>Optimizar la entrada de registro MaxPoolThreads  
 Esta configuración especifica el número de subprocesos de grupo pueden crear por cada procesador. Grupo de subprocesos inspeccionar la red para las solicitudes y procesar las solicitudes entrantes. El recuento de MaxPoolThreads no incluye los subprocesos que se usan las aplicaciones ISAPI. Por lo general, no debería crear más de 20 subprocesos por procesador. MaxPoolThreads es una entrada de registro REG_DWORD ubicada en HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\InetInfo\Parameters\ con el valor predeterminado es 4.  
  
### <a name="disable-wcf-services-tracing"></a>Deshabilitar el seguimiento de los servicios WCF  
 Utilice la herramienta Editor de configuración (SvcConfigEditor.exe) para deshabilitar el seguimiento en un entorno de producción de los servicios WCF. Para obtener más información acerca de la herramienta Editor de configuración, consulte [Configuration Editor Tool (SvcConfigEditor.exe)](http://go.microsoft.com/fwlink/?LinkID=127070) (http://go.microsoft.com/fwlink/?LinkID=127070).  
  
### <a name="configure-aspnet-20-maxconcurrentrequests-for-iis-7570-integrated-mode"></a>Configurar ASP.NET 2.0 MaxConcurrentRequests para el modo integrado de IIS 7.5 o 7.0  
 Cuando ASP.NET 2.0 está hospedado en IIS 7.5 o 7.0 en modo integrado, el uso de subprocesos se controla de forma diferente que en IIS 7.5 o 7.0 en modo clásico. Cuando ASP.NET 2.0 está hospedado en IIS 7.5 en el modo integrado, ASP.NET 2.0 restringe el número de solicitudes en lugar del número de subprocesos que se ejecutan al mismo tiempo las solicitudes que se ejecutan concurrentemente. Escenarios sincrónicos, esto indirectamente limitará el número de subprocesos porque el número de solicitudes será el mismo que el número de subprocesos. Pero para escenarios asincrónicos, el número de solicitudes y subprocesos probablemente serán muy diferente porque podría tener mucho más solicitudes que subprocesos. Cuando se ejecuta ASP.NET 2.0 en IIS 7.5 en modo integrado, se omiten el minFreeThreads y minLocalRequestFreeThreads del elemento "httpRuntime" en el archivo machine.config. Para el modo integrado de IIS 7.5, un valor DWORD denominado MaxConcurrentRequestsPerCPU en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0 determina el número de solicitudes simultáneas por CPU. De forma predeterminada, no existe la clave del registro y el número de solicitudes por CPU se limita a 12. .NET framework 3.5 SP1 incluye una actualización de los archivos binarios de la versión 2.0 que admite configurar grupos de aplicaciones de IIS mediante el archivo aspnet.config. Esta configuración se aplica solo al modo integrado (el modo ISAPI o clásico ignora esta configuración). La nueva sección de configuración aspnet.config con los valores predeterminados se enumera a continuación:  
  
```  
<system.web>  
   <applicationPool maxConcurrentRequestsPerCPU="12" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>  
</system.web>  
```  
  
 En el modo integrado de IIS 7.5, la maxWorkerThreads y los parámetros maxIoThreads en la sección "processModel" del archivo machine.config no se utilizan para controlar el número de ejecución de las solicitudes, sí, pero aún se usan para controlar el tamaño del grupo de subprocesos CLR ASP.NET lo utiliza. Cuando la sección "processModel" del archivo machine.config tiene "autoConfig = true" (que es el valor predeterminado), esto le dará el grupo de aplicaciones hasta 100 subprocesos de trabajo (MaxWorkerThreads) por cada CPU lógica. Por lo tanto, un servidor de mercancías común con 2 CPU de doble núcleo tendría 400 MaxWorkerThreads. Esto debería ser suficiente para todas las aplicaciones más exigentes.  
  
 Para obtener más información sobre cómo configurar el uso de subprocesos de ASP.NET en IIS 7.5, vea [Blog de Thomas Marquardt sobre el uso de subprocesos de ASP.NET en IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=157518) (http://go.microsoft.com/fwlink/?LinkId=157518).  
  
### <a name="configure-aspnet-4-maxconcurrentrequests-for-iis-7570-integrated-mode"></a>Configurar ASP.NET 4 MaxConcurrentRequests para el modo integrado de IIS 7.5 o 7.0  
 Con .NET Framework 4, el valor predeterminado de maxConcurrentRequestsPerCPU es 5000 que es un número muy grande y, por tanto, le permitirá una gran cantidad de solicitudes asincrónicas que se ejecuten simultáneamente. Para obtener más información, consulte [ \<applicationPool\> (configuración Web) del elemento](http://go.microsoft.com/fwlink/?LinkID=205339) (http://go.microsoft.com/fwlink/?LinkID=205339).  
  
 Para el modo integrado de IIS 7.5 o 7.0, un valor DWORD denominado MaxConcurrentRequestsPerCPU en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0 determina el número de solicitudes simultáneas por CPU. De forma predeterminada, no existe la clave del registro y el número de solicitudes por CPU se limita a 5000.  
  
### <a name="enable-iis-http-compression"></a>Habilitar la compresión HTTP de IIS  
 Para utilizar de forma más eficaz el ancho de banda disponible, habilite la compresión HTTP de IIS. La compresión HTTP proporciona el tiempo de transmisión entre exploradores con compresión habilitada e IIS, independientemente de si el contenido se sirve desde el almacenamiento local o un recurso UNC.  
  
-   **Para configurar la compresión en el nivel de servidor Web:**  
  
    1.  Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
    2.  En el **conexiones** panel, seleccione el servidor Web, haga clic para seleccionar **vista características**y, a continuación, haga doble clic en el **compresión** característica.  
  
    3.  Establecer las opciones de compresión deseado y, a continuación, haga clic en **aplicar** en el **acciones** panel.  
  
-   **Para configurar la compresión en el nivel de sitio Web:**  
  
    1.  Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
    2.  En el **conexiones** panel, haga clic para expandir **sitios**, haga clic para seleccionar el sitio Web para el que desea configurar la compresión, haga clic para seleccionar **vista características**, y a continuación, haga doble clic en el **compresión** característica.  
  
    3.  Establecer las opciones de compresión deseado y, a continuación, haga clic en **aplicar** en el **acciones** panel.  
  
## <a name="see-also"></a>Vea también  
 [Optimización del rendimiento](../technical-guides/optimizing-performance.md)