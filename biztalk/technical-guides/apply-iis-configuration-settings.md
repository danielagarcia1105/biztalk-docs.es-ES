---
title: "Aplicar opciones de configuración de IIS | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d638f83-e1c8-4e35-b345-361d5a3093fa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a032070876df6bea0579a159d527a6ad903e2ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="apply-iis-configuration-settings"></a>Aplicar opciones de configuración de IIS
De forma predeterminada el mensaje SOAP, HTTP, y basado en HTTP WCF adaptadores (y .NET en general) abran sólo dos conexiones HTTP simultáneas desde cada instancia de host de BizTalk a cualquier servidor de destino específico. Por ejemplo, si tiene un puerto de envío SOAP envía mensajes a **http://www.contoso.com/SomeWebService.asmx**, a continuación, de forma predeterminada cada instancia de host que se ejecuta en cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] abrirá sólo dos conexiones HTTP simultáneas a **www.contoso.com**, con independencia de la cantidad de mensajes que deben enviarse.  
  
 Esta opción se ajusta a la RFC de IETF para la especificación de HTTP 1.1 y, aunque es conveniente para escenarios de usuario, no se optimiza para las comunicaciones de servidor a servidor de alto rendimiento. El valor predeterminado limita eficazmente las llamadas salientes de SOAP y HTTP envía a cada servidor de destino para dos simultánea de cada uno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instancia de host.  
  
## <a name="configure-aspnet-maxconcurrentrequests-for-iis-70-integrated-mode"></a>Configurar ASP.NET MaxConcurrentRequests para el modo integrado de IIS 7.0  
 Si ASP.NET 2.0 se hospeda en IIS 7.0 en modo integrado, el uso de subprocesos se trata de forma diferente que en IIS 6.0 o IIS 7.0 en modo clásico. Cuando ASP.NET 2.0 se hospeda en IIS 7.0 en modo integrado, ASP.NET 2.0 restringe el número de solicitudes en lugar del número de subprocesos que se ejecutan simultáneamente las solicitudes que se ejecutan concurrentemente. Para escenarios sincrónicos, esto indirectamente limitará el número de subprocesos porque el número de solicitudes será el mismo que el número de subprocesos. Pero para escenarios asincrónicos, el número de subprocesos y las solicitudes probablemente serán muy diferente porque podría tener mucho más solicitudes que subprocesos. Cuando se ejecuta ASP.NET 2.0 en IIS 7.0 en modo integrado, se omiten las minFreeThreads y minLocalRequestFreeThreads del elemento "httpRuntime" en el archivo machine.config. Para el modo integrado de IIS 7.0, un valor DWORD denominado MaxConcurrentRequestsPerCPU en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0 determina el número de solicitudes simultáneas por CPU. De forma predeterminada, no existe la clave del registro y el número de solicitudes por CPU se limita a 12. .NET framework 3.5 SP1 incluye una actualización de los archivos binarios de v2.0 que admita configurar grupos de aplicaciones de IIS mediante el archivo aspnet.config. Esta configuración se aplica solo al modo integrado (el modo ISAPI o clásico pasa por alto esta configuración). La nueva sección de configuración de archivo aspnet.config con los valores predeterminados se menciona a continuación:  
  
