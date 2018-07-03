---
title: Contadores de rendimiento de los adaptadores WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, WCF adapters
- performance, performance counters
- WCF adapters, performance
ms.assetid: 9feb052f-5674-419f-84ab-9b5d312a04a5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5b916b6212da18dcf4aa48d4ca941e23413513d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016255"
---
# <a name="wcf-adapters-performance-counters"></a>Contadores de rendimiento de los adaptadores de WCF
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por un servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor. Los adaptadores de WCF no proporcionan sus propios contadores de rendimiento. No obstante, puede supervisar los contadores de rendimiento de Windows Communication Foundation (WCF) para calibrar el rendimiento de las ubicaciones de recepción WCF. Con el fin de usar los contadores de rendimiento de WCF para las ubicaciones de recepción WCF, tiene que habilitar los contadores de rendimiento para las instancias de host que ejecutan las ubicaciones de recepción.  
  
> [!NOTE]
>  Los contadores de rendimiento de WCF no están disponibles para los puertos de envío.  
  
 Para los adaptadores de WCF de tipo En curso, puede habilitar los contadores de rendimiento a través del archivo BTSNTSvc.exe.config. En el caso de los adaptadores de WCF aislados, puede modificar el archivo Web.config para habilitar los contadores de rendimiento. Para obtener más información acerca de los contadores de rendimiento de WCF, vea "WCF Performance Counters" en [ http://go.microsoft.com/fwlink/?LinkID=87245 ](http://go.microsoft.com/fwlink/?LinkID=87245).  
  
## <a name="enabling-the-wcf-performance-counters-for-the-wcf-receive-locations"></a>Habilitar los contadores de rendimiento de WCF para las ubicaciones de recepción WCF  
 Para los adaptadores de WCF de tipo En curso, puede habilitar los contadores de rendimiento a través del archivo BTSNTSvc.exe.config.  
  
 En el caso de los adaptadores de WCF aislados, puede habilitar el seguimiento de WCF mediante la modificación del archivo Web.config que el Asistente para publicación de Servicio WCF de BizTalk crea en la carpeta de la aplicación Web.  
  
 Para modificar los archivos BTSNtSvc.exe.config o Web.config, abra el archivo de configuración y, a continuación, configure el seguimiento de WCF, como se indica en el ejemplo de configuración siguiente:  
  
> [!NOTE]
>  El archivo BTSNTSvc.exe.config siempre está ubicado en el mismo directorio que el archivo BTSNTSvc.exe, que normalmente es [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  
```  
<configuration>  
 <system.serviceModel>  
 <diagnostics performanceCounters="All" />  
 </system.serviceModel>  
 </configuration>  
```  
  
 El **performanceCounters** atributo puede establecerse para habilitar un tipo específico de contadores de rendimiento. Los valores válidos son  
  
- **Todos los**: todos los contadores de categoría (**ServiceModelService**, **ServiceModelEndpoint**, y **ServiceModelOperation**) están habilitadas.  
  
- **ServiceOnly**: solo **ServiceModelService** se habilitan los contadores de categoría.  
  
- **Desactivar**: contadores de rendimiento ServiceModel * están deshabilitados. Este es el valor predeterminado.  
  
  Después de modificar el archivo BTSNTSvc.exe.config, debe reiniciar las instancias de host que ejecutan las ubicaciones de recepción WCF de tipo En curso.  
  
## <a name="types-of-performance-counters"></a>Tipos de contadores de rendimiento  
 Contadores de rendimiento de WCF se limitan a tres niveles diferentes: servicio, punto de conexión y operación.  
  
 **Contadores de rendimiento de servicio**  
  
 Los contadores de rendimiento de servicio miden el comportamiento del servicio en su conjunto y pueden emplearse para diagnosticar el rendimiento del servicio completo. Se encuentran en el **ServiceModelService 3.0.0.0** objeto de rendimiento cuando se ven con el Monitor de rendimiento. Los nombres de las instancias se asignan mediante el patrón siguiente:  
  
```  
biztalkserviceinstance@<URI of a receive location>  
```  
  
 Puesto que los adaptadores de WCF crean un host de servicio independiente para cada ubicación de recepción, se crea una instancia de contador de rendimiento para cada ubicación de recepción. Para obtener más información acerca de la clase de servicio implementa WCF contratos de servicio, vea el **BizTalkServiceInstance (clase)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 
  
 **Contadores de rendimiento del punto de conexión**  
  
 Los contadores de rendimiento de extremo permiten observar los datos que reflejan el modo en que un extremo acepta los mensajes. Se encuentran en el **ServiceModelEndpoint 3.0.0.0** objeto de rendimiento cuando se ven con el Monitor de rendimiento. Los nombres de las instancias se asignan mediante el patrón siguiente:  
  
```  
biztalkserviceinstance.<WCF service contract>@<URI of a receive location>  
```  
  
 Se crea una instancia de contador de rendimiento para cada ubicación de recepción. En el patrón anterior, el nombre del contrato de servicio de WCF representa el contrato de servicio que los adaptadores de WCF eligen para recibir los mensajes a través de la ubicación de recepción. Para obtener más información sobre cómo los adaptadores de WCF eligen un contrato de servicio de WCF disponible contratos de servicio, consulte **referencia de contrato de servicio de adaptadores de WCF** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
 **Contadores de rendimiento de la operación**  
  
 Contadores de rendimiento de la operación se encuentran en el **ServiceModelOperation 3.0.0.0** objeto de rendimiento cuando se ven con el Monitor de rendimiento. Se crean dos instancias de contadores de rendimiento para cada ubicación de recepción. El nombre de una de las instancias de objetos se asigna mediante el patrón siguiente:  
  
```  
biztalkserviceinstance.<WCF service contract>biztalksubmit@<URI of a receive location>  
```  
  
 En el patrón anterior, el nombre del contrato de servicio de WCF representa el contrato de servicio que los adaptadores de WCF eligen para recibir los mensajes a través de la ubicación de recepción. **biztalksubmit** es un nombre de operación declarado en el contrato de servicio y hace que el tiempo de ejecución cree operaciones de WSDL en los metadatos.  
  
> [!NOTE]
>  Para obtener más información sobre cómo los adaptadores de WCF eligen un contrato de servicio de WCF disponible contratos de servicio, consulte **referencia de contrato de servicio de adaptadores de WCF** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
 El nombre de la otra instancia de objetos se asigna mediante el patrón siguiente:  
  
```  
biztalkserviceinstance.<WCF service contract><twowaymethod|onewaymethod>@<URI of a receive location>  
```  
  
 Esta instancia del contador de rendimiento representa la operación que procesa de forma asíncrona los mensajes entrantes a través de la ubicación de recepción. La parte del nombre de operación de esta instancia puede ser **twowaymethod** o **onewaymethod** según el tipo de adaptador WCF usado en la ubicación de recepción. Si usa el adaptador WCF-NetMsmq, una instancia con el **onewaymethod** se crea el nombre de la operación. Para los demás adaptadores **twowaymethod** se usa para la parte del nombre de operación.