```  
<system.web>  
   <applicationPool maxConcurrentRequestsPerCPU="12" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>  
</system.web>  
```  
  
 Como regla general, MaxConcurrentRequestsPerCPU debe establecerse en un valor demasiado alto, como 5000.  
  
 En el modo integrado de IIS 7.0, el maxWorkerThreads y los parámetros de maxIoThreads en la sección "processModel" del archivo machine.config no se usan para controlar el número de solicitudes, en ejecución sí mismo, pero todavía se usan para controlar el tamaño del grupo de subprocesos CLR utilizados por ASP.NET. Cuando la sección "processModel" del archivo machine.config tiene "autoConfig = true" (que es el valor predeterminado), esto le dará el grupo de aplicaciones hasta 100 subprocesos de trabajo (MaxWorkerThreads) por CPU lógica. Por lo tanto, un servidor de mercancías común con 2 CPU de doble núcleo tendría 400 MaxWorkerThreads. Esto debería ser suficiente para todas las aplicaciones más exigentes.  
  
 Para obtener más información acerca de cómo configurar el uso de subprocesos de ASP.NET en IIS 7.0 y 6.0, consulte [Blog de Thomas Marquardt sobre el uso de subprocesos de ASP.NET en IIS 7.0 y 6.0](http://go.microsoft.com/fwlink/?LinkId=157518) (http://go.microsoft.com/fwlink/?LinkId=157518).  
  
## <a name="log-only-essential-information-or-completely-disable-iis-logging"></a>Registrar solamente información esencial o deshabilitar por completo el registro de IIS  
 El registro de IIS se debe minimizar o incluso deshabilitado en un entorno de producción. Para deshabilitar el registro siga estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el **conexiones** panel, haga clic para expandir **sitios**, haga clic para seleccionar el sitio Web para el que desea deshabilitar el registro, haga clic para seleccionar **vista características**y, a continuación, Haga doble clic en el **registro** característica.  
  
3.  Haga clic en **deshabilitar** en el **acciones** panel para deshabilitar el registro para este sitio Web.  
  
## <a name="disable-iis-asp-debugging-in-production-environments"></a>Deshabilitar la depuración de ASP de IIS en entornos de producción  
 Depuración de ASP de IIS debe deshabilitarse en un entorno de producción. Para deshabilitar IIS depuración ASP sigue estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el **conexiones** panel, haga clic para expandir **sitios**, haga clic para seleccionar el sitio web para el que desea deshabilitar la depuración, haga clic para seleccionar **vista características**y, a continuación, Haga doble clic en el **ASP** característica.  
  
3.  Haga clic para expandir **compilación**, haga clic para expandir **propiedades de depuración**y compruebe que ambos **Habilitar depuración de cliente** y **habilitar servidor Depuración** se establecen en **False**.  
  
4.  Si es necesario, haga clic en **aplicar** en el **acciones** panel.  
  
 Deshabilitar la depuración para aplicaciones y servicios Web ASP.NET mediante la especificación de la \<indicador de compilación debug = "false" / > sección en el archivo web.config para la aplicación web.  
  
## <a name="tune-the-value-of-the-asp-threads-per-processor-limit-property"></a>Ajustar el valor de la propiedad de ASP subprocesos por límite de procesador  
 El ASP **límite de subprocesos por procesador** propiedad especifica el número máximo de subprocesos de trabajo por procesador que crea IIS. Aumente el valor para el límite de subprocesos por procesador hasta que el uso de procesador cumple al menos el 50 por ciento o una versión posterior. Esta configuración puede influir considerablemente en la escalabilidad de las aplicaciones Web y el rendimiento del servidor en general. Dado que esta propiedad define el número máximo de solicitudes ASP que se pueden ejecutar simultáneamente, este valor debe permanecer en el valor predeterminado a menos que sus aplicaciones ASP realicen llamadas de larga duración a componentes externos. En este caso, puede aumentar el valor de límite de subprocesos por procesador. Esto permite que el servidor para crear más subprocesos para atender más solicitudes concurrentes. El valor predeterminado del límite de subprocesos por procesador es 25. El valor máximo recomendado para esta propiedad es 100.  
  
 Para aumentar el valor para el límite de subprocesos por procesador siga estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el **conexiones** panel, seleccione el servidor web, haga clic para seleccionar **vista características**y, a continuación, haga doble clic en el **ASP** característica.  
  
3.  Haga clic para expandir **límites propiedades** en **comportamiento**, haga clic en **límite de subprocesos por procesador**, escriba el valor deseado para **límite de subprocesos por procesador**  y haga clic en **aplicar** en el **acciones** panel.  
  
 Para obtener más información sobre cómo modificar las propiedades de la \<límites > elemento de IIS 7.0 \<asp > elemento, vea [límites de ASP \<límites >](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483).  
  
> [!NOTE]  
>  Dado que esta propiedad solo se aplica en el nivel de servidor, la modificación de esta propiedad afecta a todos los sitios Web que se ejecutan en el servidor.  
  
> [!NOTE]  
>  El ASP **límite de subprocesos por procesador** propiedad para IIS 7.0 reemplaza IIS 6.0 **ASPProcessorThreadMax** configuración de Metabase de ASP. Para obtener información acerca de la configuración de la Metabase de IIS 6.0 ASPProcessorThreadMax ASP, consulte [configuración de optimización de la Metabase de ASP](http://go.microsoft.com/fwlink/?LinkId=158834) (http://go.microsoft.com/fwlink/?LinkId=158834) en MSDN.  
  
## <a name="tune-the-value-of-the-asp-queue-length-property"></a>Ajustar el valor de la propiedad de longitud de la cola de ASP  
 El objetivo de esta propiedad para la optimización es garantizar el buen tiempo de respuesta al tiempo que minimiza la frecuencia con el servidor envía el error HTTP 503 (Server Too Busy) a los clientes cuando la cola de solicitudes ASP está completa. Si el valor de propiedad de longitud de la cola de ASP es demasiado bajo, el servidor enviará el error HTTP 503 con mayor frecuencia. Si el valor de propiedad de longitud de la cola de ASP es demasiado alto, los usuarios pueden percibir que el servidor no responde cuando en realidad que su solicitud está en espera en la cola. Observando la cola durante los períodos de mucho tráfico, debe distinguir un patrón de valores máximos de solicitud web y mínimos. Tome nota del valor máximo y establezca el valor de la propiedad de longitud de la cola ASP justo encima del valor máximo. Utilice la cola para atender los picos a corto plazo, asegúrese de tiempo de respuesta y limitar el sistema para evitar una sobrecarga cuando prolongado, se producen picos inesperados. Si no tiene datos para ajustar la propiedad de longitud de la cola de ASP, será un buen punto de partida establecer una relación uno a uno de las colas en subprocesos totales. Por ejemplo, si se establece la propiedad ASP subprocesos por procesador Limit en 25 y tiene cuatro procesadores (4 * 25 = 100 subprocesos), establezca la propiedad de longitud de la cola de ASP en 100 y ajustar desde allí.  
  
 Para aumentar el valor de la propiedad de longitud de la cola, siga estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el **conexiones** panel, seleccione el servidor Web, haga clic para seleccionar **vista características**y, a continuación, haga doble clic en el **ASP** característica.  
  
3.  Haga clic para expandir **límites propiedades** en **comportamiento**, haga clic en **longitud de cola**, escriba el valor deseado para **longitud de cola** y, a continuación, Haga clic en **aplicar** en el **acciones** panel.  
  
 Para obtener más información sobre cómo modificar las propiedades de la \<límites > elemento de IIS 7.0 \<asp > elemento, vea [límites de ASP \<límites >](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483).  
  
> [!NOTE]  
>  Dado que esta propiedad solo se aplica en el nivel de servidor, la modificación de esta propiedad afecta a todos los sitios Web que se ejecutan en el servidor.  
  
> [!NOTE]  
>  El ASP **longitud de cola** propiedad para IIS 7.0 reemplaza IIS 6.0 **AspRequestQueueMax** configuración de Metabase de ASP. Para obtener información acerca de la configuración de la Metabase de IIS 6.0 AspRequestQueueMax ASP, consulte [configuración de optimización de la Metabase de ASP](http://go.microsoft.com/fwlink/?LinkId=158834) (http://go.microsoft.com/fwlink/?LinkId=158834) en MSDN.  
  
## <a name="tune-the-maxpoolthreads-registry-entry"></a>Optimizar la entrada de registro MaxPoolThreads  
 Esta configuración especifica el número de subprocesos del grupo pueden crear por cada procesador. Subprocesos de grupo analizan la red para las solicitudes y procesar las solicitudes entrantes. El recuento de MaxPoolThreads no incluye los subprocesos consumidos por aplicaciones ISAPI. Por lo general, no debería crear más de 20 subprocesos por procesador. MaxPoolThreads es una entrada de registro REG_DWORD ubicada en HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\InetInfo\Parameters\ con un valor predeterminado de 4.  
  
## <a name="disable-wcf-services-tracing"></a>Deshabilitar el seguimiento de los servicios WCF  
 Utilice la herramienta Editor de configuración (SvcConfigEditor.exe) para deshabilitar el seguimiento en un entorno de producción de los servicios WCF. Para obtener más información acerca de la herramienta Editor de configuración, consulte [herramienta Editor de configuración (SvcConfigEditor.exe)](http://go.microsoft.com/fwlink/?LinkID=127070) (http://go.microsoft.com/fwlink/?LinkID=127070).  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)